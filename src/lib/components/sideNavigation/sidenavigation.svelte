<script lang="ts">
	interface sidenavigationInterface {
		// Config
		navBarSource: any[];
		sidenavHeaderSource?: string;
		sidenavContentSource?: string;
	}

	let {
		//Config
		navBarSource = [],
		sidenavHeaderSource = '',
		sidenavContentSource = ''
	}: sidenavigationInterface = $props();

	let sideBarToogle = $state(false);

	function toggleSideBar() {
		sideBarToogle = !sideBarToogle;
	}
</script>

<main>
	<!-- svelte-ignore a11y_click_events_have_key_events -->
	<!-- svelte-ignore a11y_no_static_element_interactions -->
	<div class="sideBarIcon" onclick={toggleSideBar}>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			height="24px"
			viewBox="0 -960 960 960"
			width="24px"
			fill="#e8eaed"
			><path
				d="M200-120q-33 0-56.5-23.5T120-200v-560q0-33 23.5-56.5T200-840h560q33 0 56.5 23.5T840-760v560q0 33-23.5 56.5T760-120H200Zm280-80h280v-560H480v560Z"
			/></svg
		>
	</div>
  {#if sideBarToogle}
	<div class="sideBar-container">
		<input type="text" placeholder="Search" />
		<div class="component-section">
			{#each navBarSource as { sidenavHeaderSource, sidenavContentSource }}
				<div class="components">
					<h1>{sidenavHeaderSource}</h1>
					<ul>
						{#each sidenavContentSource as { sidenavComponentSource, link }}
							<li><a href={link}>{sidenavComponentSource}</a></li>
						{/each}
					</ul>
				</div>
			{/each}
		</div>
	</div>
  {/if}
  <div class="components-container">
	<input type="text" placeholder="Search" />
	<div class="component-section">
		{#each navBarSource as { sidenavHeaderSource, sidenavContentSource }}
			<div class="components">
				<h1>{sidenavHeaderSource}</h1>
				<ul>
					{#each sidenavContentSource as { sidenavComponentSource, link }}
						<li><a href={link}>{sidenavComponentSource}</a></li>
					{/each}
				</ul>
			</div>
		{/each}
	</div>
</div>
</main>

<style>
	main {
		width: 100%;
		display: flex;
		& .sideBarIcon {
			display: none;
			cursor: pointer;
		}

		/* & .sideBar-container {
			display: none;
		} */

		& .sideBar-container, & .components-container  {
			border: 1px solid #000;
			overflow: hidden;
			padding: 0.625rem;
			display: flex;
			flex-direction: column;
			height: 100%;
			overflow-x: scroll;
			overflow-y: hidden;

			&::-webkit-scrollbar {
				display: none;
			}

			& input {
				width: 85%;
				padding: 0.6rem;
				border: 1px solid #ccc;
				border-radius: 0.2rem;
				margin-bottom: 0.625rem;
			}

			& .component-section {
				display: flex;
				flex-direction: column;
				overflow-y: scroll;
				height: 100%;
				max-height: 100vh;
				& .components {
					display: flex;
					flex-direction: column;
					& h1 {
						font-size: 25px;
						font-weight: bold;
						margin-bottom: -0.25rem;
					}
					& ul {
						list-style: none;
						& li {
							margin-left: -15px;
							font-size: 18px;
							cursor: pointer;
							padding-top: 0.625rem;
							&:hover {
								background-color: #f2f2f2;
							}

							& a {
								text-decoration: none;
								color: black;
							}
						}
					}
				}
			}
		}
	}

	@media screen and (max-width: 768px) {
		main {
			& .sideBarIcon {
				display: block;
			}

			& .components-container {
				display: none;
				/* overflow-x: scroll;
			overflow-y: hidden;

			&::-webkit-scrollbar {
				display: none;
			} */
			}
		}
	}
</style>
