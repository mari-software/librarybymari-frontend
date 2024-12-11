<script>
	import Carousel from '$lib/components/carousel/Carousel.svelte';
	import Entrance from '$lib/components/entrance/Entrance.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';
	import TopNavigation from '$lib/components/navigation/TopNavigation.svelte';
</script>

<TopNavigation 
  navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
  navBarLogoTextSource="Mari_Gold"
  navBarMenuSource="Menu Source"
/>

<Entrance 
mainEntranceSource= "Mari_Gold"
mainEntranceText= "Build your ideas faster"
mainEntranceButton= "See more"
/>

<Carousel />

<Footer
navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
navBarLogoTextSource="Mari_Gold" />


