<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';
  import TextInput from './UI/TextInput.svelte';

  let title = "";
  let subtitle = "";
  let address = "";
  let email = "";
  let description = "";
  let imageUrl = "";

  let meetups = [
    {
      id: 'm1',
      title: 'Goth Coding Bootcamp',
      subtitle: 'Learn to code like a goth in 2 hours',
      description: 'In this meetup we will have some goths that teach you how to code',
      imageUrl: 'https://www.thebeaverton.com/wp-content/uploads/2017/12/447599_43d3200458_o.jpg',
      address: 'The Crypt, Highgate Cemetary, Highgate N6, UK',
      contactEmail: 'code@gothcode.com'
    },
    {
      id: 'm2',
      title: 'Swimming With Goths',
      subtitle: 'Let\'s go swim with some goths',
      description: 'In this meetup we will swim with the goths',
      imageUrl: 'https://i.ytimg.com/vi/YHU_k6QykU8/maxresdefault.jpg',
      address: 'The Swamp, Highgate Cemetary, Highgate N6, UK',
      contactEmail: 'swim@gothswim.com'
    }
  ];

  function addMeetup() {
    const newMeetup = {
      id: Math.random.toString(),
      title: title,
      subtitle: subtitle,
      description: description,
      imageUrl: imageUrl,
      contactEmail: email,
      address: address
    }

    meetups = [newMeetup, ...meetups];
  }
</script>

<style>
  main {
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
  <form on:submit|preventDefault="{addMeetup}">
    <TextInput id="title" label="Title" type="text" value={title} on:input="{event => (title = event.target.value)}" />
    <TextInput id="subtitle" label="Subtitle" type="text" value={subtitle} on:input="{event => (subtitle = event.target.value)}" />
    <TextInput id="address" label="Address" type="text" value={address} on:input="{event => (address = event.target.value)}" />
    <TextInput id="imageUrl" label="Image URL" type="text" value={imageUrl} on:input="{event => (imageUrl = event.target.value)}" />
    <TextInput id="email" label="Email" type="email" value={email} on:input="{event => (email = event.target.value)}" />
    <TextInput id="description" label="Description" type="textarea" value={description} on:input="{event => (description = event.target.value)}" />
    <button type="submit">Save</button>
  </form>
  <MeetupGrid {meetups}/>
</main>


