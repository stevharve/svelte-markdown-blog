<script>
  import {
    Grid,
    Row,
    Column,
    Loading
    } from 'carbon-components-svelte'
  
  import ArticleCard from '../lib/article/ArticleCard.svelte'

  const getArticles = async () => {

    const res = await fetch('https://svelte.dev/tutorial/random-number')

    if(res.ok) {
      return res.text()
    } else {
      throw new Error(res.text())
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
          <ArticleCard />
        {/each}
      {:catch error}
        <h1>Error while loading data! {error}</h1>
      {/await}
    </Column>
  </Row>
</Grid>

<style>
  
</style>