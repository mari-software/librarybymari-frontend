<script lang="ts">
	interface entranceInterface {
		// Config
		mainEntranceSource: string;
		mainEntranceText: string;
		mainEntranceButton: string;
	}

	let {
		//Config
		mainEntranceSource = '',
		mainEntranceText = '',
		mainEntranceButton = ''
	}: entranceInterface = $props();
</script>

<section>
	<div class="main-entrance">
		<h1>{mainEntranceSource}</h1>
		<p>{mainEntranceText}</p>
		<button>{mainEntranceButton}</button>
	</div>
</section>

<style>
	section {
		& .main-entrance {
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			height: 20rem;
			background-color: var(--primary-color-variants-100);
			padding: 5px;

			& h1 {
				font-size: var(--font-title-size);
				margin-bottom: 10px;
			}

			& button {
				margin-bottom: 10px;
				font-weight: var(--font-heavy-weight);
				border: none;
				border-radius: 25px;
				padding: 5px 20px;
				font-size: var(--font-small-size);
				box-shadow: 0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5);
				cursor: pointer;
				transition:
					transform 0.2s ease,
					box-shadow 0.2s ease;

				&:active {
					transform: translateY(0.125rem);
					box-shadow: 0.0625rem 0.0625rem 0.3125rem rgba(0, 0, 0, 0.3);
				}
			}
		}
	}

	@media screen and (max-width: 768px) {
		section {
			& .main-entrance {
				height: 15rem;
			}
		}
	}
</style>
