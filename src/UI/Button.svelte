<script>
  export let type = null;
  export let href = null;
  export let mode = null;
  export let color = null;
  export let disabled = false;
</script>

{#if href}
  <a class="text-xs sm:text-base no-underline" {href}>
    <slot />
  </a>
{:else}
  <button
    class="{color} text-xs sm:text-base py-1 px-2 {mode}"
    {type}
    {disabled}
    on:click>
    <slot />
  </button>
{/if}
