<script>
  import MeetupItem from "./MeetupItem.svelte";
  export let meetups;
</script>

<section class="w-full grid grid-cols-1 gap-1 md:grid-cols-2 mt-16">
  {#each meetups as meetup}
    <MeetupItem
      title={meetup.title}
      subtitle={meetup.subtitle}
      description={meetup.description}
      contactEmail={meetup.contactEmail}
      address={meetup.address}
      imageUrl={meetup.imageUrl} />
  {/each}
</section>
