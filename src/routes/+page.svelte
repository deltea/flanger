<script lang="ts">
  import AudioWave from "$lib/components/AudioWave.svelte";
</script>

<main class="bg-[#1e182a] h-full squircle rounded-[6rem] flex justify-center items-center text-lg relative overflow-hidden bg-grid">
  <!-- background back layer -->
  <div class="size-full bg-grid-back absolute inset-0"></div>

  <!-- audio waveform thingy -->
  <div class="absolute top-8 w-full">
    <!-- <AudioWave /> -->
  </div>

  <div class="w-[30rem] text-xl">
    <p class="glow">Presenting...</p>
    <img src="/flanger.png" alt="Flanger Logo" class="glow-filter w-full">
    <p class="float-right glow">by <span class="underline decoration-2">Hack Club</span></p>
  </div>

  <div class="w-full h-52 bg-[url(/dither-transition.png)] absolute bottom-0 left-0 bg-repeat-x bg-contain"></div>

  <!-- orpheus flag -->
  <!-- <a
    href="https://hackclub.com"
    class="group -left-3 top-8 absolute"
  >
    <img
      src="/hack-club.png"
      alt="Hack Club Flag"
      class="group-hover:rotate-8 origin-[left_center] duration-75 glow-filter-pink"
      width="300"
    >
  </a> -->
</main>
