<script lang="ts">
  let { position }: { position: "top" | "bottom" } = $props();
</script>

<div
  class="w-full h-48 bg-repeat-x bg-contain pixelated z-10"
  style:background-image="url('/images/dither-transition-{position}.png')"
></div>
