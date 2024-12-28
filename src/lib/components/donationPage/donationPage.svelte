<script lang="ts">
	import InfoPage from "../informationPage/infoPage.svelte";

	interface donationPageInterface {
		// Config

		donationHeader: string;
		donationText: string;
		donationQuote: string;

		currencySource: any[];
		donationAmount: any[];
		donationOption: any[];

		// Function
	}

	let {
		//Config
		currencySource = [],
		donationAmount = [],
		donationOption = [],

		donationHeader = '',
		donationText = '',
		donationQuote = ''
	}: donationPageInterface = $props();

	// Function
	let activeCurrency = $state();
	let amount = $state();
	let currencyValue = $state();
	let currencyOption = $state();

	function setActive(selectedCurrency: string) {
        activeCurrency = (activeCurrency === selectedCurrency) ? null : selectedCurrency;
    }

	function activeCurrencyOption(selectedCurrency: string) {
        currencyOption = (currencyOption === selectedCurrency) ? null : selectedCurrency;
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
		{/each}

		<form>
			<select bind:value={currencyValue}>
				{#each currencySource as { currency, currencyFull }}
					<option value={currency}>{currency} </option>
				{/each}
			</select>
			<input type="number" placeholder="Type the amount..." bind:value={amount} />
		</form>
	</div>
	<hr />

	<InfoPage />

	<hr />
	<div class="donation-check">
		<div class="donation-source">
			<div class="amount-box" style="display: flex;">
				<span>Amount:</span>

				<!-- {#if amount}
					<div class="amount">
						{amount}$
					</div>
					{#if currencyValue}
						<p class="amount">{currencyValue}</p>
					{/if}
				{:else if activeCurrency}
					<div class="amount">
						{activeCurrency}
					</div>
					{#if currencyValue}
						<p class="amount">{currencyValue}</p>
					{/if}
				{/if} -->
				{#if amount || activeCurrency}
					<div class="amount">
						{#if amount}
							{amount}$
						{:else}
							{activeCurrency}
						{/if}
					</div>
					{#if currencyValue}
						<p class="amount">{currencyValue}</p>
					{/if}
				{/if}
			</div>

			<input type="checkbox" id="checkbox" name="checkbox" />
			<label for="checkbox">Yes, I will receive the receipt of my donation. </label>
		</div>
		<div class="donation-option">
			<p>
				By donating, you agree to our <span>terms of services</span> and
				<span>privacy policy</span>.
			</p>

			{#each donationOption as { optionList }}
				<ul class="donation-option-list">
					<!-- svelte-ignore a11y_click_events_have_key_events -->
					<!-- svelte-ignore a11y_no_noninteractive_element_interactions -->
					<li 
					
					onclick={() => activeCurrencyOption(optionList)}
					class="donation-option-list {currencyOption === optionList ? 'active' : ''} "
					>{optionList}</li>
				</ul>
			{/each}
		</div>
	</div>
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
				border-radius: 0.3rem;
				outline: none;
				cursor: pointer;
				transition: all 0.2s ease-in;
			}

			& input:focus {
				outline: 1px solid #005bba;
			}

			& input::placeholder {
				color: #ccc;
			}
		}

		& .donation-check {
			margin: 2rem;
			display: flex;
			justify-content: space-around;

			& .donation-source {
				
				& .amount-box {
					font-size: 1.25rem;
					
					& span {
						font-weight: bold;
					}
				}

				& .amount {
					font-size: 4rem;
					margin: 1.2rem;
				}

				& label {
					color: #4D4D4D;

				}

				& input[type="checkbox"]:checked + label {
					color: black;
				}	
			}
			
			& p {
				font-size: 1.25rem;
				margin-bottom: 1rem;
			}
			
			& input {
				margin-right: 0.5rem;
			}
			
			& label {
				font-size: 1.25rem;
				cursor: pointer;
			}
			 
			& .donation-option {
				/* margin-top: 1rem; */
				/* margin-left: 20rem; */
				
				& p {
					text-align: center;
					font-size: 1.25rem;
					margin: 1rem 0 1rem 1.5rem;
					width: 20rem;

					& span {
						color: #005bba;
						cursor: pointer;
					}
				}

				& ul {
						text-align: center;
					& li {
						display: flex;
						align-items: center;
						justify-content: center;
						list-style: none;
						/* width: 20rem; */
						height: 2.75rem;
						border-radius: 0.25rem;
						font-size: 1.5rem;
						background-color: #005bba;
						transition: all 0.2s ease-in;
						cursor: pointer;
						color: white;
						
						&:hover {
							background-color: #FFC439;
						}

						&:active {
							background-color: #FFC439;
						}

					}
				}
				
				& .donation-option-list {
					
					& .active {
						background-color: #FFC439;
					}
				}
			}
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
				

				& .donation-amount-box {
					display: grid;
					width: 1.5rem;
					padding: 0.5rem 1.5rem;
				}

				& select {
					padding: 0.5rem 1rem;
				}

				& input {
					/* display: block; */
					padding: 0.5rem 2rem;
				}

			}
			
			& .donation-check {
				display: block;

				& .donation-source {
					margin: 1rem;

						& label {
							font-size: 1.1rem;
					}

					& .amount-box {
						font-size: 1.25rem;
					}

					& .amount {
						font-size: 1.5rem;
						margin: 0.5rem;
					}
				}

				& .donation-option {
					/* display: flex; */
					flex-direction: column;
					margin: 0;
					
					& p {
						font-size: 1.2rem;
						width: 15rem;
					}

					& ul {
						& li {
							/* width: 10rem; */
							height: 2rem;
							font-size: 1.2rem;
						}
					}
				}
			}
		}
	}
</style>
