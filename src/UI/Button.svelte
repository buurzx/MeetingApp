<script>
  export let type;
  export let caption;
  export let href;
  export let mode;
</script>

<style>

</style>

{#if href}
  <a class="text-xs sm:text-base " {href}>{caption}</a>
{:else}
  <button class="text-xs sm:text-base py-1 px-2 {mode}" {type}>
    {caption}
  </button>
{/if}
