<script>
  import Header from './header.svelte'
  import { Content } from 'carbon-components-svelte'
</script>

<main>
  <Header />
  <Content>
    <slot />
  </Content>
</main>

<style>

</style>