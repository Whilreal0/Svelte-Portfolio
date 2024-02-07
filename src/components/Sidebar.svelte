<script>
  import "iconify-icon";

  export let navItems;
  export let navSocials;
</script>

<nav
  class="bg-[#9c7760]  sticky top-0 bottom-0 h-[100vh] gap-24 hidden md:flex w-full max-w-[160px] flex-col  items-center"
>
  <span class="text-6xl my-10">WR</span>
  <div class="w-full">
    <ul class="flex flex-col justify-center items-center gap-5">
      {#each navItems as item}
        <li class="hover:scale-105 hover:text-[#271e18] transition-all duration-200 ease-in-out font-bold  text-lg"><a class=" py-2 px-3.5 " href={item.link}>{item.name}</a></li>
      {/each}
    </ul>
  </div>
  <div class="flex items-end justify-center w-full bg-red-300 h-full  mb-5">
    <ul class=" flex flex-col justify-center items-center gap-3">
      {#each navSocials as item}
        <li class="hover:scale-125  transition-transform duration-200 ease-in">
          <a class="p-1 flex" href={item.link}>
            <iconify-icon class="text-gray-300 hover:text-white" icon={item.name} height="30"  />
          </a>
        </li>
      {/each}
    </ul>
  </div>
</nav>
