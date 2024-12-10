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

		NavBarMenuButtonToggle?: boolean;
		NavBarMenuButtonSource?: string;

		NavBarMenuIconToggle?: boolean;
		NavBarMenuIconSource?: string;

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

		NavBarMenuButtonToggle = undefined,
		NavBarMenuButtonSource = '',

		NavBarMenuIconToggle = undefined,
		NavBarMenuIconSource = ''
	}: navigationBarInterface = $props();

	// Function

	let activeNavMenu = null;

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
					<a href="/Dashboard" onclick={() => setActive(navBarMenuSource)} class="navItem active"
						>{navBarMenuSource}</a
					>
				</nav>
			</div>

			<div class="headerMenu">
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
			</div>
		{/if}
	</header>
	<!-- <div class="main-entrance">
		<h1>Mari Gold</h1>
		<p>Build your ideas faster</p>
		<button>See more</button>
	</div>

	<footer>
		<div class="footerBar">
			<div class="footerLogo">
				<img src={navBarLogoSource} alt="logo" class="logo" />
				<span class="logoText">{navBarLogoTextSource}</span>
			</div>
			<p class="footerCopyrightText">Copyright &copy; {new Date().getFullYear()} Mari_Gold</p>
      <p class="footerCopyrightText">All rights reserved</p>
			<div class="footerContact">
				<p>Get regular updated for better experience</p>
				<div class="footerEmail">
					<input type="email" placeholder="Email address" class="footerEmailInput" />
					<button type="submit" class="footerEmailButton">✈</button>
				</div>
			</div>
		</div>
	</footer> -->
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
				max-width: 200%;
				width: 100%;
			}

			& .headerLogo {
				display: flex;
				align-items: center;

				& .logo {
					height: 4.6875rem;
					margin-right: 0.5rem;
				}

				& .logoText {
					font-size: 1.5625rem;
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
					padding: 0.3125rem 1.25rem;
					border: none;
					border-radius: 1.25rem;
					color: black;
					font-size: 1.25rem;
					font-weight: bold;
					margin-right: 0.625rem;
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
						margin-right: 0.9375rem;
					}
				}

				& .MenuIcon {
					height: 2.5rem;
					width: 2.5rem;
					border-radius: 50%;
					margin-right: 1rem;
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

		& .navbarMenu {
			background-color: rgba(250, 249, 253, 1);
			padding: 0.625rem 0;
			width: 100%;
		}

		& .navItem {
			text-decoration: none;
			font-size: 1.25rem;
			justify-content: space-evenly;
			font-weight: 500;
			color: rgba(102, 102, 102, 1);
			margin: 0 1.25rem;

			&.active {
				color: rgba(0, 0, 0, 1);
			}
		}}
        </style>