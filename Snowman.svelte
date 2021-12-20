<script>
	import seedrandom from "seedrandom";
	import Face from "./Face.svelte";
	import Body from "./Body.svelte";
	import Scarf from "./Scarf.svelte";
	import Arms from "./Arms.svelte";
	import ClickMeText from "./ClickMeText.svelte";
	import Mountains from "./Mountains.svelte";

	export let seed = 0;

	$: seededRandom = seedrandom(seed);
	$: random = (min, max, decimals = 2) =>
	  (min + seededRandom() * (max - min)).toFixed(decimals);
</script>

<svg width="10em" viewBox="-1 0 2 5" style="overflow: visible">
	<defs>
		<pattern id="snow" viewBox="-1.5 -1 3 2" width="100%" height="50%" patternUnits="userSpaceOnUse">
			<g fill="white" class="snow">
				{#each new Array(10) as _,i}
					<circle
						cx={random(-1,1)}
						cy={random(-5,1)}
						r="0.1"
					/>
				{/each}
			</g>
		</pattern>
	</defs>

	<!-- background -->
	<Mountains {random} />
	<rect x="-10" y="3.2" width="20" height="20" fill="white" />

	<circle cy="1.5" r="4" fill="url(#snow)"
		opacity="0.5"
  />
	
	<g id="snowman">
		<Arms  {seed} {random} />
		<Body  {seed} {random} />
		<Scarf {seed} {random} />
		<Face  {seed} {random} />
	</g>

	<circle cy="1.5" r="2.3" fill="url(#snow)"
		style="mix-blend-mode: overlay"
  />

	<ClickMeText />
</svg>

<style>
	svg {
	  --sticks: #685258;
	  --eyes: black;
	  --buttons: black;
	  --cheeks: pink;
	  --carrot: orange;
	}
	@keyframes fall {
	  0% {
	    transform: translate(0px, 0px);
	  }
	  50% {
	    transform: translate(1px, 1px);
	  }
	  100% {
	    transform: translate(0px, 2px);
	  }
	}
	.snow {
	  animation: fall 12s linear infinite;
	}
	circle {
	  transition: all 0.3s ease-out;
	}
</style>