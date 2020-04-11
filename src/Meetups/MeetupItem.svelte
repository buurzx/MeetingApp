<script>
  export let title;
  export let subtitle;
  export let imageUrl;
  export let description;
  export let address;
  export let contactEmail;
</script>

<article class="shadow-md rounded-lg bg-white m-4 flex flex-col">
  <header class="p-4">
    <h1>{title}</h1>
    <h2>{subtitle}</h2>
    <p>{address}</p>
  </header>

  <div class="relative my-4 h-64">
    <img class="absolut h-full w-full object-cover" src={imageUrl} alt="" />
  </div>

  <div class="p-4 lg:h-16">
    <p class="text-xl m-0 float-right">{description}</p>
  </div>
  <footer class="p-4 justify-end">
    <a href="mailto:{contactEmail}">Contact</a>
    <button class="text-xs py-1 rounded px-2 m-1">Show Details</button>
    <button class="text-xs py-1 rounded px-2 m-1">Favorite</button>
  </footer>
</article>
