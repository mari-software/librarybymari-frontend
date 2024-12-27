<script>
	import CarouselNext from '$lib/components/carouselNext/carouselNext.svelte';
	import Community from '$lib/components/community/Community.svelte';
	import Carousel from '$lib/components/carousel/Carousel.svelte';
	import Entrance from '$lib/components/entrance/Entrance.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';
	import TopNavigation from '$lib/components/navigation/TopNavigation.svelte';
</script>

<main>

	
	<!-- <TopNavigation
	navBarLogoTextSource="mari"
	navBarLogoSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
	navBarMenuToggle={true}
	
	navBarMenuSource={[
		{ options: 'Home', link: '/' },
		{ options: 'Components', link: '/components' },
		{ options: 'CDK', link: '/' },
		{ options: 'Guides', link: '/' },
		{ options: 'Donate Us', link: '/' }
		]}
		
		
		navBarHeaderDropDown={true}
		NavBarMenuIconToggle={true}
		NavBarMenuIconSource="https://banner2.cleanpng.com/20180617/uzy/kisspng-gitlab-github-continuous-integration-computer-icon-5b25ebd5d3e583.5178856115292118618679.jpg"
		
		dropDownSource = {[
			{ options: 'option-1', link: '/' },
		{ options: 'option-2', link: '/' },
		{ options: 'option-3', link: '/' },
		{ options: 'option-4', link: '/' }
		]}
		/> -->
		
		<Entrance
		mainEntranceSource="mari"
		mainEntranceText="Build your ideas faster"
		mainEntranceButton="See more"
		/>
		<hr />
		
		<!-- <Carousel /> -->
		
		<!-- Carousel-1 -->
		
		<!-- <CarouselNext
		carouselDataSource={[]}
		carouselDataTextSource=""
		carouselDataHeaderSource=""
		sliderToggle={true}
		sliderImage={false}
		sliderTextToggle={true}
		sliderHeading={false}
		active={0}
		itemLength={3}
		/> -->
		
		<hr />
		
		
<!-- Carousel-2 -->

<CarouselNext 
carouselOptionMenu="Components"
carouselMoreMenu="View more Components"
carouselMoreMenuLink="/"

carouselDataSource={[
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Get Started',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 2',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 3',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 4',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	}
]}
carouselDataTextSource=""
carouselDataHeaderSource=""
sliderToggle={true}
sliderImage={true}
sliderTextToggle={true}
sliderHeading={true}
active={0}
itemLength={2}
/>

<hr />

<!--  Carousel-3 -->

<CarouselNext 
carouselOptionMenu="Blog"
carouselMoreMenu="View more blogs"
carouselMoreMenuLink="/"

carouselDataSource={[
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Get Started',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 2',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 3',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	},
	{
		image:
		'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		heading: 'Slide 4',
		carouselDataHeaderSource: 'Get Started',
		carouselDataTextSource: 'Add Mari_Gold materials to your projects.',
		link: '/'
	}
]}
carouselDataTextSource=""
carouselDataHeaderSource=""
sliderToggle={true}
sliderImage={true}
sliderTextToggle={true}
sliderHeading={true}
active={0}
itemLength={2}
/>

<hr />


<Community 
blogDataSource={[
	{
		blogImage: 'https://cdn3.iconfinder.com/data/icons/social-network-30/512/social-06-512.png',
		blogHeading: 'YouTube',
		blogText: 'Visit our YouTube channel to see latest tutorials'
		},
		{
			blogImage: 'https://cdn.prod.website-files.com/6257adef93867e50d84d30e2/636e0a6a49cf127bf92de1e2_icon_clyde_blurple_RGB.png',
			blogHeading: 'Discord',
			blogText: 'Join our Discord serve to become a part of community'
		},
		{
			blogImage: 'https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg',
			blogHeading: 'Blogs',
			blogText: 'News and Tips from Mari Team'
		},
	]}
/>

<!-- <hr />
<Footer
navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
navBarLogoTextSource="mari"
footerTextCopyright={`Copyright &copy; ${new Date().getFullYear()} mari`}
footerTextAllRights="All rights reserved"
footerContactText="Get regular updated for better experience"
/> -->

</main>

<style>
	main {

		margin-top: 4rem;
	}
</style>