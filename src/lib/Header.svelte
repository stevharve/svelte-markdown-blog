<script>
  import { location } from 'svelte-spa-router'

  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    // SideNav,
    // SideNavItems,
    // SideNavMenu,
    // SideNavMenuItem,
    // SideNavLink,
    // SideNavDivider,
    SkipToContent,
    HeaderUtilities,
    HeaderAction,
    HeaderPanelLinks,
    HeaderPanelLink,
    HeaderPanelDivider
  } from "carbon-components-svelte"

  import UserAvatarFilledAlt20 from "carbon-icons-svelte/lib/UserAvatarFilledAlt20"
  // import Home32 from "carbon-icons-svelte/lib/Home32"
  // import Information32 from "carbon-icons-svelte/lib/Information32"

  let isSideNavOpen = false
  let isAccountOpen = false
  
  const onPath = (loc, path) => {
  if(loc === path) {
    return true
  } else {
    return false
  }
}
</script>

<Header href="#/" company="Svelte" platformName="Markdown Blog" bind:isSideNavOpen>
  <svelte:fragment slot="skip-to-content">
    <SkipToContent />
  </svelte:fragment>
  <HeaderNav>
    <HeaderNavItem isSelected={onPath($location, '/')} href="#/" text="Home" />
    <HeaderNavItem isSelected={onPath($location, '/about')} href="#/about" text="About" />
  </HeaderNav>
  <HeaderUtilities>
    <HeaderAction bind:isOpen={isAccountOpen} icon={UserAvatarFilledAlt20}>
      <HeaderPanelLinks>
        <HeaderPanelDivider>Account</HeaderPanelDivider>
        <HeaderPanelLink href="#/login" on:click={() => isAccountOpen = false}>Log In</HeaderPanelLink>
      </HeaderPanelLinks>
    </HeaderAction>
  </HeaderUtilities>

  <!-- <SideNav rail bind:isOpen={isSideNavOpen}>
    <SideNavItems>
      <SideNavLink isSelected={onPath($location, '/')} icon={Home32} href="#/" text="Home" />
      <SideNavLink isSelected={onPath($location, '/about')} icon={Information32} href="#/about" text="About" />
    </SideNavItems>
  </SideNav> -->
</Header>

<style>

</style>
