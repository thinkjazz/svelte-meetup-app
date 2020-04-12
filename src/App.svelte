<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  const meetups = [
    {
      id: 1,
      title: 'Coding bootcamp',
      subtitle: "Learign svelte",
      description: 'Hey this  is description. Un this meetup. We will have some expert opinion',
      urlImage: 'https://www.codingdojo.com/blog/wp-content/uploads/coding-bootcamps-vs-cs-degrees.png',
      address: '27 Los Robles, 22133 Pasadena',
      contactEmail: "code@code.com"

  },
    {
      id: 2,
      title: 'Javascript 2020 bootcamp',
      subtitle: "Learign js",
      description: 'Hey this is description',
      urlImage: 'https://s.dou.ua/img/announces/COAX_Bootcamp_2019_-_JS.png',
      address: '100 Main Street, 666 LA',
      contactEmail: "main@code.com"
    }

  ];
</script>
<style>
  main{
    margin-top: 5rem;
  }
</style>

<Header />

<main>
    <MeetupGrid {meetups}/>
</main>
