<script>
  import Header from './UI/Header.svelte';
  import MeetupGrid from './Meetups/MeetupGrid.svelte';

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
</style>

<Header />

<main>
  <form on:submit|preventDefault="{addMeetup}">
    <div class="form-control">
        <label for="title">Title</label>
        <input type="text" id="title" bind:value={title} />
    </div>
    <div class="form-control">
        <label for="subtitle">Subtitle</label>
        <input type="text" id="subtitle" bind:value={subtitle} />
    </div>
    <div class="form-control">
        <label for="imageUrl">Image URL</label>
        <input type="text" id="imageUrl" bind:value={imageUrl} />
    </div>
    <div class="form-control">
        <label for="address">Address</label>
        <input type="text" id="address" bind:value={address} />
    </div>
    <div class="form-control">
        <label for="contactEmail">Contact Email</label>
        <input type="email" id="contactEmail" bind:value={email} />
    </div>
    <div class="form-control">
        <label for="description">Description</label>
        <textarea rows="3" id="description" bind:value={description} />
    </div>
    <button type="submit">Save</button>
  </form>
  <MeetupGrid {meetups}/>
</main>


