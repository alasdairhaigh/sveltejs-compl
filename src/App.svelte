<script>
  import Header from './UI/Header.svelte';
  import MeetupItem from './Meetups/MeetupItem.svelte';

  const meetups = [
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
</script>

<style>
  #meetups {
    margin-top: 5rem;
  }
</style>

<Header />

<section id="meetups">
  {#each meetups as meetup}
    <MeetupItem />
  {/each}
</section>

