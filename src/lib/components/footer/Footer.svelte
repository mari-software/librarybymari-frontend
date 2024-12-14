<script lang="ts">
	import SVG from './46076 1.svg';

	interface FooterBarInterface {
		// Config
		navBarLogoSource: string;
		navBarLogoTextSource: string;

		footerTextCopyright: string;
		footerTextAllRights: string;
		footerContactText: string;
	}

	let {
		//Config
		navBarLogoSource = '',
		navBarLogoTextSource = '',

		footerTextCopyright = '',
		footerTextAllRights = '',
		footerContactText = ''
	}: FooterBarInterface = $props();
</script>

<section>
	<footer>
		<div class="footerBar">
			<div class="footerCopyrightText">
				<div class="logoSection">
			<div class="footerLogo">
				<img src={navBarLogoSource} alt="logo" class="logo" />
				<span class="logoText">{navBarLogoTextSource}</span>
			</div>
		</div>
			<p>{footerTextCopyright}</p>
			<p>{footerTextAllRights}</p>
		</div>
			<div class="footerContact">
				<p>{footerContactText}</p>
				<div class="footerEmail">
					<input type="email" placeholder="" class="footerEmailInput" />
					<!-- <div type="submit" class="footerEmailButton">✈</div> -->
					<div class="footerEmailButton"><img src={SVG} alt="" /></div>
				</div>
			</div>
		</div>
	</footer>
</section>

<style>
	section {
		& footer {
			/* padding: 0.625rem 0; */
			width: 100%;

			& .footerBar {
				display: flex;
				justify-content: space-between;
				flex-wrap: wrap;
				align-items: center;

				& .footerLogo {
					display: flex;
					align-items: center;

					& .logo {
						height: 3rem;
						margin-left: 1rem;
					}

					& .logoText {
						margin-left: 0.5rem;
						font-size: 1.2rem;
						font-weight: bold;
					}
				}

				& .footerCopyrightText {
					margin-left: 1rem;
					text-align: center;
					color: var(--white-500);
					/* flex-basis: 100%;
					order: calc(2 - 1); */

					& .logoSection {
						display: flex;
						align-items: center;
						justify-content: center;
					}
				}

				& .footerContact {
					align-items: center;
					justify-content: center;
					margin-right: 1.25rem;
					text-align: right;

					& p {
						color: var(--black-700);
						margin-right: 0.625rem;
					}

					& .footerEmail {
						display: flex;
						align-items: center;

						& .footerEmailInput {
							padding: 0.5rem;
							border: none;
							border-radius: 0.3125rem;
							box-shadow: 0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5);
							margin-right: 0.5rem;
							outline: none;
						}

						& .footerEmailButton {
							padding: 0.5rem;
							border: none;
							border-radius: 0.3125rem;
							filter: drop-shadow(0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5));
							cursor: pointer;
							transition:
								transform 0.2s ease,
								box-shadow 0.2s ease;

							&:active {
								transform: translateY(0.125rem);
								filter: drop-shadow(0.0625rem 0.0625rem 0.3125rem rgba(0, 0, 0, 0.3));
							}
						}
					}
				}
			}
		}
	}
</style>
