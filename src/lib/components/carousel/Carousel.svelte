<script lang="ts">
	import Swiper from 'swiper';
	import 'swiper/css';
	import 'swiper/css/pagination';
	import 'swiper/css/navigation';
	import { onMount } from 'svelte';

	let swiper: Swiper | null = null;

	onMount(() => {
		swiper = new Swiper('.swiper', {
			direction: 'horizontal',
			loop: true,
			slidesPerView: 3,
			spaceBetween: 10,
			pagination: {
				el: '.swiper-pagination',
				type: 'bullets'
			},

			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			}
		});

		document.querySelector('.swiper-button-next')?.addEventListener('click', () => {
			swiper?.slideNext();
		});
		document.querySelector('.swiper-button-prev')?.addEventListener('click', () => {
			swiper?.slidePrev();
		});
	});

	let swiperContent = [
		{ content: 'This is the first slide' },
		{ content: 'This is the second slide' },
		{ content: 'This is the third slide' },
		{ content: 'This is the fourth slide' },
		{ content: 'This is the fifth slide' }
	];
</script>

<main>
	<div class="swiper">
		<div class="swiper-wrapper">
			<!-- <div class="swiper-slide">This is slide one from the carousel</div>
			<div class="swiper-slide">Slide 2</div>
			<div class="swiper-slide">Slide 3</div>
			<div class="swiper-slide">SLide 4</div>
			<div class="swiper-slide">Slide 5</div> -->

			{#each swiperContent as slide}
				<div class="swiper-slide">{slide.content}</div>
			{/each}
		</div>

		<div class="swiper-pagination"></div>

		<div class="swiper-button-prev"></div>
		<div class="swiper-button-next"></div>
	</div>
</main>

<style>
	main {
		display: flex;
		justify-content: center;
		align-items: center;

		& .swiper {
			width: 90%;
			position: relative;

			& .swiper-wrapper {
				width: fit-content;
				height: fit-content;
				justify-content: center;
				align-items: center;
				text-align: center;

				& .swiper-slide {
					display: flex;
					justify-content: center;
					align-items: center;
					text-align: center;
					box-sizing: border-box;
					padding: 20px;
				}
			}
		}
		& .swiper-pagination {
			position: absolute;
            display: block;
			bottom: 10px;
			left: 50%;
			transform: translateX(-50%);
			text-align: center;
			width: 10px;
            height: 10px;
			background-color: black;
		}
		& .swiper-button-next,
		& .swiper-button-prev {
			color: black;
			border-radius: 50%;
			cursor: pointer;
		}
	}
</style>
