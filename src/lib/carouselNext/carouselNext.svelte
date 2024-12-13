<script lang="ts">
	interface carouselInterface {
		// Config
		carouselDataSource: any[];
		carouselDataTextSource?: string;
		carouselDataHeaderSource?: string;
		
		sliderToggle?: boolean;
		sliderImage?: boolean;
		sliderText?: boolean;
		sliderHeading?: boolean;
		
		// Style
		
		// Function
		active: number;
		itemLength: number;
	}

	let {
		//Config
		carouselDataSource = [],
		
		sliderToggle = true,
		sliderImage = false,
		sliderText = true,
		sliderHeading = true,

		
		// Function
		itemLength = carouselDataSource.length ,
		active = 0
	}: carouselInterface = $props();

	

	/* function setActive(index: number) {
		active = index;
	} */

	const nextSlide = () => {
		active = active + 1 > itemLength ? 0 : active + 1;
	};

	const prevSlide = () => {
		active = active - 1 < 0 ? itemLength - 1 : active - 1;
	};
</script>

<main>
	<div class="carousel">
		<div class="slides" style="transform: translateX(-{active * 100}%)">
			{#each carouselDataSource as { image, heading, carouselDataHeaderSource, carouselDataTextSource, index }}
				<div class="slide" class:active={active === index}>
					{#if sliderToggle}
						
					<div class="slideText">
						{#if sliderHeading}
							<h2>{carouselDataHeaderSource}</h2>
						{/if}
						{#if sliderText}
							<p>{carouselDataTextSource}</p>
						{/if}
					</div>
					{/if}

					{#if sliderImage}
					<img src={image} alt={heading} />
					{/if}
				</div>
			{/each}
		</div>

		<button class="previous" onclick={prevSlide}> &lt; </button>

		<button class="next" onclick={nextSlide}> &gt; </button>

		<!-- <div class="indicators">
			{#each carouselDataSource as _, index}
				<div class="dot {active === index ? 'active' : ''}" onclick={() => setActive(index)}></div>
			{/each}
		</div> -->
	</div>
</main>

<style>
	main {
		& .carousel {
			position: relative;
			width: 100%;

			height: 20rem;
			overflow: hidden;

			& .slides {
				display: flex;
				transition: transform 0.5s ease;

				& .slide {
				border: #000000 solid 1px;
				width: 50px;
					min-width: 100%;
					box-sizing: border-box;
					padding: 1.25rem;
					text-align: center;

					& img {
						aspect-ratio: 1/1;
						border-radius: 0.5rem;
					}
				}
			}
		}

		& .previous,
		& .next {
			position: absolute;
			top: 50%;
			font-size: 2.5rem;
			border: none;
			border-radius: 50%;
			cursor: pointer;
			transform: translateY(-50%);
			transition: all 0.2s ease-in-out;
		}

		& .previous {
			left: 1.875rem;
		}

		& .next {
			right: 1.875rem;
		}

		/* & .previous:hover,
		& .next:hover {
			background-color: rgba(0, 0, 0, 0.8);
			color: white;
		} */

		/* & .indicators {
			position: absolute;
			display: flex;
			justify-content: space-evenly;
			width: 11%;
			bottom: 0.5rem;
			left: 50%;
			padding: 0.3125rem 0.0625rem;
			border-radius: 1.5625rem;

			opacity: 0.5;
			z-index: 10;
			transform: translateX(-50%);

			& .dot {
				display: inline-block;
				background-color: bisque;
				width: 0.625rem;
				height: 0.625rem;
				border-radius: 50%;
				margin: 0.125rem;
				cursor: pointer;
				justify-content: space-evenly;

				&.active {
					background-color: #000000;
				}
			}
		} */
	}
</style>
