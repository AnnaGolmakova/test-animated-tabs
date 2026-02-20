<script lang="ts">
	import { animate } from 'motion';

	interface Props {
		isActive: boolean;
		label: string;
		onclick?: () => void;
	}

	let { isActive, label, onclick }: Props = $props();

	let svgElement: SVGSVGElement | undefined = $state();

	const bounce = {
		duration: 0.4,
		ease: smoothWaveEase
	};

	const spring = {
		type: 'spring',
		stiffness: 700,
		damping: 30
	};

	// From https://easings.net/#easeOutBounce
	function smoothWaveEase(x: number) {
		const frequency = 2;
		const decay = 3;

		return 1 - Math.pow(1 - x, decay) * Math.cos(frequency * x * Math.PI);
	}

	$effect(() => {
		if (svgElement) {
			const targetHeight = isActive ? 15 : 0;
			const transition = isActive ? bounce : spring;

			animate(svgElement, { height: targetHeight }, transition);
		}
	});
</script>

<button
	class={[isActive && 'active', 'tab']}
	type="button"
	role="tab"
	aria-selected={isActive}
	tabindex={isActive ? 0 : -1}
	{onclick}
>
	{label}
	<svg
		bind:this={svgElement}
		class="indicator"
		width="93"
		height={isActive ? 16 : 0}
		viewBox="0 0 93 15"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path
			d="M93 14.9999H0C19.2414 14.9999 28.1568 -0.126067 47.0345 0.000791219C65.9121 0.127649 71.6207 14.9999 93 14.9999Z"
			fill="currentColor"
		/>
	</svg>
</button>

<style>
	.tab {
		display: flex;
		position: relative;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		border: none;
		background-color: transparent;
		padding: 0 24px;
		height: 100%;
		color: var(--tab-default);
		font-weight: 400;
		font-size: 20px;
		letter-spacing: 0.3px;
	}

	.active {
		cursor: unset;
		color: var(--tab-active);
	}

	.indicator {
		position: absolute;
		bottom: -2px;
		margin: auto;
		color: var(--container-bg);
	}
</style>
