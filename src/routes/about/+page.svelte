<script>
  let skills = [
    { icon: "devicon:html5", name: 'Html 5' },
    { icon: "devicon:css3", name: 'CSS3' },
    { icon: "devicon:javascript", name: 'Javascript' },
    { icon: "devicon:tailwindcss", name: 'Tailwind CSS' },
    { icon: "devicon:vuejs", name: 'Vue.js' },
    { icon: "devicon:vuetify", name: 'Vuetify' },
    { icon: "devicon:git", name: 'Git' },
    { icon: "devicon:github", name: 'Github' },
    { icon: "devicon:bootstrap", name: 'Bootstrap' },
    { icon: "devicon:wordpress", name: 'Wordpress' },
    { icon: "devicon:html5", name: 'html5' },
  ];
</script>

<div class="flex flex-col gap-4">
  <h3 class="text-3xl py-4 bg-gray-200">Knowledge and Skills</h3>
  <div>
    <p class="bg-red-300">
      As a web developer I've worked with small businesses, start-ups and
      individuals to create web products. Here are some of the tools and
      technologies i've used to create web products:
    </p>
  </div>
  <div
    class="w-full max-w-[300px] sm:max-w-[400px] md:max-w-full mx-auto lg:mx-0 lg:max-w-[700px]"
  >
    <div
      class="grid grid-cols-2
            sm:grid-cols-3
            md:grid-cols-4
            lg:grid-cols-5
            gap-1 md:gap-2"
    >
      {#each skills as item}
        <div class=" h-36 max-h-36 w-full max-w-40 mx-auto shadow-md ">
          <div class="h-[70%] flex items-center justify-center">
            <iconify-icon class="" icon={item.icon} height="72px" />
          </div>
          <div class="h-[30%] text-center">
            <h2>{item.name}</h2>
          </div>
        </div>
      {/each}
    </div>
  </div>
</div>
