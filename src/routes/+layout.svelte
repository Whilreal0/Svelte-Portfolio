<script>
  import "../app.css";
  import Sidebar from "../components/Sidebar.svelte";
  import Header from "../components/Header.svelte";

  let screenWidth;
  let innerHeight;
  let y;

  let navItems = [
    {name : 'Home', link: '/'},
    {name : 'About', link: '/about'},
    {name : 'Projects', link: '/projects'},
  ]
  let navSocials = [
    {
      name : 'mdi:linkedin' , link : ''
    },
    {
      name : 'mdi:github' , link : ''
    },
    {
      name : 'mdi:facebook' , link : ''
    },
  ]
</script>

<svelte:head>
  <title>Home</title>
</svelte:head>
<svelte:window
  bind:scrollY={y}
  bind:innerHeight
  bind:innerWidth={screenWidth}
/>
<div class="relative flex md:flex-row flex-col text-[#413228]   max-h-full">
  <!-- {#if screenWidth >= 768} -->
    <Sidebar {navItems} {navSocials}/>
    
  <!-- {:else} -->
    <Header {y} {navItems} {navSocials}/>
  <!-- {/if} -->
  <div class="mx-auto theme-light-primary 2xl:ml-24 mt-5 md:mt-24 px-3 md:px-0 max-w-[1050px] md:max-w-[540px] lg:max-w-[750px] xl:max-w-[1100px] w-full">
    <slot />
  </div>
</div>
