<script lang="ts">
	/* 	import '../Global.css'; */

	interface navigationBarInterface {
		// Config
		navBarLogoSource: string;
		navBarLogoTextSource: string;

		navBarMenuToggle?: boolean;
		navBarMenuSource: string;

		navBarSearchToggle?: boolean;
		navBarSearchSource?: string;

		navBarHeaderDropDown?: boolean;

		NavBarMenuButtonToggle?: boolean;
		NavBarMenuButtonSource?: string;

		NavBarMenuIconToggle?: boolean;
		NavBarMenuIconSource?: string;

		navBarMenuIconText?: string;

		// Style
	}

	let {
		//Config
		navBarLogoSource = 'https://anibase.net/files/200e4fbbc54f6ffdb2565919c2fa354d',
		navBarLogoTextSource = 'Mari_Gold',

		navBarMenuToggle = undefined,
		navBarMenuSource = '',

		navBarSearchToggle = undefined,
		navBarSearchSource = '',

		navBarHeaderDropDown = true,

		NavBarMenuButtonToggle = undefined,
		NavBarMenuButtonSource = '',

		NavBarMenuIconToggle = undefined,
		NavBarMenuIconSource = '',

		navBarMenuIconText = 'GitHub'
	}: navigationBarInterface = $props();

	// Function

	let activeNavMenu = $state('activeNavMenu');

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
				{#if navBarSearchToggle}
					<div class="headerSearch">
						<input type="text" class="searchBox" placeholder={navBarSearchSource} />
					</div>
					<hr />
				{/if}

				<nav class="navbarMenu">
					<a
						href="/"
						onclick={() => setActive(navBarMenuSource)}
						class="navItem {activeNavMenu === navBarMenuSource ? 'active' : ''}"
						>{navBarMenuSource}</a
					>
				</nav>
			</div>

			<div class="headerMenu">
				{#if navBarHeaderDropDown}
					<div class="dropDown">
						<input type="checkbox" class="combo-box" id="combo-box" />
						<label for="combo-box">Version</label>

						<div class="dropdown-content">
							<ul>
								<li>option 1</li>
								<li>option 2</li>
								<li>option 3</li>
								<li>option 4</li>
							</ul>
						</div>
					</div>
				{/if}

				{#if NavBarMenuButtonToggle}
					<button class="headerMenuButton">
						<span>
							<svg
								width="15"
								height="15"
								viewBox="0 0 20 20"
								fill="none"
								xmlns="http://www.w3.org/2000/svg"
							>
								<path
									d="M11.3462 2.59615C11.3462 1.85156 10.7446 1.25 10 1.25C9.25541 1.25 8.65385 1.85156 8.65385 2.59615V8.65385H2.59615C1.85156 8.65385 1.25 9.25541 1.25 10C1.25 10.7446 1.85156 11.3462 2.59615 11.3462H8.65385V17.4038C8.65385 18.1484 9.25541 18.75 10 18.75C10.7446 18.75 11.3462 18.1484 11.3462 17.4038V11.3462H17.4038C18.1484 11.3462 18.75 10.7446 18.75 10C18.75 9.25541 18.1484 8.65385 17.4038 8.65385H11.3462V2.59615Z"
									fill="black"
								/>
							</svg>
						</span>
						{NavBarMenuButtonSource}
					</button>
				{/if}
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
			position: relative;
			display: flex;
			align-items: center;
			justify-content: space-between;
			background-color: rgba(250, 249, 253, 1);
			box-shadow: 0.1875rem 0.1875rem 0.3125rem rgba(0, 0, 0, 0.1);
			width: 100%;
			box-sizing: border-box;

			& .headerSectionDiv .headerSearch {
				width: 100%;
			}

			& .headerLogo {
				display: flex;
				align-items: center;

				& .logo {
					height: 4.2rem;
					margin-right: 0.5rem;
				}

				& .logoText {
					font-size: 1.5rem;
					font-weight: bold;
				}
			}

			& .headerSearch {
				flex: 1;
				display: flex;
				justify-content: center;
				width: 100%;

				& .searchBox {
					width: 100%;
					max-width: 35rem;
					box-shadow: 0.0625rem 0.0625rem 0.125rem rgba(0, 0, 0, 0.25);
					padding: 0.5rem 0.75rem;
					border: 0.0625rem solid rgba(250, 249, 253, 1);
					border-radius: 0.625rem;
					font-size: 0.875rem;
					outline: none;
				}
			}

			& .headerMenu {
				display: flex;
				align-items: center;

				& .headerMenuButton {
					display: flex;
					align-items: center;
					padding: 0.3rem 1rem;
					border: none;
					border-radius: 1.25rem;
					color: black;
					font-size: 1rem;
					font-weight: bold;
					margin-right: 0.6rem;
					cursor: pointer;
					box-shadow: 0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5);
					transition:
						transform 0.2s ease,
						box-shadow 0.2s ease;

					&:active {
						transform: translateY(0.125rem);
						box-shadow: 0.0625rem 0.0625rem 0.3125rem rgba(0, 0, 0, 0.3);
					}

					& span {
						margin-right: 0.5rem;
					}
				}

				& .MenuIcon {
					height: 2rem;
					cursor: pointer;

					/* width: 3rem;
					margin-right: 1rem;
					border-radius: 50%;
					box-shadow: 0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5);
					transition:
						transform 0.2s ease,
						box-shadow 0.2s ease;

					&:active {
						transform: translateY(0.125rem);
						box-shadow: 0.0625rem 0.0625rem 0.3125rem rgba(0, 0, 0, 0.3);
					} */
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
						transform: rotate(0deg);
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
							}
						}
					}

					#combo-box:checked + label + .dropdown-content {
						display: block;
					}
				}
			}
		}

		& .navbarMenu {
			background-color: rgba(250, 249, 253, 1);
			padding: 0.625rem 0;
			width: 100%;
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
</style>
