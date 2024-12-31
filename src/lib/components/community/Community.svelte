<script lang="ts">
	interface blogInterface {
		// Config
		blogDataSource: any[];
	}

	let {
		//Config
		blogDataSource = []
	}: blogInterface = $props();
</script>

<main>
	<div class="blog-lineup">
		{#each blogDataSource as { blogImage, blogHeading, blogText }}
			<div class="lineup-item">
				<img src={blogImage} alt="" />
				<h2>{blogHeading}</h2>
				<p>{blogText}</p>
			</div>
		{/each}
	</div>
</main>

<style>
	main {
		& .blog-lineup {
			justify-content: center;
			display: flex;
			gap: 3rem;

			& .lineup-item {
				& img {
					display: block;
					margin: 0 auto;
					align-items: center;
					aspect-ratio: 1/1;
					width: 4rem;
                    cursor: pointer;
					overflow: hidden;
					transition: all 0.3s ease-in-out;

					&:hover {
						transform: scale(1.2);
					}
				}

				& h2 {
					text-align: center;
				}

				& p {
					text-align: center;
				}
			}
		}
	}

	@media only screen and (max-width: 768px) {

		main {
			& .blog-lineup {
				& .lineup-item {
					&  p {
						display: none;
					}
					& img {
						width: 3rem;
					}
				}
			}
		}
	}
</style>
