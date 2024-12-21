<script>
	import DonationPage from "$lib/components/donationPage/donationPage.svelte";

</script>
<DonationPage
currencySource = {[
	{ currency: 'USD' ,currencyFull: 'USD | United States Dollar' },
	{ currency: 'MMK' ,currencyFull: 'MMK | Myanmar Kyat' },
	{ currency: 'THB' ,currencyFull: 'THB | Thai Baht' },
]}

donationAmount = {[
	{ amount: '10$' },
	{ amount: '25$' },
	{ amount: '50$' },
	{ amount: '100$' },
]}
/>