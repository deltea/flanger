<script lang="ts">
  import { onMount } from "svelte";

  let audioCtx: AudioContext;
  let analyser: AnalyserNode;
  let audioElement: HTMLAudioElement;
  let dataArray: Uint8Array<ArrayBuffer>;
  let bufferLength: number;

  let canvas: HTMLCanvasElement;
  let ctx: CanvasRenderingContext2D;

  onMount(() => {
    audioCtx = new AudioContext();
    analyser = audioCtx.createAnalyser();

    const source = audioCtx.createMediaElementSource(audioElement);
    source.connect(analyser);
    analyser.connect(audioCtx.destination);

    analyser.fftSize = 512;
    bufferLength = analyser.frequencyBinCount;
    dataArray = new Uint8Array(bufferLength);

    ctx = canvas.getContext("2d")!;

    audioElement.onplay = () => {
      if (audioCtx.state === "suspended") audioCtx.resume();
    };

    // draw();
    setInterval(() => {
      draw();
    }, 100);
  });

  function draw() {
    // requestAnimationFrame(draw);

    analyser.getByteTimeDomainData(dataArray);

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    ctx.lineWidth = 2;
    ctx.strokeStyle = "#c589dc";
    ctx.beginPath();

    const WIDTH = 1000;
    const HEIGHT = 50;

    const sliceWidth = WIDTH / bufferLength;
    let x = 0;
    let offset = 0;
    for (let i = 0; i < bufferLength; i++) {
      const v = dataArray[i] / 600.0;
      let y = ((v + 1) ** 1.5 - 1) * (HEIGHT / 2);

      if (i === 0) {
        ctx.moveTo(x, HEIGHT / 2);
        offset = HEIGHT / 2 - y;
      } else {
        ctx.lineTo(x, y + offset);
      }

      x += sliceWidth;
    }

    ctx.lineTo(WIDTH, HEIGHT / 2);
    ctx.stroke();
  }
</script>

<canvas
  bind:this={canvas}
  class="w-full pixelated"
  width="1000"
  height="50"
></canvas>

<audio
  bind:this={audioElement}
  src="/music.mp3"
  autoplay
  class="hidden"
></audio>
