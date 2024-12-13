<script lang="ts">
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

		footerTextCopyright = 'Copyright &copy; {new Date().getFullYear()} Mari_Gold',
		footerTextAllRights = 'All rights reserved',
		footerContactText = 'Get regular updated for better experience'
	}: FooterBarInterface = $props();
</script>

<section>
	<footer>
		<div class="footerBar">
			<div class="footerLogo">
				<img src={navBarLogoSource} alt="logo" class="logo" />
				<span class="logoText">{navBarLogoTextSource}</span>
			</div>
			<p class="footerCopyrightText">{footerTextCopyright}</p>
			<p class="footerCopyrightText">{footerTextAllRights}</p>
			<div class="footerContact">
				<p>{footerContactText}</p>
				<div class="footerEmail">
					<input type="email" placeholder="Email address" class="footerEmailInput" />
					<button type="submit" class="footerEmailButton">✈</button>
				</div>
			</div>
		</div>
	</footer>
</section>

<style>
	section {
		& footer {
			padding: 0.625rem 0;
			width: 100%;

			& .footerBar {
				display: flex;
				justify-content: space-between;
				flex-wrap: wrap;

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
					color: var(--white-500);
					text-align: left;
					flex-basis: 100%;
					order: 3;
				}

				& .footerContact {
					align-items: center;
					justify-content: center;
					margin-right: 20px;
					text-align: right;
					margin-top: 14px;

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
							border-radius: 5px;
							box-shadow: 0.125rem 0.125rem 0.3125rem rgba(0, 0, 0, 0.5);
							margin-right: 0.5rem;
						}

						& .footerEmailButton {
							padding: 0.5rem;
							border: none;
							border-radius: 5px;
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
			}
		}
	}
</style>
