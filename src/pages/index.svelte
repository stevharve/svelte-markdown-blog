<script>
  import {
    Grid,
    Row,
    Column,
    Loading
    } from 'carbon-components-svelte'
  
  import ArticleCard from '../lib/article/ArticleCard.svelte'

  /*
    IMPORTANT FOR FUTURE:
    Use a store to hold all of the articles so that the api
    isn't called so frequently
  */

  const getArticles = async () => {

    const res = await fetch('http://localhost:5000/articles')

    if(res.ok) {
      return res.json()
    } else {
      throw new Error(res.json())
    }
  }

  let articles = getArticles()

</script>

<Grid>
  <Row>
    <Column>
      <h1>Articles</h1>
    </Column>
  </Row>
  <Row>
    <Column>
      {#await articles}
        <Loading withOverlay={false} />
      {:then data}
        {#each data as article}
          <ArticleCard title={article.title} description={article.description} href={`#/article/${article.slug}`} />
        {/each}
      {:catch error}
        <h1>Error while loading data! {error}</h1>
      {/await}
    </Column>
  </Row>
</Grid>

<style>
  
</style>