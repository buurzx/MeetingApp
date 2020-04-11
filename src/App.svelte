<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";

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
</script>

<main class="bg-gray-200">
  <Header />
  <MeetupGrid {meetups} />
</main>
