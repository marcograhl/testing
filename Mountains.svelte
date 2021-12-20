<script>
  import * as d3 from "d3-scale";
  export let random;

  const colorScale = d3
    .scaleLinear()
    .domain([0, 16])
    .range(["#bEdAe3", "#8DACAD"]);
</script>

<g transform="translate(0, 3.3)">
  {#each new Array(6) as _,i}
    <path d={[
        "M", random(-5,0), 0,
        "q", random(1, 3), random(-4, -0.5),
             random(2.5, 6), 0,
        "z"
      ].join(" ")}
      fill={colorScale(i)}
    />
  {/each}
</g>

<style>
	path {
	  transition: all 0.3s ease-out;
	}
</style>