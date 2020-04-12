<script>
  export let controlType;
  export let id;
  export let label;
  export let rows;
  export let value;
  export let type;
</script>

<style>

</style>

<div class="py-1 w-full my-1">
  <label class="block mb-2 w-full" for={id}>{label}</label>
  {#if controlType === 'textarea'}
    <textarea
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none"
      {rows}
      {id}
      {value}
      on:input />
  {:else}
    <input
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none"
      type={type ? type : 'text'}
      id="title"
      {value}
      on:input />
  {/if}
</div>
