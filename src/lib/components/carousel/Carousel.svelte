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
			pagination: {
				el: '.swiper-pagination'
			},
			navigation: {
				nextEl: '.swiper-button-next',
				prevEl: '.swiper-button-prev'
			}
		});
	});
</script>

<main>
	<div class="swiper">
		<div class="swiper-wrapper">
			<div class="swiper-slide"><p>This is slide one from the carousel</p></div>
			<div class="swiper-slide">Slide 2</div>
			<div class="swiper-slide">Slide 3</div>
			<div class="swiper-slide">SLide 4</div>
			<div class="swiper-slide">Slide 5</div>
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
			width: 100%;
			position: relative;

			& .swiper-wrapper {
				border: 1px solid red;
				width: fit-content;
				height: fit-content;
                justify-content: center;
                align-items: center;
                text-align: center;

				& .swiper-slide {
					padding: 20px;
				}
			}
		}
		& .swiper-pagination {
			position: absolute;
			bottom: 10px;
			left: 50%;
			transform: translateX(-50%);
			text-align: center;
			width: 100%;
            background-color: black;
		}
		& .swiper-button-next,
        & .swiper-button-prev {
			color: black;
			background: rgba(255, 255, 255, 0.5);
			border-radius: 50%;
			width: 40px;
			height: 40px;

           
            
		}
		
	}
</style>
