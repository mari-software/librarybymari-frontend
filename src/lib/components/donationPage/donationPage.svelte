<script lang="ts">
	interface donationPageInterface {
		// Config
		currencySource: any[];
		donationAmount: any[];

		// Function
	}

	let {
		//Config
		currencySource = [],
		donationAmount = []
	}: donationPageInterface = $props();

	// Function
	let activeCurrency = $state('activeCurrency');


	function setActive(activeCurrency: string) {
		activeCurrency = activeCurrency;
	}


</script>

<main>
	<div class="donation-intro">
		<h1>Help us do more</h1>
		<p>
			Mari_Gold is committed to providing free, high-quality components and assets to the developer
			community. Your donation will help us continue to develop new tools, improve existing ones,
			and keep our platform running smoothly.
		</p>
		<div class="quote">Every contribution, no matter how small, makes a big difference.</div>
	</div>

	<div class="donation-box">

		{#each donationAmount as  {amount}}
			<!-- svelte-ignore a11y_click_events_have_key_events -->
			<!-- svelte-ignore a11y_no_static_element_interactions -->
			<div 
			onclick={() => setActive(amount)}
			class="donation-amount-box {activeCurrency === amount ? 'active' : ''}">{amount}</div>
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
					font-size: 1.2rem;
					width: 90%;
				}

				& .quote {
					font-size: 1.25rem;
				}
			}

			& .donation-box {
				 width: 80%;
				 display: grid;
				 

				& .donation-amount-box {
					padding: 0.5rem 1.5rem;
				}

			}
		}
	}
</style>
