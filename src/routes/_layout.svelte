<script context="module">
  import { fetchYaml } from '../utils/queries'

  export async function preload() {
    const nav = await fetchYaml(`Nav`)
    const footer = await fetchYaml(`Footer`)
    const social = await fetchYaml(`Social`)

    return { nav, footer, social }
  }
</script>

<script>
  import Header from '../components/Header.svelte'
  import Footer from '../components/Footer.svelte'
  import GoogleAnalytics from '../components/GoogleAnalytics.svelte'

  export let nav, footer, social
</script>

<GoogleAnalytics />
<Header {nav} />
<main>
  <slot />
</main>
<Footer {...footer} {social} />
