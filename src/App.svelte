<script>
  // CSS
  import "carbon-components-svelte/css/all.css";

  import Router from 'svelte-spa-router'

  import Layout from './lib/__layout.svelte'

  import Index from './pages/index.svelte'
  import About from './pages/about.svelte'
</script>

<main>
  <Layout>
    <Router routes={{
      '/': Index,
      '/about': About
    }} />
  </Layout>
</main>

<style>
	
</style>