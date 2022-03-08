<script>
  import { Loading } from 'carbon-components-svelte'

  export let params = {}

  const getArticle = async () => {

  const res = await fetch(`https://markdown-blog-api.herokuapp.com/articles/${params.slug}`)

  if(res.ok) {
    return res.json()
  } else {
    throw new Error(res.json())
  }
  }

  let article = getArticle()

  console.log(article)
</script>

<svelte:head>
  <title>{params.slug} | Svelte Markdown Blog</title>
</svelte:head>

{#await article}
  <Loading />
{:then data}
  <h2>{data.title}</h2>
  {@html data.sanitizedHtml}
{:catch error}
  <h1>Error while loading data! {error}</h1>
{/await}