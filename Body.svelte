<script>
  import BodyShadow from "./BodyShadow.svelte";
  import BodyNoise from "./BodyNoise.svelte";
  export let seed = 0;
</script>

<BodyShadow {seed} />

<g fill="white" id="body">
  <circle cy="3" r="1" />
  <circle cy="2" r="0.8" />
  <circle cy="1" r="0.6" />

  <BodyNoise />

  <g fill="var(--buttons)">
    <circle r="0.08" cy="2" />
    <circle r="0.08" cy="2.35" />
    <circle r="0.08" cy="2.7" />
  </g>
</g>

<style>
	g {
	  transition: all 0.3s ease-out;
	}
</style>