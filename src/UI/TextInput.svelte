<script>
  export let controlType = false;
  export let id;
  export let label;
  export let rows = 3;
  export let value;
  export let type = "text";
  export let valid = true;
  export let validityMessage = "true";

  let touched = false;

  $: invalidClass =
    !valid && touched ? "bg-red-100 border-red-200 border-b-2" : "";
</script>

<style>

</style>

<div class="py-1 w-full my-1 border-re">
  <label class="block mb-2 w-full" for={id}>{label}</label>
  {#if controlType === 'textarea'}
    <textarea
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none {invalidClass}"
      {rows}
      {id}
      bind:value
      on:blur={() => (touched = true)}
      on:input />
  {:else}
    <input
      class="block w-full bg-white px-2 py-1 border-0 border-b-2
      transition-colors duration-500 ease-in-out border-gray-600 rounded-sm
      focus:border-red-500 focus:outline-none {invalidClass}"
      {type}
      id="title"
      {value}
      on:blur={() => (touched = true)}
      on:input />
  {/if}

  {#if validityMessage && !valid && touched}
    <p class="text-red-500">{validityMessage}</p>
  {/if}
</div>
