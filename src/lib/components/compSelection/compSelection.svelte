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
					<img src={cardImage}  alt="" />
					<h1>{cardTitle}</h1>
					<p>{cardDescription}</p>
				</div>
			</a>
		{/each}

	
		
	</div>
</main>

<style>
	main {
	
		& .component {
			display: flex;
			flex-wrap: wrap;

			& a {
				text-decoration: none;
				color: var(--black-900);
			}

			& .component-card {
				display: inline-block;
				width: 20rem;
				
			/* 	height: fit-content; */
				justify-content: center;
				align-items: center;
				border: 1px solid #ccc;
				margin: 2rem;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;

				& img {
					aspect-ratio: 1/1;
					width: 100%;
					height: 15rem;
					border-radius: inherit;
				}

				& h1 {
					text-align: center;
				}

				& p {
					text-align: center;
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
</style>
