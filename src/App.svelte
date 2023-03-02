<script>
  import Router from "svelte-spa-router";
  // @ts-ignore
  import routes from "virtual:generated-pages-svelte";
  import "@unocss/reset/tailwind.css";
  import "warna-tailwind/warna.css";
  import latar from "./gambar/latar.jpg";
</script>

<img src={latar} alt="" class="latar" />
<Router {routes} />

<style>
  .latar {
    z-index: -1;
    object-fit: cover;
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
  }
  :global(*) {
    word-wrap: break-word;
  }
  /* chrome extension */
  :global(body) {
    width: 350px;
    font-size: 16px;
  }
</style>
