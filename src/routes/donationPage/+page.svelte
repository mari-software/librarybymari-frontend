<script>
	import DonationPage from '$lib/components/donationPage/donationPage.svelte';
	import InfoPage from '$lib/components/informationPage/infoPage.svelte';
</script>
<main>

	<DonationPage
	currencySource={[
		{ currency: 'USD', currencyFull: 'USD | United States Dollar' },
		{ currency: 'MMK', currencyFull: 'MMK | Myanmar Kyat' },
		{ currency: 'THB', currencyFull: 'THB | Thai Baht' }
	]}
	donationAmount={[{ amount: '10$' }, { amount: '25$' }, { amount: '50$' }, { amount: '100$' }]}
	donationHeader="Help us do more"
	donationText="Mari_Gold is committed to providing free, high-quality components and assets to the developer
	community. Your donation will help us continue to develop new tools, improve existing ones,
	and keep our platform running smoothly."
	donationQuote="Every contribution, no matter how small, makes a big difference."
	/>
	
	<hr />
	
	<InfoPage />
	
</main>

<style>
	main {
		margin-top: 5rem;
	}
</style>