<script lang="ts">
  import { animate, scrambleText, utils } from "animejs";
  import AudioWave from "$lib/components/AudioWave.svelte";
  import { onMount } from "svelte";

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

<main class="bg-bg h-full bg-grid squircle rounded-[6rem] text-lg overflow-y-auto">
  <div class="fixed inset-0 -z20 bg-grid-back pointer-events-none"></div>

  <div class="flex flex-col justify-center items-center h-[calc(100vh-6rem)] relative">
    <!-- audio waveform thingy -->
    <div class="absolute top-6 w-full">
      <AudioWave />
    </div>

    <div class="w-[30rem] text-xl">
      <p id="scramble" class="glow">Presenting...</p>
      <img src="/flanger.png" alt="Flanger Logo" class="glow-filter w-full">
      <p class="float-right glow">
        <span id="scramble">by</span>
        <span id="scramble" class="underline decoration-2">Hack Club</span>
      </p>
    </div>

    <div class="w-full h-52 bg-[url(/dither-transition-top.png)] bg-repeat-x bg-contain pixelated absolute bottom-0 left-0"></div>
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

  <section class="h120 bg-black px-8">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni saepe neque eum velit. Voluptatum consectetur neque nihil assumenda necessitatibus porro praesentium error magni. Eligendi a autem ducimus. Maiores, suscipit magnam.
    Neque ipsa magni exercitationem omnis asperiores dolores laudantium tenetur et veritatis. Doloribus, nemo in! Neque voluptas tempora saepe quas corrupti repellat inventore exercitationem sapiente praesentium. Iste ipsa voluptatibus quo labore?
    Asperiores corrupti officia molestias odio, dolorum ut repellendus odit fuga, rem in dicta. Iure optio, vero quas et reiciendis molestiae enim nisi eaque velit hic omnis nesciunt rem necessitatibus earum?
    Esse, deleniti quis nostrum quidem aut inventore commodi quas quos enim reiciendis. Atque ipsum autem hic libero architecto dignissimos tempora ad natus? Quae consectetur dolores id odio. Suscipit, reiciendis maiores.
    Harum esse est tempore eum nisi velit, saepe corporis culpa quod recusandae eaque accusantium cum consequatur dolor deleniti, illo possimus ipsum natus? Iusto iure illum soluta atque doloremque laboriosam vero.
  </section>

  <div class="w-full h-52 bg-[url(/dither-transition-bottom.png)] bg-repeat-x bg-contain pixelated"></div>

  <section class="h-screen px-8">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni saepe neque eum velit. Voluptatum consectetur neque nihil assumenda necessitatibus porro praesentium error magni. Eligendi a autem ducimus. Maiores, suscipit magnam.
    Neque ipsa magni exercitationem omnis asperiores dolores laudantium tenetur et veritatis. Doloribus, nemo in! Neque voluptas tempora saepe quas corrupti repellat inventore exercitationem sapiente praesentium. Iste ipsa voluptatibus quo labore?
    Asperiores corrupti officia molestias odio, dolorum ut repellendus odit fuga, rem in dicta. Iure optio, vero quas et reiciendis molestiae enim nisi eaque velit hic omnis nesciunt rem necessitatibus earum?
    Esse, deleniti quis nostrum quidem aut inventore commodi quas quos enim reiciendis. Atque ipsum autem hic libero architecto dignissimos tempora ad natus? Quae consectetur dolores id odio. Suscipit, reiciendis maiores.
    Harum esse est tempore eum nisi velit, saepe corporis culpa quod recusandae eaque accusantium cum consequatur dolor deleniti, illo possimus ipsum natus? Iusto iure illum soluta atque doloremque laboriosam vero.
  </section>

  <div class="w-full h-52 bg-[url(/dither-transition-top.png)] bg-repeat-x bg-contain pixelated"></div>

  <footer class="bg-black px-8 pb-8">
    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Doloremque, unde! Est, dolorem quam. Explicabo, tempora! Voluptates incidunt nesciunt nobis perferendis rerum dolores illo veniam natus ad, quia, earum iusto similique.
    Porro deserunt consequuntur tenetur aliquid voluptas laborum mollitia dolor, possimus eaque asperiores quisquam adipisci nisi iusto voluptate, eligendi eveniet facere quae, repellat est esse quo ipsam fuga illum. Consequuntur, quasi.
    Laboriosam quidem officiis consequatur minima dolorum ad, neque illo tenetur vero iusto, rerum fugit perferendis dolore placeat. Aliquam distinctio itaque in odit? Commodi ducimus a eveniet esse? Deleniti, veritatis explicabo?
    Minima molestias sit dicta ipsam dolor ab inventore ullam eaque rerum, mollitia obcaecati perspiciatis? Aspernatur repudiandae dignissimos aliquam inventore facere, tenetur ipsum dolorum at quas recusandae rem et nisi delectus!
    Vel harum suscipit ipsa reprehenderit repudiandae nemo, sequi quae commodi ipsum eaque neque minus omnis, sunt natus quas, debitis eos iste cum iure sit temporibus consequuntur minima nisi! Necessitatibus, veniam.
  </footer>
</main>

