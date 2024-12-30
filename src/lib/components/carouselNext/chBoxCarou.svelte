<script lang="ts">
    interface chBoxCarouInterface {
        // Config


        checkboxSource: any[];
        descriptionText: string;
        descriptionButton: string;
        descriptionImage: string;

        // Function
    }

    let {
        //Config

        checkboxSource = [],
        descriptionText = 'This is a description text of this check box',
        descriptionButton = '',
        descriptionImage = ''

    }: chBoxCarouInterface = $props();
    

    let active = $state(0);
	let itemLength = checkboxSource.length;
	// Funtion
	const nextSlide = () => {
		active = active + 1 > itemLength ? 0 : active + 1;
	};

	const prevSlide = () => {
		active = active - 1 < 0 ? itemLength : active - 1;
	};

</script>

<main>
    <label class="check-box">
        {#each checkboxSource as { descriptionText, descriptionButton, descriptionImage }}
        <div class="heading-checked">
			<input type="checkbox" name="" id="" />
            <div class="dots"></div>
		</div>

         <div class="description-checked">
            <div class="description-text">
                <p>{descriptionText}</p>
                <button>{descriptionButton}</button>
            </div>
            <div class="description-image">
                <img src={descriptionImage} alt="">
            </div>
         </div>
        {/each}
    </label>
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
</main>

<style>
    main {
        & .check-box {
            border: 1px solid #ccc;
            width: fit-content;
            display: block;
            padding: 0.5rem;
            transition: all 0.2s ease-in-out;
            position: relative;

            & input[type="checkbox"] {
                border-radius: 50%;
            }

            &:hover {
                transform: scale(1.1);
            }

            &:active {
                transform: scale(1);
            }

        }
        
        & .heading-checked {
            display: flex;
            justify-content: space-between;
            border-bottom: 1px solid #ccc;
            padding: 0.5rem;

            & .dots {
                background-color: red;
                width: 0.75rem;
                height: 0.75rem;
                border-radius: 50%;
                
            }
        }

        & .description-checked {
            display: flex;
            padding: 0.5rem;
        }

        & .description-text {
            border: 1px solid #ccc;
            padding: 0.5rem;
            margin-right: 2rem;
            width: 4.5rem;

            & button {
                margin-top: 0.5rem;
                border: none;
                background-color: red;
                padding: 5px 12%;
                border-radius: 25px;
                text-align: center;
                justify-content: center;
                cursor: pointer;
            }
        }

        & .description-image {
            border: 1px solid #ccc;
            
            & img {
                width: 10rem;
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
</style>
