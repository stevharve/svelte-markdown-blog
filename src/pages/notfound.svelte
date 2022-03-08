<script>
  // Possibly include a back spa button instead of one that sends to home
  import { location } from 'svelte-spa-router'
  
  import { Grid, Row, Column, ClickableTile } from 'carbon-components-svelte'
</script>

<svelte:head>
  <title>404 | Svelte Markdown Blog</title>
</svelte:head>

<Grid>
  <Row>
    <Column>
      <h1>404</h1>
      <h3>The path requested: {$location} was not found on this server.</h3>
      <ClickableTile href="#/">
        Home
      </ClickableTile>
    </Column>
    <Column />
    <Column />
  </Row>
</Grid>
