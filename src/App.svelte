<script>
  import Header from "./UI/Header.svelte";
  import Button from "./UI/Button.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import EditMeetup from "./Meetups/EditMeetup.svelte";

  let meetups = [
    {
      id: "m1",
      title: "Coding Bootcamp",
      subtitle: "Learn to code in 2 hours",
      description:
        "In this meetup, we will have some experts that teach you how to code!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/e/e4/Caffe_Nero_Expresso_Bar%2C_Sutton%2C_Surrey%2C_Greater_London.jpg",
      address: "27th Nerd Road, 32523 London",
      contactEmail: "code@test.com",
      isFavorite: false
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Let's go for some swimming",
      description: "We will simply swim some rounds!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/0/02/Aquatics_Centre_London_2012.jpg",
      address: "27th Nerd Road, 32523 London",
      contactEmail: "swim@test.com",
      isFavorite: false
    }
  ];

  let editMode;

  function addMeetup(event) {
    const newMeetUp = {
      id: Math.random().toString(),
      title: event.detail.title,
      subtitle: event.detail.subtitle,
      address: event.detail.address,
      email: event.detail.email,
      description: event.detail.description,
      imageUrl: event.detail.imageUrl
    };

    meetups = [newMeetUp, ...meetups];
    editMode = null;
  }

  function toggleFavorite(event) {
    const id = event.detail;
    // create new copy of array and mutate it
    const updatedMeetup = { ...meetups.find(m => m.id === id) };
    updatedMeetup.isFavorite = !updatedMeetup.isFavorite;
    const meetupIndex = meetups.findIndex(m => m.id === id);
    // copy of existing meetups
    const updatedMeetups = [...meetups];
    updatedMeetups[meetupIndex] = updatedMeetup;
    meetups = updatedMeetups;
  }

  function cancelEdit() {
    editMode = null;
  }
</script>

<main class="bg-gray-200">
  <Header />
  <div class="mt-16">
    <div class="m-4">
      <Button on:click={() => (editMode = 'add')}>New Meetup</Button>
    </div>
    {#if editMode === 'add'}
      <EditMeetup on:save={addMeetup} on:cancel={cancelEdit} />
    {/if}
    <MeetupGrid {meetups} on:togglefavorite={toggleFavorite} />
  </div>
</main>
