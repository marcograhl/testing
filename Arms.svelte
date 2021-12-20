<script>
  export let seed = 0;
  export let random;
</script>

<g transform="translate(0, 2)"
  stroke="var(--sticks)"
  stroke-width="0.13"
  stroke-linecap="round"
>
  <use href="#arms" stroke="black" stroke-width="0.26" />
  <g id="arms">
    <g id="arm" transform="translate(0.2, -0.1) rotate({random(-20,20)})">
      <line x1="0.3" x2="1.4" y2="-0.4" />
      <line x1="1.1" x2="1.2" y1="-0.27" y2="-0.58" />
      <line x1="1.1" x2="1.35" y1="-0.27" y2="-0.13" />
    </g>
    <use href="#arm" transform="scale(-1 1)" />
  </g>
</g>

<style>
	g {
	  transition: transform 0.3s ease-out;
	}
</style>