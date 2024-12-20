<script lang="ts">
	interface compSelectionInterface {
		// Config
	}
</script>


<main>
	<div class="component">
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				width="200"
				height="200"
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				width="200"
				height="200"
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				width="200"
				height="200"
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				width="200"
				height="200"
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		<div class="component-card">
			<img
				src="https://i.pinimg.com/originals/a0/03/4e/a0034e2ed9dc9e4e76727e4fbdb31d0c.jpg"
				width="200"
				height="200"
				alt=""
			/>
			<h1>Component-1</h1>
			<p>This component does this</p>
		</div>
		
	</div>
</main>

<style>
	main {
	
		& .component {
			display: flex;
			flex-wrap: wrap;
			& .component-card {
				display: inline-block;
				width: 20rem;
				height: 10rem;
				height: fit-content;
				justify-content: center;
				align-items: center;
				border: 1px solid #ccc;
				margin: 2rem;
				border-radius: 0.5rem;
				cursor: pointer;
				transition: all 0.2s ease-in-out;

				& img {
					width: 100%;
					height: 20rem;
					border-radius: inherit;
				}

				& h1 {
					text-align: center;
				}

				& p {
					text-align: center;
				}

				&:hover {
					transform: scale(1.1);
				}

				&:active {
					transform: scale(0.9);
				}
			}
		}
	}
</style>
