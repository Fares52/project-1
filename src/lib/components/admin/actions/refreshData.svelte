<script>
	// @ts-nocheck
	import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

	let isRotating = false;

	function rotateButton() {
		isRotating = true;
		console.log('Refresh button clicked'); // Log to check the button click

		setTimeout(() => {
			isRotating = false;
		}, 500);

		// Dispatch the refresh event
		dispatch('refresh');
	}
</script>

<button class="refreshButton" on:click={rotateButton}>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		width="20"
		height="20"
		fill="#623e2a"
		viewBox="0 0 256 256"
		class:rotate={isRotating}
	>
		<path
			d="M224,48V96a8,8,0,0,1-8,8H168a8,8,0,0,1-5.66-13.66L180.65,72a79.48,79.48,0,0,0-54.72-22.09h-.45A79.52,79.52,0,0,0,69.59,72.71,8,8,0,0,1,58.41,61.27A96,96,0,0,1,192,60.7l18.36-18.36A8,8,0,0,1,224,48ZM186.41,183.29A80,80,0,0,1,75.35,184l18.31-18.31A8,8,0,0,0,88,152H40a8,8,0,0,0-8,8v48a8,8,0,0,0,13.66,5.66L64,195.3a95.42,95.42,0,0,0,66,26.76h.53a95.36,95.36,0,0,0,67.07-27.33,8,8,0,0,0-11.18-11.44Z"
		/>
	</svg>
</button>

<style>
	.refreshButton {
		border: none;
		background-color: transparent;
		cursor: pointer;
		padding: 5px;
	}

	.rotate {
		transform: rotate(360deg);
		transition: transform 0.5s ease-in-out;
	}
</style>
