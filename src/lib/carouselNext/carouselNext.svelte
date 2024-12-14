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
		itemLength = carouselDataSource.length,
		active = 0
	}: carouselInterface = $props();

	// Funtion

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
		<div class="slides" style="transform: translateX({-active * 50}%)">
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

		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="previous" onclick={prevSlide}>
			<svg
				width="38"
				height="38"
				viewBox="0 0 77 77"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g clip-path="url(#clip0_189_892)">
					<path
						opacity="0"
						d="M77 38.5C77 48.7108 72.9438 58.5035 65.7236 65.7236C58.5035 72.9438 48.7108 77 38.5 77C28.2892 77 18.4965 72.9438 11.2764 65.7236C4.05624 58.5035 0 48.7108 0 38.5C-3.68225e-07 33.4441 0.995832 28.4377 2.93064 23.7667C4.86544 19.0957 7.70133 14.8514 11.2764 11.2764C14.8514 7.70133 19.0957 4.86544 23.7667 2.93064C28.4377 0.995832 33.4441 0 38.5 0C43.5559 0 48.5623 0.995832 53.2333 2.93064C57.9043 4.86544 62.1486 7.70133 65.7236 11.2764C69.2987 14.8514 72.1346 19.0957 74.0694 23.7667C76.0042 28.4377 77 33.4441 77 38.5Z"
						fill="black"
					/>
					<path
						d="M46.0654 63.1633L20.2219 41.5639C20.2219 41.5639 18.043 39.0819 20.2598 36.2777C22.4766 33.4736 45.643 15.2757 46.9827 13.9896C48.3225 12.7034 55.6107 13.4001 52.6633 19.7237L30.4771 38.8016L52.7168 57.7724C52.7168 57.7724 54.647 65.3079 46.0654 63.1633Z"
						fill="black"
					/>
				</g>
				<defs>
					<clipPath id="clip0_189_892">
						<rect width="77" height="77" fill="white" />
					</clipPath>
				</defs>
			</svg>
		</div>

		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<div class="next" onclick={nextSlide}>
			<svg
				width="38"
				height="38"
				viewBox="0 0 77 77"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<g clip-path="url(#clip0_189_892)">
					<path
						opacity="0"
						d="M77 38.5C77 48.7108 72.9438 58.5035 65.7236 65.7236C58.5035 72.9438 48.7108 77 38.5 77C28.2892 77 18.4965 72.9438 11.2764 65.7236C4.05624 58.5035 0 48.7108 0 38.5C-3.68225e-07 33.4441 0.995832 28.4377 2.93064 23.7667C4.86544 19.0957 7.70133 14.8514 11.2764 11.2764C14.8514 7.70133 19.0957 4.86544 23.7667 2.93064C28.4377 0.995832 33.4441 0 38.5 0C43.5559 0 48.5623 0.995832 53.2333 2.93064C57.9043 4.86544 62.1486 7.70133 65.7236 11.2764C69.2987 14.8514 72.1346 19.0957 74.0694 23.7667C76.0042 28.4377 77 33.4441 77 38.5Z"
						fill="black"
					/>
					<path
						d="M46.0654 63.1633L20.2219 41.5639C20.2219 41.5639 18.043 39.0819 20.2598 36.2777C22.4766 33.4736 45.643 15.2757 46.9827 13.9896C48.3225 12.7034 55.6107 13.4001 52.6633 19.7237L30.4771 38.8016L52.7168 57.7724C52.7168 57.7724 54.647 65.3079 46.0654 63.1633Z"
						fill="black"
					/>
				</g>
				<defs>
					<clipPath id="clip0_189_892">
						<rect width="77" height="77" fill="white" />
					</clipPath>
				</defs>
			</svg>
		</div>

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
			overflow-x: scroll;
			position: relative;
			width: 100%;
			height: 20rem;
			overflow-y: hidden;
			scroll-behavior: smooth;
			scroll-snap-type: x mandatory;

			&::-webkit-scrollbar {
				display: none;
			}

			
			
			& .slides {
				display: flex;
				transition: all 0.5s ease;

				& .slide {
					display: inline-block;
					/* border: #000000 solid 1px;
					width: 50px; */
					min-width: 50%;
					box-sizing: border-box;
					padding: 1.25rem;
					overflow: hidden;
					text-align: center;
					width: 100%;
  height: 20rem;
					transition: all 0.2s ease-in-out;
					scroll-snap-align: start;

					&:last-child {
						scroll-snap-align: end;
					}

					&.active {
						transform: scale(1.05);
						z-index: 100;
					}

					&:hover {
						transform: scale(1.05);
					}

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
			border: none;
			border-radius: 50%;
			cursor: pointer;
			/* z-index: 99; */
			transform: translateY(-50%);
			transition: all 0.2s ease-in-out;
		}

		& .previous {
			left: 1.875rem;
		}

		& .next {
			right: 1.875rem;
			transform: translateY(-50%) rotate(180deg);
		}

		/* 	& .previous:hover,
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
