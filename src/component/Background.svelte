<div class="root">
	<div class="geometric-bg"></div>
</div>

<style>
	.root {
		background: linear-gradient(-45deg, #1e3c72, #2a5298, #2980b9, #2c3e50);
		animation: gradientBG 15s ease infinite;
		background-size: 400% 400%;
		overflow: hidden;
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}
	@keyframes gradientBG {
		0% {
			background-position: 0% 50%;
		}
		50% {
			background-position: 100% 50%;
		}
		100% {
			background-position: 0% 50%;
		}
	}
	.geometric-bg {
		z-index: -1;
		opacity: 0.3;
	}
	.geometric-bg::before,
	.geometric-bg::after {
		content: '';
		position: absolute;
		width: 200vmax;
		height: 200vmax;
		top: -100vmax;
		left: 50%;
		transform: translate(-50%, 0);
		background: rgba(255, 255, 255, 0.1);
		animation: rotate 30s linear infinite;
	}
	.geometric-bg::before {
		border-radius: 37% 29% 27% 27% / 28% 25% 41% 37%;
	}
	.geometric-bg::after {
		border-radius: 26% 33% 33% 35% / 25% 15% 41% 39%;
		animation-duration: 40s;
	}

	@keyframes rotate {
		0% {
			transform: translate(-50%, 0) rotate(0deg);
		}
		100% {
			transform: translate(-50%, 0) rotate(360deg);
		}
	}
</style>
