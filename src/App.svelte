<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  let title = '';
  let subtitle = '';
  let address = '';
  let email = '';
  let description = '';
  let urlImage = '';

  let meetups = [
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
  function addMeetup() {
    const newMeetup = {
      id: Math.random().toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      urlImage: urlImage,
      address:address,
      contactEmail: email
    };
    meetups = [...meetups, newMeetup]
  }
</script>
<style>
  main{
    margin-top: 5rem;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
    <div class="form-control">
      <label for="title">Title</label>
      <input type="text" id="title" class="" bind:value={title}>
    </div>
    <div class="form-control">
      <label for="subtitle">SubTitle</label>
      <input type="text" id="subtitle" class="" bind:value={subtitle}>
    </div>
    <div class="form-control">
      <label for="address">Address</label>
      <input type="text" id="address" class="" bind:value={address}>
    </div>
    <div class="form-control">
      <label for="urlImage">Image Url</label>
      <input type="text" id="urlImage" class="" bind:value={urlImage}>
    </div>
    <div class="form-control">
      <label for="email">E-mail</label>
      <input type="email" id="email" class="" alt="" bind:value={email}>
    </div>
    <div class="form-control">
      <label for="description">Description</label>
      <textarea bind:value={description} rows="3" id="description"/>
    </div>
    <button type="submit">Save</button>
  </form>
    <MeetupGrid {meetups}/>
</main>
