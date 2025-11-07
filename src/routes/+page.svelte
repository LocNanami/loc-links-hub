<script lang="ts">
	import { faBluesky, faXTwitter, faYoutube } from '@fortawesome/free-brands-svg-icons';
	import { type IconDefinition } from '@fortawesome/free-regular-svg-icons';
	import Fa from 'svelte-fa';
	import Background from '../component/Background.svelte';

	interface SocialLink {
		name: string;
		url: string;
		icon: IconDefinition;
	}

	const socialLinks: SocialLink[] = [
		{ name: 'Twitter', url: 'https://twitter.com/nana_loc_', icon: faXTwitter },
		{
			name: 'YouTube',
			url: 'https://www.youtube.com/channel/UC0lKmMdlipz2z_Gj1yHsbNw',
			icon: faYoutube
		},
		// { name: 'Pokekara', url: 'https://u.pokekara.com/user/2135111424', icon: faMicrophone }
		{ name: 'Bluesky', url: 'https://bsky.app/profile/nanaloc.bsky.social', icon: faBluesky }
	];
</script>

<svelte:head>
	<title>七海ロク - SNSリンク</title>
	<link
		href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<Background />
<div class="main">
	<div class="container head">
		<div class="image">
			<img src="head-image.png" alt="Loc Nanami" />
		</div>
		<h1>Loc Nanami</h1>
	</div>
	<div class="container links">
		<p>SNS Links</p>
		<ul class="sns-links">
			{#each socialLinks as link, index}
				<li style="animation-delay: {index * 0.1}s;">
					<a href={link.url} target="_blank" rel="noopener noreferrer">
						<div class="icon">
							<Fa icon={link.icon} />
						</div>
						{link.name}
					</a>
				</li>
			{/each}
		</ul>
	</div>
</div>

<style>
	:global(body) {
		font-family: 'Chakra Petch', sans-serif;
		margin: 0;
		padding: 32px;
		min-height: 100vh;
		overflow: hidden;
		min-width: 250px;
	}

	@keyframes rotate {
		0% {
			transform: translate(-50%, 0) rotate(0deg);
		}
		100% {
			transform: translate(-50%, 0) rotate(360deg);
		}
	}

	.main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		z-index: 1;
		gap: 32px;
		max-width: 800px;
		margin: auto;
	}

	.head {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		height: 200px;
		padding-left: 300px;
		padding-right: 30px;
		min-width: 100px;
	}
	.head .image {
		position: absolute;
		top: 0;
		left: 0;
		height: 198px; /* border の分2px高さ調整してる		 */
		object-fit: contain;
		clip-path: polygon(35% 0%, 90% 0%, 65% 100%, 10% 100%);
		margin-left: -10px;
	}
	.head img {
		height: 100%;
	}
	.container {
		background: rgba(255, 255, 255, 0.1);
		backdrop-filter: blur(10px);
		box-shadow: 0 8px 32px rgba(31, 38, 135, 0.37);
		border: 1px solid rgba(255, 255, 255, 0.18);
		z-index: 1;
		color: #ffffff;
		box-sizing: border-box;
		width: 100%;
	}
	.links {
		padding: 0 32px;
		padding-bottom: 18px;
	}

	h1 {
		text-align: center;
		font-weight: 600;
		letter-spacing: 1px;
	}

	.sns-links {
		list-style-type: none;
		padding: 0;
	}

	.sns-links li {
		margin-bottom: 20px;
		animation: fadeIn 0.5s ease forwards;
		opacity: 0;
	}

	.sns-links a {
		display: flex;
		align-items: center;
		padding: 15px 20px;
		background-color: rgba(255, 255, 255, 0.1);
		color: #ffffff;
		text-decoration: none;
		border-radius: 10px;
		transition: all 0.3s ease;
		font-weight: 300;
	}

	.sns-links a:hover {
		background-color: rgba(255, 255, 255, 0.2);
		transform: translateY(-3px);
		box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
	}

	.sns-links .icon {
		display: flex;
		justify-content: center;
		margin-right: 15px;
		font-size: 24px;
		width: 32px;
		text-align: center;
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(20px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@media (max-width: 580px) {
		.head {
			padding-left: 115px;
			height: 130px;
		}
		.head .image {
			clip-path: polygon(40% 0%, 65% 0%, 55% 100%, 30% 100%);
			margin-left: -42px;
			height: 128px;
		}
	}
</style>
