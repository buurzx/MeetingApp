<script>
  import Header from "./UI/Header.svelte";
  import TextInput from "./UI/TextInput.svelte";
  import Button from "./UI/Button.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

  let title = "";
  let subtitle = "";
  let address = "";
  let email = "";
  let description = "";
  let imageUrl = "";

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
      contactEmail: "code@test.com"
    },
    {
      id: "m2",
      title: "Swim Together",
      subtitle: "Let's go for some swimming",
      description: "We will simply swim some rounds!",
      imageUrl:
        "https://upload.wikimedia.org/wikipedia/commons/0/02/Aquatics_Centre_London_2012.jpg",
      address: "27th Nerd Road, 32523 London",
      contactEmail: "swim@test.com"
    }
  ];

  function addMeetup() {
    const newMeetUp = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      address: address,
      email: email,
      description: description,
      imageUrl: imageUrl
    };

    meetups = [newMeetUp, ...meetups];
  }
</script>

<main class="bg-gray-200">
  <Header />
  <div class="mt-16">
    <form
      class="w-4/12 max-w-11/12 m-auto"
      on:submit|preventDefault={addMeetup}>
      <TextInput
        id="title"
        label="Title"
        value={title}
        on:input={event => (title = event.target.value)} />
      <TextInput
        id="subtitle"
        label="Subtitle"
        value={subtitle}
        on:input={event => (subtitle = event.target.value)} />
      <TextInput
        id="address"
        label="Address"
        value={address}
        on:input={event => (address = event.target.value)} />
      <TextInput
        id="imageUrl"
        label="Image URL"
        value={imageUrl}
        on:input={event => (imageUrl = event.target.value)} />
      <TextInput
        id="email"
        label="E-mail"
        value={email}
        type="email"
        on:input={event => (email = event.target.value)} />
      <TextInput
        id="description"
        label="Description"
        value={description}
        controlType="textarea"
        on:input={event => (description = event.target.value)} />

      <Button type="submit" caption="Save" />

    </form>
    <MeetupGrid {meetups} />
  </div>
</main>
