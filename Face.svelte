<script>
  export let random;
</script>

<g transform="translate(0, 1)">
  <g id="face--right">
    <circle cx="0.26" cy="-0.1" r="0.08" fill="var(--eyes)" />
    <circle cx={random(0.15,0.33)} cy={random(0.04,0.042)} r={random(0.08,0.12)} fill="white" />
    <circle cx="0.37" cy="0.1" r="0.12" fill="var(--cheeks)" />
    <circle cx="0.27" cy="-0.133" r="0.02" fill="white" />
    <path
      id="mouth"
      d={[
        "M 0,0.25",
        ["c", 0.3,0, 0.35,random(-0.3,0.2), 0.225,random(0,0.12)].join(" "),
        ["c",-0.1,0.1,-0.2,0.1, -0.225,0.1].join(" "),
      ].join(" ")}
      stroke-width="0.1"
      stroke="black"
    />
    <circle cy={random(0.45,0.6)} r={random(0.1,0.25)} fill="pink" clip-path="url(#mouth-clip)" />
  </g>
  <clipPath id="mouth-clip">
    <use href="#mouth" />
  </clipPath>

  <!-- https://developer.mozilla.org/en-US/docs/Web/SVG/Element/use -->
  <use href="#face--right" transform="scale(-1 1)" />
  <path
    fill="var(--carrot)"
    stroke="var(--carrot)"
    stroke-width="0.1"
    stroke-linejoin="round"
    d="M 0,0 L {random(-0.5,0.5)},0.05 L 0,0.1 Z"
    transform="rotate({random(-10,10)})"
  />
</g>

<style>
		circle,
		path {
		  transition: all 0.3s ease-out;
		}
</style>