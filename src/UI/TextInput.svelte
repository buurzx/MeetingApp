<script>
  export let controlType = false;
  export let id;
  export let label;
  export let rows = 3;
  export let value;
  export let type = "text";
  export let valid = true;
  export let validityMessage = "true";
</script>

<style>
  .invalid {
    border-color: red;
    background-color: lightcoral;
  }
</style>

<div class="py-1 w-full my-1">
  <label class="block mb-2 w-full" for={id}>{label}</label>
  {#if controlType === 'textarea'}
    <textarea
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none"
      class:invalid={!valid}
      {rows}
      {id}
      {value}
      on:input />
  {:else}
    <input
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none"
      {type}
      id="title"
      {value}
      on:input />
  {/if}

  {#if validityMessage && !valid}
    <p class="text-red-500">{validityMessage}</p>
  {/if}
</div>
