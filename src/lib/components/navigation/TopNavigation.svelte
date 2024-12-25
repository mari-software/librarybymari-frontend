<script lang="ts">
	import { fly, slide } from 'svelte/transition';
	import SVG from './1203966 1.svg';

	interface navigationBarInterface {
		// Config
		navBarLogoSource: string;
		navBarLogoTextSource: string;

		navBarMenuToggle?: boolean;
		navBarMenuSource: any[];

		navBarHeaderDropDown?: boolean;

		NavBarMenuIconToggle?: boolean;
		NavBarMenuIconSource?: string;

		navBarMenuIconText?: string;

		sideBarToogle?: boolean;

		dropDown?: boolean;
		dropDownSource?: any[];

		// Style
	}

	let {
		//Config
		navBarLogoSource = 'https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d',
		navBarLogoTextSource = 'Mari_Gold',

		navBarMenuToggle = undefined,
		navBarMenuSource = [],

		navBarHeaderDropDown = true,

		NavBarMenuIconToggle = undefined,
		NavBarMenuIconSource = '',

		navBarMenuIconText = 'GitHub',

		sideBarToogle = false,

		dropDownSource = []
	}: navigationBarInterface = $props();

	// Function

	let activeNavMenu = $state('activeNavMenu');

	activeNavMenu = navBarMenuSource.length > 0 ? navBarMenuSource[0].options : '';

	function toggleSideBar() {
		sideBarToogle = !sideBarToogle;
	}

	function setActive(selectedNavMenu: string) {
		activeNavMenu = selectedNavMenu;
	}
</script>

