<script>
  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    SideNav,
    SideNavItems,
    SideNavMenu,
    SideNavMenuItem,
    SideNavLink,
    SideNavDivider,
    SkipToContent,
    Content,
    Grid,
    Row,
    Column,
  } from "carbon-components-svelte"

  let isSideNavOpen = false
</script>

<main>
  <Header company="Svelte" platformName="Markdown Blog" bind:isSideNavOpen>
    <svelte:fragment slot="skip-to-content">
      <SkipToContent />
    </svelte:fragment>
    <HeaderNav>
      <HeaderNavItem href="#/" text="Home" />
      <HeaderNavItem href="#/about" text="About" />
    </HeaderNav>

    <SideNav bind:isOpen={isSideNavOpen}>
      <SideNavItems>
        <SideNavLink href="#/" text="Home" />
        <SideNavLink href="#/about" text="About" />
      </SideNavItems>
    </SideNav>
  </Header>
</main>

<style>

</style>