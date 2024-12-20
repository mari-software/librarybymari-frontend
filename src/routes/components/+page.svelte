<script>
	import Components from '$lib/components/compSelection/compSelection.svelte';
import Sidenavigation from '$lib/components/sideNavigation/sidenavigation.svelte';
</script>

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
  {cardImage: 'https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg', cardTitle: 'Component-1', cardDescription: 'This component does this', link: '/'},
]}
/>
