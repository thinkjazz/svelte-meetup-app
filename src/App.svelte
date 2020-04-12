<script>
  import Header from "./UI/Header.svelte";
  import MeetupGrid from "./Meetups/MeetupGrid.svelte";
  import TextInput from './UI/TextInput.svelte';
  
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
  form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>

<Header />

<main>
  <form on:submit|preventDefault={addMeetup}>
      <TextInput id="title"
                 label="Title"
                 value={title}
                 type="text"
                 on:input={(event) => title = event.target.value}
    />
     <TextInput id="subtitle"
                label="Subtitle"
                value={subtitle}
                type="text"
                on:input={(event) => subtitle = event.target.value}
     />
    <TextInput id="address"
               label="Address"
               value={address}
               type="text"
               on:input={(event) => address = event.target.value}
    />
   <TextInput id="urlImage"
              label="Url Image"
              value={urlImage}
              type="text"
              on:input={(event) => urlImage = event.target.value}
   />                                                                     
  <TextInput id="email"
             label="E-mail"
             value={email}
             type="email"
             on:input={(event) => email = event.target.value}
  />                                                               
   <TextInput id="description"
              label="Description"
              value={description}
              controlType="textarea"
              on:input={(event) => description = event.target.value}
   />
    <button type="submit">Save</button>
   </form>
    <MeetupGrid {meetups}/>
</main>
