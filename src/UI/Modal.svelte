<script>
  import Button from "./Button.svelte";
  export let title;
</script>

<div class="fixed top-0 right-0 w-full h-screen z-10 bg-gray-800 opacity-75" />

<div
  class="fixed bg-white z-20 rounded-sm overflow-scroll shadow-md max-h-80s
  w-4/5 lg:w-5/12 font-roboto"
  id="modal">
  <h1 class="m-0 p-4 border-b border-solid border-gray-300">{title}</h1>
  <div class="p-4">
    <slot />
  </div>
  <footer class="p-4">
    <slot name="footer">
      <Button>Close</Button>
    </slot>
  </footer>
</div>
