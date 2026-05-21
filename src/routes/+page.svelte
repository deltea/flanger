<script lang="ts">
  import { animate, scrambleText, utils } from "animejs";
  import AudioWave from "$lib/components/AudioWave.svelte";
  import { onMount } from "svelte";
  import Separator from "$lib/components/Separator.svelte";
  import "iconify-icon";

  onMount(() => {
    utils.$("#scramble").forEach(text => {
      animate(text, {
        innerHTML: scrambleText({
          chars: "blocks",
          revealDelay: 250,
          revealRate: 30
        }),
      });
    });

    animate("#cover", {
      opacity: { from: 1, to: 0 },
      duration: 600
    })
  });
</script>

<div id="cover" class="fixed inset-0 bg-black z-50 pointer-events-none"></div>

<main class="bg-bg h-full bg-grid squircle rounded-[6rem] xl:text-lg text-base overflow-y-auto">
  <div class="fixed inset-0 bg-grid-back pointer-events-none"></div>

  <div class="flex flex-col justify-center items-center lg:h-[calc(100vh-6rem)] h-[calc(100vh-2rem)] relative px-8">
    <!-- audio waveform thingy -->
    <div class="absolute top-4 w-full">
      <AudioWave />
    </div>

    <div class="w[30rem] lg:w-2/5 w-4/5 text-xl mt-8 mb-20">
      <p id="scramble" class="glow">Presenting...</p>
      <img src="/images/flanger.png" alt="Flanger Logo" class="glow-filter w-full">
      <p class="float-right glow">
        <span id="scramble">by</span>
        <span id="scramble" class="underline decoration-2">Hack Club</span>
      </p>
    </div>

    <div class="bg-primary text-white px-2.5 glow-filter-primary mb-16">
      <p>Ship a music related project, and get a DAW for free!</p>
    </div>

    <!-- <div class="flex gap-2">
      <input
        type="email"
        name="Email"
        id="email"
        class="border-2 px-4 py-2 w-96 border-secondary glow-filter-secondary"
        placeholder="johnflanger@gmail.com"
      />
      <button class="border-2 border-secondary px-4 py-2 glow-filter-secondary">RSVP</button>
    </div> -->

    <div class="w-full h-48 bg-[url(/images/dither-transition-top.png)] bg-repeat-x bg-contain pixelated absolute bottom-0 left-0 z-10"></div>
  </div>

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

  <section class="bg-black px-8">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni saepe neque eum velit. Voluptatum consectetur neque nihil assumenda necessitatibus porro praesentium error magni. Eligendi a autem ducimus. Maiores, suscipit magnam.
    Neque ipsa magni exercitationem omnis asperiores dolores laudantium tenetur et veritatis. Doloribus, nemo in! Neque voluptas tempora saepe quas corrupti repellat inventore exercitationem sapiente praesentium. Iste ipsa voluptatibus quo labore?
    Asperiores corrupti officia molestias odio, dolorum ut repellendus odit fuga, rem in dicta. Iure optio, vero quas et reiciendis molestiae enim nisi eaque velit hic omnis nesciunt rem necessitatibus earum?
    Esse, deleniti quis nostrum quidem aut inventore commodi quas quos enim reiciendis. Atque ipsum autem hic libero architecto dignissimos tempora ad natus? Quae consectetur dolores id odio. Suscipit, reiciendis maiores.
    Harum esse est tempore eum nisi velit, saepe corporis culpa quod recusandae eaque accusantium cum consequatur dolor deleniti, illo possimus ipsum natus? Iusto iure illum soluta atque doloremque laboriosam vero.
  </section>

  <Separator position="bottom" />

  <section class="h-screen px-8">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni saepe neque eum velit. Voluptatum consectetur neque nihil assumenda necessitatibus porro praesentium error magni. Eligendi a autem ducimus. Maiores, suscipit magnam.
    Neque ipsa magni exercitationem omnis asperiores dolores laudantium tenetur et veritatis. Doloribus, nemo in! Neque voluptas tempora saepe quas corrupti repellat inventore exercitationem sapiente praesentium. Iste ipsa voluptatibus quo labore?
    Asperiores corrupti officia molestias odio, dolorum ut repellendus odit fuga, rem in dicta. Iure optio, vero quas et reiciendis molestiae enim nisi eaque velit hic omnis nesciunt rem necessitatibus earum?
    Esse, deleniti quis nostrum quidem aut inventore commodi quas quos enim reiciendis. Atque ipsum autem hic libero architecto dignissimos tempora ad natus? Quae consectetur dolores id odio. Suscipit, reiciendis maiores.
    Harum esse est tempore eum nisi velit, saepe corporis culpa quod recusandae eaque accusantium cum consequatur dolor deleniti, illo possimus ipsum natus? Iusto iure illum soluta atque doloremque laboriosam vero.
  </section>
</main>

