<script>
  import { onMount } from "svelte";
  import { slide } from 'svelte/transition';
  export let y
  export let navItems;
  export let navSocials;
  let isOpen = false;
  // 



  // for opening and closing nav
  let navOpen = () => {
    isOpen = !isOpen;
    if (isOpen) {
      document.body.style.overflow = "hidden"; // Disable scrolling
    } else {
      document.body.style.overflow = ""; // Enable scrolling
    }
  };
  let closeMenu = () => {
    isOpen = false;
    document.body.style.overflow = ""; // Enable scrolling
  };
  // Cleanup function to re-enable scrolling when component is unmounted
  onMount(() => {
    return () => {
      document.body.style.overflow = ""; // Enable scrolling
    };
  });
</script>

<header
  class={"py-3 px-3 w-full flex md:hidden items-center transition ease-in duration-300 justify-between bg-[#DDD0C8]" +
    (y > 0 ? " sticky  top-0 left-0 right-0 drop-shadow-md" : "static ")}
>
  <span class="text-3xl">WR</span>
  <button
    class="md:hidden flex {isOpen ? 'hidden' : 'flex'}"
    on:click={navOpen}
  >
    <iconify-icon class=" " icon="charm:menu-hamburger" height="30" />
  </button>
  <button
    class="items-end md:hidden flex {isOpen ? 'flex' : 'hidden'}"
    on:click={navOpen}
  >
    <iconify-icon class=" " icon="f7:xmark" height="30" />
  </button>

  {#if isOpen}
    <!--  -->
    <a 
      href="/#"
      class="absolute md:hidden flex bg-black opacity-65 h-[100vh] inset-0 mt-[60px] {isOpen
        ? 'flex'
        : 'hidden'} "
      on:click={navOpen}
    >
    </a>
    <!-- content here -->
    <div transition:slide={{ delay: .5, duration: 300 }}
      class="bg-[#DDD0C8] absolute  md:hidden gap-5 py-3 px-4 w-full right-0 top-[60px] flex flex-col items-center"
    >
      <ul class="text-center">
        {#each navItems as item}
          <li><a href={item.link} on:click={closeMenu}>{item.name}</a></li>
        {/each}
      </ul>
      <ul class="">
        {#each navSocials as item}
          <li>
            <a href={item.link}>
              <iconify-icon class=" " icon={item.name} height="30" />
            </a>
          </li>
        {/each}
      </ul>
    </div>
  {/if}
</header>
