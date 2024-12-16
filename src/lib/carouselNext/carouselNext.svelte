<script lang="ts">
	interface carouselInterface {
		// Config

		carouselOptionMenu: string;
		carouselMoreMenu: string;
		carouselMoreMenuLink: string;

		carouselDataSource: any[];
		carouselDataTextSource?: string;
		carouselDataHeaderSource?: string;

		sliderToggle?: boolean;
		sliderImage?: boolean;
		sliderTextToggle?: boolean;
		sliderHeading?: boolean;

		// Style

		// Function
		active: number;
		itemLength: number;
	}

	let {
		//Config

		carouselOptionMenu = '',
		carouselMoreMenu = '',
		carouselMoreMenuLink = '',

		carouselDataSource = [],

		sliderToggle = true,
		sliderImage = true,
		sliderTextToggle = true,
		sliderHeading = true

		// Function
	}: carouselInterface = $props();

	let active = $state(0);
	let itemLength = carouselDataSource.length;
	// Funtion
	const nextSlide = () => {
		active = active + 1 > itemLength ? 0 : active + 1;
	};

	const prevSlide = () => {
		active = active - 1 < 0 ? itemLength : active - 1;
	};
</script>

<main>
	<div class="carouselMenu">
		<h1>{carouselOptionMenu}</h1>
		<a href={carouselMoreMenuLink}
			><p>
				{carouselMoreMenu}
				<svg
					width="15"
					height="15"
					viewBox="0 0 15 15"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M10.9754 8.16189C11.3415 7.7958 11.3415 7.20127 10.9754 6.83518L5.35149 1.21207C4.98535 0.845978 4.39074 0.845978 4.0246 1.21207C3.65847 1.57815 3.65847 2.17268 4.0246 2.53877L8.98653 7.5L4.02753 12.4612C3.66139 12.8273 3.66139 13.4218 4.02753 13.7879C4.39367 14.154 4.98828 14.154 5.35442 13.7879L10.9783 8.16482L10.9754 8.16189Z"
						fill="black"
					/>
				</svg>
			</p></a
		>
	</div>
	<div class="carousel">
		<div class="slides">
			{#each carouselDataSource as { image, heading, carouselDataHeaderSource, carouselDataTextSource, index, link }}
				<div
					class="slide"
					style="transform: translateX({-active * 50}%)"
					class:active={active === index}
				>
					{#if sliderImage}
						<img src={image} alt={heading} />
					{/if}
					{#if sliderToggle}
						<a href={link}
							><div class="slideText">
								{#if sliderHeading}
									<h2>{carouselDataHeaderSource}</h2>
								{/if}
								{#if sliderTextToggle}
									<p>{carouselDataTextSource}</p>
								{/if}
							</div></a
						>
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
	</div>
</main>

<style>
	main {
		& .carouselMenu {
			display: flex;
			justify-content: space-between;
			margin-bottom: 1rem;

			& h1 {
				margin-left: 2rem;
			}

			& a {
				text-decoration: none;
				color: var(--black-900);
				transition: text-decoration 0.2s ease-in-out;

				&:hover {
					text-decoration: underline;
				}

				p {
					display: flex;
					justify-content: center;
					align-items: center;
					margin-right: 1.5rem;

					& svg {
						margin-left: 0.7rem;
					}
				}
			}
		}

		& .carousel {
			display: flex;
			position: relative;
			justify-content: center;
			align-items: center;
			/* width: 100%;
			height: 100%; */

			& .slides {
				display: flex;
				overflow-x: scroll;
				overflow-y: hidden;
				scroll-snap-type: x mandatory;
				scroll-behavior: smooth;
				scrollbar-width: none;

				&::-webkit-scrollbar {
					display: none;
				}

				& .slide {
					border: 1px solid rgba(0, 0, 0, 0.5);
					border-radius: 25px;
					min-width: 33%;
					box-sizing: border-box;
					overflow: hidden;
					text-align: center;
					width: 15rem;
					height: 15rem;
					cursor: pointer;
					margin-right: 2rem;
					cursor: pointer;
					transition: all 0.2s ease-in-out;

					&:hover {
						scale: 1.1;
					}

					&:active {
						scale: 0.99;
					}

					& a {
						text-decoration: none;
						color: var(--black-900);
					}

					& img {
						margin-top: 1.75rem;
						width: 5rem;
						height: 5rem;
						overflow: hidden;
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
	}

	@media screen and (max-width: 768px) {
		main {
			& .carousel {
				& .slides {
					& .slide {
						min-width: 100%;
						width: 10rem;
						height: 15rem;
					}
				}
			}
		}
	}
</style>
