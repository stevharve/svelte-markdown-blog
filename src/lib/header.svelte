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
  } from "carbon-components-svelte"

  import Home16 from "carbon-icons-svelte/lib/Home16"
  import Information16 from "carbon-icons-svelte/lib/Information16"

  let isSideNavOpen = false
</script>

<main>
  <Header company="Svelte" platformName="Markdown Blog" bind:isSideNavOpen>
    <svelte:fragment slot="skip-to-content">
      <SkipToContent />
    </svelte:fragment>
    <!-- <HeaderNav>
      <HeaderNavItem href="#/" text="Home" />
      <HeaderNavItem href="#/about" text="About" />
    </HeaderNav> -->

    <SideNav rail bind:isOpen={isSideNavOpen}>
      <SideNavItems>
        <SideNavLink isSelected icon={Home16} href="#/" text="Home" />
        <SideNavLink icon={Information16} href="#/about" text="About" />
      </SideNavItems>
    </SideNav>
  </Header>
</main>

<style>

</style>