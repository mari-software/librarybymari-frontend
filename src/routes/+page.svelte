<script>
	import Carousel from '$lib/components/carousel/Carousel.svelte';
	import Entrance from '$lib/components/entrance/Entrance.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';
	import TopNavigation from '$lib/components/navigation/TopNavigation.svelte';
</script>

<TopNavigation
  navBarLogoTextSource = "Mari_Gold"
  navBarLogoSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
  navBarMenuToggle={true}
  navBarMenuSource="Dashboard" 
  navBarSearchToggle={false}
  navBarSearchSource = "🔍 What's on your mind?"
  NavBarMenuButtonToggle={false}
  NavBarMenuButtonSource = "Create"
  NavBarMenuIconToggle={true}
  NavBarMenuIconSource="https://cdn-icons-png.flaticon.com/512/147/147144.png"
/>


<Entrance
	mainEntranceSource="Mari_Gold"
	mainEntranceText="Build your ideas faster"
	mainEntranceButton="See more"
/>
<hr />

<!-- <Carousel />
<hr />

<Footer
	navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
	navBarLogoTextSource="Mari_Gold"
/>
 -->