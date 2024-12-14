<script>
	import CarouselNext from '$lib/carouselNext/carouselNext.svelte';
	import Community from '$lib/components/community/Community.svelte';
	import Carousel from '$lib/components/carousel/Carousel.svelte';
	import Entrance from '$lib/components/entrance/Entrance.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';
	import TopNavigation from '$lib/components/navigation/TopNavigation.svelte';
</script>

<TopNavigation
	navBarLogoTextSource="Mari_Gold"
	navBarLogoSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
	navBarMenuToggle={true}

	navBarMenuSource={[
		{ options: 'Home', link: '/' },
		{ options: 'Components', link: '/' },
		{ options: 'CDK', link: '/' },
		{ options: 'Guides', link: '/' },
		{ options: 'Donate Us', link: '/' }
	]}



	navBarSearchToggle={false}
	navBarSearchSource="🔍 What's on your mind?"
	NavBarMenuButtonToggle={false}
	NavBarMenuButtonSource="Create"
	NavBarMenuIconToggle={true}
	NavBarMenuIconSource="https://banner2.cleanpng.com/20180617/uzy/kisspng-gitlab-github-continuous-integration-computer-icon-5b25ebd5d3e583.5178856115292118618679.jpg"

	dropDownSource = {[
		{ options: 'option-1', link: '/' },
		{ options: 'option-2', link: '/' },
		{ options: 'option-3', link: '/' },
		{ options: 'option-4', link: '/' }
	]}
/>

<Entrance
	mainEntranceSource="Mari_Gold"
	mainEntranceText="Build your ideas faster"
	mainEntranceButton="See more"
/>
<hr />

<!-- <Carousel /> -->

<!-- Carousel-1 -->

<!-- <CarouselNext
	carouselDataSource={[
		{
			image:
				'https://steamuserimages-a.akamaihd.net/ugc/2486634816019385799/42EAD597D63146529E43BAE1425E25FA5E39A9D3/?imw=637&imh=358&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=true',
			heading: 'Slide 1',
			carouselDataHeaderSource: 'Header for Slide 1',
			carouselDataTextSource: 'Description for Slide 1'
		},
		{
			image:
				'https://static.animecorner.me/2024/09/1726468888-2731cfe1c0a510ad6809ed6cb3af3bcd.png',
			heading: 'Slide 1',
			carouselDataHeaderSource: 'Header for Slide 1',
			carouselDataTextSource: 'Description for Slide 1'
		},
		{
			image:
				'https://i.ytimg.com/vi/A2x5q69sZNw/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDl2AQfF3dzcAR-7L5YqhpGJpQW8w',
			heading: 'Slide 1',
			carouselDataHeaderSource: 'Header for Slide 1',
			carouselDataTextSource: 'Description for Slide 1'
		},
		{
			image:
				'https://admin.esports.gg/wp-content/uploads/2024/11/Genshin-Impact-drip-marketing-Citlali-reveal-968x544.jpg',
			heading: 'Slide 1',
			carouselDataHeaderSource: 'Header for Slide 1',
			carouselDataTextSource: 'Description for Slide 1'
		}
	]}
	carouselDataTextSource=""
	carouselDataHeaderSource=""
	sliderToggle={true}
	sliderImage={true}
	sliderText={true}
	sliderHeading={true}
	active={0}
	itemLength={2}
/> -->

<hr />

<!-- Carousel-2 -->

<CarouselNext
	carouselDataSource={[]}
	carouselDataTextSource=""
	carouselDataHeaderSource=""
	sliderToggle={true}
	sliderImage={false}
	sliderText={true}
	sliderHeading={false}
	active={0}
	itemLength={3}
/>

<hr />

<!--  Carousel-3 -->

<CarouselNext
	carouselDataSource={[]}
	carouselDataTextSource=""
	carouselDataHeaderSource=""
	sliderToggle={true}
	sliderImage={true}
	sliderText={true}
	sliderHeading={true}
	active={0}
	itemLength={3}
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

<hr />
<Footer
	navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
	navBarLogoTextSource="Mari_Gold"
	footerTextCopyright={`Copyright &copy; ${new Date().getFullYear()} Mari_Gold`}
	footerTextAllRights="All rights reserved"
	footerContactText="Get regular updated for better experience"
/>
