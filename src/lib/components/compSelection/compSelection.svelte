<script lang="ts">
	interface compSelectionInterface {
		// Config

		componentSource: any[];
	}

	let {
		//Config

		componentSource = []
	}: compSelectionInterface = $props();
</script>

<main>
	<div class="component">
		{#each componentSource as { cardImage, cardTitle, cardDescription, link }}
			<a href={link}>
				<div class="component-card">
					<img src={cardImage} alt="" />
					<div class="card-text">
						<h1>{cardTitle}</h1>
						<p>{cardDescription}</p>
					</div>
				</div>
			</a>
		{/each}
	</div>
</main>

<style>
	main {
		& .component {
			/* border: 1px	solid #000; */
			display: flex;
			flex-wrap: wrap;
			overflow-y: scroll;
			height: 100vh;

			& a {
				text-decoration: none;
				color: var(--black-900);
			}

			& .component-card {
				display: inline-block;
				width: 15rem;
				height: fit-content;
				justify-content: center;
				align-items: center;
				border: 1px solid #ccc;
				margin: 2rem;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;

				& img {
					/* aspect-ratio: 3/2; */
					width: 100%;
					height: 10rem;
					border-radius: inherit;
				}

				& .card-text {
					/* padding: 1rem; */
					text-align: center;
					margin-top: -23px;
				}

				/* & h1 {
					text-align: center;
				} */

				& p {
					margin-top: -15px;
				}

				&:hover {
					transform: scale(1.1);
				}

				&:active {
					transform: scale(0.9);
				}
			}
		}
	}

	@media screen and (max-width: 768px) {
		main {
			& .component {
				height: 100vh;
				& .component-card {
					width: 8.5rem;
					height: 8rem;
					/* justify-content: center;
					align-items: center; */
					border: 1px solid #ccc;
					margin: 0.5rem;
					border-radius: 0.5rem;
					cursor: pointer;
					transition: all 0.2s ease-in-out;

					& img {
						width: 100%;
						height: 8rem;
						border-radius: inherit;
					}

					& .card-text {
						text-align: center;
						margin-top: -10px;
					}

					& h1 {
						text-align: center;
						font-size: 1.3rem;
					}

					& p {
						margin-top: -10px;
						font-size: 1rem;
					}
				}
			}
		}
	}
</style>
