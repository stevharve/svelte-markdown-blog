<script>
  import { Loading } from 'carbon-components-svelte'
  import { onMount } from 'svelte'

  export let params = {}
  let title = 'Article | Svelte Markdown Blog'
  let article

  const getArticle = async () => {

  const res = await fetch(`https://markdown-blog-api.herokuapp.com/articles/${params.slug}`)

  if(res.ok) {
    return res.json()
  } else {
    throw new Error(res.json())
  }
  }

  onMount(async () => {
    article = await getArticle()
  })
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

{#await article}
  <Loading />
{:then data}
  {title = `${data.title} | Svelte Markdown Blog`}
  <h2>{data.title}</h2>
  {@html data.sanitizedHtml}
{:catch error}
  {title = 'Error | Svelte Markdown Blog'}
  <h1>Error while loading data! {error}</h1>
{/await}