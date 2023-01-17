<script lang="ts">
    import { browser } from '$app/environment'
	  import type { Theme } from 'src/types/theme';
    let html_tag : HTMLHtmlElement|null
    if (browser) {
      html_tag = document.getElementsByTagName("html").item(0) 
    }
    function set_dark_theme(){
      const theme :Theme="dark"
      localStorage.setItem("theme",theme);
      html_tag?.classList.add("dark")
    }

    function set_light_theme(){
      const theme :Theme="light"
      localStorage.setItem("theme",theme);
        html_tag?.classList.remove("dark")
    }
</script>
<div class="ml-auto flex items-center relative">
    <div class="opacity-0 text-gray-700 text-3xl mr-5 pointer-events-none">
      <span class="iconify" data-icon="bi:sun-fill" />
    </div>
    <div
      class="text-gray-700 text-3xl mr-5 duration-300 absolute left-0 spring-light cursor-pointer dark:opacity-0 dark:pointer-events-none dark:rotate-180"
      on:click={set_dark_theme}
    >
      <span class="iconify" data-icon="bi:sun-fill" />
    </div>
    <div
      class="text-gray-300 text-2xl mr-5 duration-300 absolute left-0 spring cursor-pointer translate-x-1
         opacity-0 pointer-events-none -rotate-180 dark:opacity-100 dark:pointer-events-auto dark:rotate-0"
      on:click={set_light_theme}
    >
      <span class="iconify" data-icon="bi:moon-fill" />
    </div>
</div>