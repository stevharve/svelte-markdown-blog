<script>
  import { ClickableTile, Grid, Row } from 'carbon-components-svelte'

  export let href = "#/"
</script>

<ClickableTile href={href}>
  <Grid>
    <Row>
      <h3>Article Name</h3>
    </Row>
    <Row>
      <h5>Article desc</h5>
    </Row>
  </Grid>
</ClickableTile>