<script>
  import { createEventDispatcher } from "svelte";
  import Button from "../UI/Button.svelte";
  import Badge from "../UI/Badge.svelte";

  export let id;
  export let title;
  export let subtitle;
  export let imageUrl;
  export let description;
  export let address;
  export let contactEmail;
  export let isFavorite = false;

  const dispatch = createEventDispatcher();
</script>

<article class="shadow-md rounded-lg bg-white m-4 flex flex-col">
  <header class="p-4">
    <h1 class="flex items-center font-roboto">
      {title}
      {#if isFavorite}
        <Badge>Favorite</Badge>
      {/if}
    </h1>
    <h2>{subtitle}</h2>
    <p>{address}</p>
  </header>

  <div class="relative my-4 h-64">
    <img class="absolut h-full w-full object-cover" src={imageUrl} alt="" />
  </div>

  <div class="p-4 h-32">
    <p class="text-xl m-0 float-right">{description}</p>
  </div>
  <footer class="p-4 justify-end">
    <Button href="mailto:{contactEmail}">Contact</Button>
    <Button
      type="button"
      color={isFavorite ? null : 'success'}
      mode="outline"
      on:click={dispatch('togglefavorite', id)}>
      {isFavorite ? 'Unfavorite' : 'Favorite'}
    </Button>
    <Button type="button">Show Details</Button>
  </footer>
</article>
