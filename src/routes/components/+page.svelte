<script>
	import Components from '$lib/components/compSelection/compSelection.svelte';
import Sidenavigation from '$lib/components/sideNavigation/sidenavigation.svelte';
</script>

<main>

  <div class="component-slide">
    
    <Sidenavigation
    navBarSource={[
      {
	  sidenavHeaderSource: 'Category-1',
    sidenavContentSource: [
      {  sidenavComponentSource: 'Component-1', link: '/' },
      { sidenavComponentSource: 'Component-2', link: '/'  },
      { sidenavComponentSource: 'Component-3', link: '/'  },
    ]
  },
  {
    sidenavHeaderSource: 'Category-1',
    sidenavContentSource: [
      {  sidenavComponentSource: 'Component-1', link: '/' },
      { sidenavComponentSource: 'Component-2', link: '/'  },
      { sidenavComponentSource: 'Component-3', link: '/'  },
    ]
  },
  {
    sidenavHeaderSource: 'Category-1',
    sidenavContentSource: [
      {  sidenavComponentSource: 'Component-1', link: '/' },
      { sidenavComponentSource: 'Component-2', link: '/'  },
      { sidenavComponentSource: 'Component-3', link: '/'  },
    ]
  },
]}
/>

<Components
componentSource = {[
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
]}
/>

</div>

</main>
<style>

  main {
    margin-top: 4rem;
  }
  .component-slide {
    /* display: grid;
    grid-template-columns: repeat(auto-fit, minmax(20px, 1fr));
    gap: 0px; */
    
    display: flex;
  }
  
</style>
