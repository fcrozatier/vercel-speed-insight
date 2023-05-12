<script>
  import { webVitals } from "$lib/vitals";
  import { browser } from "$app/environment";
  import { page } from "$app/stores";

  let analyticsId = import.meta.env.VERCEL_ANALYTICS_ID;

  console.log("analyticsId:", analyticsId);

  $: if (browser && analyticsId) {
    console.log("analyticsId:", analyticsId);

    webVitals({
      path: $page.url.pathname,
      params: $page.params,
      analyticsId,
    });
  }
</script>

<header>
  <nav>
    <a href="/">home</a>
    <a href="/about">about</a>
    <a href="/contact">contact</a>
  </nav>
</header>

<main>
  <slot />
</main>
