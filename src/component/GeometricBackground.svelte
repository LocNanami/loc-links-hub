<div class="geometric-bg">
	{#each Array(80) as _, i}
		<div
			class="square"
			style="
				top: {Math.random() * 100}%;
				left: {Math.random() * 100}%;
				width: {100 + Math.random() * 30}px;
				height: {100 + Math.random() * 30}px;
				opacity: {0.1 + Math.random() * 0.3};
				animation-duration: {5 + Math.random() * 10}s;
				animation-delay: -{Math.random() * 20}s;
			"
		></div>
	{/each}
</div>

<style>
	.geometric-bg {
		position: fixed;
		width: 100vw;
		height: 100vh;
	}
	.square {
		position: absolute;
		background: rgba(255, 255, 255, 0.5);
		animation: move-squares linear infinite;
	}

	@keyframes move-squares {
		0% {
			transform: translateX(-100vw);
		}
		100% {
			transform: translateX(100vw);
		}
	}
</style>
