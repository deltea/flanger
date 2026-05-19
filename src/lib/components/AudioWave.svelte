<script lang="ts">
  import { onMount } from "svelte";
  import { animate, svg, utils } from "animejs";

  const WIDTH = 1000;
  const HEIGHT = 60;

  let path: SVGPolylineElement;

  onMount(() => {
    utils.set(path, { points: generatePoints() });
    // setInterval(() => {
    //   animate(path, {
    //     points: svg.createDrawable
    //   });
    // }, 1000);
  });

  function generatePoints() {
    const steps = 60;
    const height = 8;
    let points = "";
    for (let i = 0; i < steps + 1; i++) {
      const isOdd = i % 2 === 0;
      const x = i * (WIDTH / steps);
      const y = isOdd ? (HEIGHT / 2 - height) : (HEIGHT / 2 + height);
      points += `${x},${y} `;
    }
    return points;
  }
</script>

<svg viewBox="0 0 {WIDTH} {HEIGHT}">
  <g stroke-width="2" stroke="var(--color-secondary)" fill="none" fill-rule="evenodd">
    <polyline bind:this={path} />
  </g>
</svg>
