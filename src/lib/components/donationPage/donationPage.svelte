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
		<div class="donation-amount-box active">$10</div>
        <div class="donation-amount-box">$25</div>
		<div class="donation-amount-box">$50</div>
		<div class="donation-amount-box">$100</div>

		<div class="donation-option-box">
			<input type="checkbox" class="donation-box" id="donation-box" />
			<label for="donation-box"></label>

			<div class="donation-options">
				<ul>
					<li><a href="/">options</a></li>
				</ul>
			</div>
			<input type="text" placeholder="Type the amount..." />
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
			margin: 2rem;

			& .donation-amount-box {
				display: flex;
				align-items: center;
				justify-content: center;
				margin: 0.5rem;
				padding: 0rem 2.5rem;
				border: 1px solid #ccc;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;

			}
            & .active {
                background-color: #005bba;
                color: white;
            }

			& .donation-amount-box:hover {
				border: 2px solid #005bba;
				color: #005bba;
			}

            & .donation-amount-box:active {
                background-color: #005bba;
                color: white;
            }

			& .donation-option-box {
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: center;
				margin: 0.5rem;
				border: 1px solid #ccc;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;
			}
		}
	}
</style>
