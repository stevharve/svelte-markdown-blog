<script>
  import { ClickableTile, Grid, Row } from 'carbon-components-svelte'

  export let title
  export let description
  export let href
</script>

<ClickableTile href={href}>
  <Grid>
    <Row>
      <h3>{title}</h3>
    </Row>
    <Row>
      <h5>{description}</h5>
    </Row>
  </Grid>
</ClickableTile>