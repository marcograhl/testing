<script>
  export let seed = 0;
  export let random;

  // https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl()
  $: getRandomColor = () =>
    `hsl(${[
      random(0, 360, 0) + "deg",
      random(40, 70, 0) + "%",
      random(40, 70, 0) + "%"
    ]})`;
  $: numberOfColors = random(1, 6, 0);
  $: scarfColors = Array.from({ length: numberOfColors }).map(getRandomColor);
</script>


<linearGradient id="scarf" gradientTransform="rotate({random(-60,60)})">
  {#each scarfColors as color, i}
    <stop
      stop-color={color}
      offset={i*100/scarfColors.length + "%"}
    />
  {/each}
</linearGradient>
<g stroke="url(#scarf)"
  stroke-width="0.3"
  stroke-linecap="round"
  stroke-linejoin="round"
  fill="none">
  <path 
    stroke-width="0.26"
    d={[
    "M -0.6,1.43",
    "C -0.3,1.83 0.3,1.83 0.6,1.43",
    ].join(" ")}
  />
  <path 
    d={[
      `M -0.44,1.55`,
      `c`,
      `-0.5,${random(-0.3,1)}`, // CP1
      `-1.5,${random(-0.8,1)}`, // CP2
      `-2.0,${random(-0.5,1)}`  // end
    ].join(" ")}
  />
</g>
		
<style>
 path {
   transition: all 0.3s ease-out;
 }
 linearGradient,
 stop {
   transition: all 0.3s ease-out;
 }
</style>