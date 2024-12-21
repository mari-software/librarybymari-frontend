<script>
	import Footer from '$lib/components/footer/Footer.svelte';
	import TopNavigation from '$lib/components/navigation/TopNavigation.svelte';
</script>

<TopNavigation
	navBarLogoTextSource="mari"
	navBarLogoSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
	navBarMenuToggle={true}

	navBarMenuSource={[
		{ options: 'Home', link: '/' },
		{ options: 'Components', link: '/components' },
		{ options: 'CDK', link: '/' },
		{ options: 'Guides', link: '/' },
		{ options: 'Donate Us', link: '/donationPage' }
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
/>

<hr>

<slot />

<hr />
<Footer
	navBarLogoSource="https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d"
	navBarLogoTextSource="mari"
	footerTextCopyright={`Copyright &copy; ${new Date().getFullYear()} mari`}
	footerTextAllRights="All rights reserved"
	footerContactText="Get regular updated for better experience"
/>