<main>
	<header class="headerNav">
		<div class="headerLogo">
			<img src={navBarLogoSource} alt="logo" class="logo" />
			<span class="logoText">{navBarLogoTextSource}</span>
		</div>
		{#if navBarMenuToggle}
			<div class="headerSectionDiv">
				<nav class="navbarMenu">
					{#each navBarMenuSource as { options, link }}
						<a
							href={link}
							onclick={() => setActive(options)}
							class="navItem {activeNavMenu === options ? 'active' : ''}">{options}</a
						>
					{/each}
				</nav>
				{#if sideBarToogle}
					<div class="sideBarMenu" transition:fly={{ x: 300, duration: 500 }}>
						<!-- svelte-ignore a11y_click_events_have_key_events -->
						<!-- svelte-ignore a11y_no_static_element_interactions -->
						<div class="crossIcon" onclick={toggleSideBar}>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								height="24px"
								viewBox="0 -960 960 960"
								width="24px"
								fill="black"
							>
								<path
									d="m256-200-56-56 224-224-224-224 56-56 224 224 224-224 56 56-224 224 224 224-56 56-224-224-224 224Z"
								/></svg
							>
						</div>
						{#each navBarMenuSource as { options, link }}
							<li>
								<a
									href={link}
									onclick={() => setActive(options)}
									class="navItem {activeNavMenu === options ? 'active' : ''}">{options}</a
								>
							</li>
						{/each}
					</div>
				{/if}
			</div>
			<!-- svelte-ignore a11y_click_events_have_key_events -->
			<!-- svelte-ignore a11y_no_static_element_interactions -->

			<div class="sideMenuIcon" onclick={toggleSideBar}>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					height="24px"
					viewBox="0 -960 960 960"
					width="24px"
					fill="black"
					><path d="M120-240v-80h720v80H120Zm0-200v-80h720v80H120Zm0-200v-80h720v80H120Z" /></svg
				>
			</div>

			<div class="headerMenu">
				{#if navBarHeaderDropDown}
					<div class="dropDown" >
						<input type="checkbox" class="combo-box" id="combo-box" />
						<label for="combo-box">Version</label>

						<div class="dropdown-content"  transition:slide|globalThis>
							{#each dropDownSource as { options, link }}
								<ul>
									<li><a href={link}>{options}</a></li>
								</ul>
							{/each}
						</div>
					</div>
				{/if}

				<div class="navBarIcon">
					<img src={SVG} alt="" />
				</div>

				{#if NavBarMenuIconToggle}
					<img src={NavBarMenuIconSource} alt="" class="MenuIcon" />
				{/if}
				<p>{navBarMenuIconText}</p>
			</div>
		{/if}
	</header>
</main>

<style>
	main {
		& .headerNav {
			position: fixed;
			z-index: 999;
			display: flex;
			align-items: center;
			justify-content: space-between;
			background-color: rgb(250, 249, 253);
			box-shadow: 0.1875rem 0.1875rem 0.3125rem rgba(0, 0, 0, 0.1);
			width: 100%;

			& .headerLogo {
				display: flex;
				align-items: center;
				overflow: hidden;

				& .logo {
					height: 4.2rem;
					margin-left: 1.5rem;
					transition: all 0.3s ease-in-out;

					&:hover {
						transform: scale(1.2);
					}
				}

				& .logoText {
					font-size: 1.5rem;
					font-weight: bold;
				}
			}

			& .sideMenuIcon {
				position: absolute;
				display: none;
				cursor: pointer;
			}
			& .headerMenu {
				display: flex;
				align-items: center;

				& .MenuIcon {
					height: 2rem;
					cursor: pointer;
				}

				& p {
					font-size: 1.25rem;
					font-weight: bold;
					cursor: pointer;
					margin-right: 1rem;
				}

				.dropDown {
					position: relative;
					display: inline-block;

					#combo-box {
						display: none;
					}

					label {
						color: black;
						padding: 0.625rem 1.25rem;
						font-size: 1rem;
						cursor: pointer;
						display: inline-block;

						&::before {
							content: '∇';
							display: inline-block;
							font-weight: 900;
							font-size: larger;
							margin-right: 0.5rem;
							transform: rotate(-90deg);
							transition: transform 0.2s ease;
						}
					}
					#combo-box:checked + label::before {
						transform: rotate(360deg);
					}

					.dropdown-content {
						display: none;
						position: absolute;
						background-color: #f9f9f9;
						min-width: 10rem;
						box-shadow: 0rem 0.5rem 1rem 0rem rgba(0, 0, 0, 0.2);

						z-index: 1;
						overflow-y: scroll;
						max-height: 8.5rem;

						ul {
							list-style: none;
							padding: 0;
							margin: 0;

							li {
								padding: 0.75rem 1rem;
								cursor: pointer;

								&:hover {
									background-color: #f1f1f1;
								}

								a {
									text-decoration: none;
									color: black;
									font-size: 1rem;
								}
							}
						}
					}

					#combo-box:checked + label + .dropdown-content {
						display: block;
					}
				}
			}

			& .navBarIcon {
				margin: 0 1.5rem;
			}
		}

		& .navbarMenu {
			background-color: rgba(250, 249, 253, 1);
			padding: 0.625rem 0;
			width: 100%;
		}

		& .sideBarMenu {
			position: fixed;
			top: 0;
			right: 0;
			height: 100vh;
			width: 15.625rem;
			z-index: 99;
			background-color: white;
			backdrop-filter: blur(0.625rem);
			box-shadow: -0.625rem 0 0.625rem rgba(0, 0, 0, 0.1);
			flex-direction: column;
			align-items: flex-start;
			justify-content: flex-start;

			& .crossIcon {
				margin: 0.9375rem 0 0 0.75rem;
				cursor: pointer;
			}

			& li {
				list-style: none;
				width: 100%;
				text-align: left;
				margin: 0.5rem 0;
				padding: 0.5rem 1rem;
				cursor: pointer;
				color: black;

				&:hover {
					background-color: rgba(0, 0, 0, 0.1);
				}
			}
		}

		& .navItem {
			text-decoration: none;
			font-size: 1.1rem;
			justify-content: space-evenly;
			font-weight: 500;
			color: rgba(102, 102, 102, 1);
			margin: 0 1.25rem;

			&.active {
				color: rgba(0, 0, 0, 1);
			}
		}
	}

	@media (max-width: 768px) {
		main {
			& .headerNav {
				& .sideMenuIcon {
					right: 4rem;
					display: block;
					cursor: pointer;
				}
				& .headerMenu {
					& p {
						display: none;
					}

					& .dropDown {
						display: none;
					}
				}
			}

			& .navbarMenu {
				display: none;
			}
			& .navBarIcon {
				display: none;
			}
		}
	}
</style>
