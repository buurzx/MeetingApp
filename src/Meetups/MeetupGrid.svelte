<script>
  import MeetupItem from "./MeetupItem.svelte";
  export let meetups;
</script>

<section class="w-full grid grid-cols-1 gap-1 md:grid-cols-2 mt-2">
  {#each meetups as meetup}
    <MeetupItem {...meetup} on:togglefavorite />
  {/each}
</section>
