<script>
  // CSS
  import "carbon-components-svelte/css/all.css";

  import Router from 'svelte-spa-router'
  import wrap from 'svelte-spa-router/wrap'

  import Layout from './lib/__layout.svelte'

  import Index from './pages/index.svelte'
  import About from './pages/about.svelte'
  // import Article from './pages/article.svelte' Done dynamicly in router
  import NotFound from "./pages/notfound.svelte";
</script>

<svelte:head>
  <title>Svlete Markdown Blog</title>
</svelte:head>

<main>
  <Layout>
    <Router routes={{
      '/': Index,
      '/about': About,
      '/article/:slug': wrap({
        asyncComponent: () => import('./pages/article.svelte')
      }),
      '*': NotFound
    }} />
  </Layout>
</main>

<style>
	
</style>