<script lang="ts">
	interface donationPageInterface {
		// Config

		donationHeader: string;
		donationText: string;
		donationQuote: string;

		currencySource: any[];
		donationAmount: any[];

		// Function
	}

	let {
		//Config
		currencySource = [],
		donationAmount = [],

		donationHeader = '',
		donationText = '',
		donationQuote = ''
	}: donationPageInterface = $props();

	// Function
	let activeCurrency = $state();

	function setActive(selectedCurrency: string) {
		activeCurrency = selectedCurrency;
	}
</script>

<main>
	<div class="donation-intro">
		<h1>{donationHeader}</h1>
		<p>
			{donationText}
		</p>
		<div class="quote">{donationQuote}</div>
	</div>

	<div class="donation-box">
		{#each donationAmount as { amount }}
			<!-- svelte-ignore a11y_click_events_have_key_events -->
			<!-- svelte-ignore a11y_no_static_element_interactions -->
			<div
				onclick={() => setActive(amount)}
				class="donation-amount-box {activeCurrency === amount ? 'active' : ''} "
			>
				{amount}
			</div>
			<!-- <div 
			onclick={() => setActive(amount)}
			class="donation-amount-box {activeCurrency === amount ? 'active' : ''}">{amount}</div> -->
			<!-- <div class="donation-amount-box" class:active={activeCurrency === amount}>{amount}</div> -->
		{/each}

		<form>
			<select>
				{#each currencySource as { currency, currencyFull }}
					<option value={currency}>{currency} </option>
				{/each}
			</select>
			<input type="text" placeholder="Type the amount..." />
		</form>
	</div>

	<p>
		{#if activeCurrency}
		amount:
		 {activeCurrency} 
		 
		 {#if activeCurrency}
			{currencySource}
		
		 {/if}
	  {/if}
	</p>
</main>

<style>
	main {
		& .donation-intro {
			margin: 2rem;

			& h1 {
				font-size: 2rem;
				margin-bottom: 1rem;
			}

			& p {
				width: 75%;
				font-size: 1.5rem;
				letter-spacing: 0.1rem;
				margin-bottom: 1rem;
			}

			& .quote {
				font-size: 1.5rem;
				font-weight: bold;
				margin-top: 1rem;
			}
		}

		& .donation-box {
			display: flex;

			& .donation-amount-box {
				/* display: flex; */
				align-items: center;
				justify-content: center;
				margin: 0.5rem;
				padding: 0.5rem 2.5rem;
				border: 1px solid #ccc;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in;
			}

			& .active {
				background-color: #005bba;
				color: white;
			}

			& .donation-amount-box:hover {
				border: 1px solid #005bba;
				color: #005bba;
			}

			& .donation-amount-box:active {
				background-color: #005bba;
				color: white;
			}

			& form {
				display: flex;
				align-items: center;
				justify-content: center;
				margin: 0.5rem;
				border: 1px solid #ccc;
				border-collapse: collapse;
				border-radius: 0.5rem;
			}

			& select {
				padding: 0.5rem 2rem;

				border: none;
				border-right: 1px solid #ccc;
				cursor: pointer;
				transition: all 0.2s ease-in;
			}

			& select:focus {
				outline: 1.5px solid #005bba;
				border-radius: 0.5rem;
			}

			& input {
				display: flex;
				padding: 0.5rem 2.5rem;
				border: none;
				/* border: 1px solid #ccc; */
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in;
			}

			& input:focus {
				outline: 1px solid #005bba;
			}

			/* & .donation-option-box {
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: center;
				margin: 0.5rem;
				border: 1px solid #ccc;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;
			} */
		}
	}

	@media (max-width: 768px) {
		main {
			& .donation-intro {
				margin: 1rem;

				& h1 {
					font-size: 1.5rem;
				}

				& p {
					font-size: 1.12rem;
					width: 100%;
				}

				& .quote {
					font-size: 1.25rem;
				}
			}

			& .donation-box {
				width: 10%;
				display: grid;
				grid-template-columns: repeat(2, 0fr);
				grid-template-rows: repeat(2, 0fr);
				 grid-gap: -20px;

				& .donation-amount-box {
					width: 1.5rem;
					padding: 0.5rem 1.5rem;
				}

				& select {
					padding: 0.5rem 1rem;
				}

				& input {
					padding: 0.5rem 2rem;
				}
			}
		}
	}
</style>
