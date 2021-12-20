<script>
  export let seed = 0;
</script>

<filter id="shadow" x="-30%" y="-15%" width="180%" height="140%">
  <feFlood flood-color="#CEEAF3" flood-opacity="0.6" result="flood1" />
  <feBlend mode="multiply" width="60%" height="78%" in="SourceGraphic" in2="flood1" result="blend2"/>
  <feTurbulence type="turbulence" baseFrequency="0.014 0.03" numOctaves="5" seed={seed} stitchTiles="stitch" result="turbulence1" />
  <feDisplacementMap in="blend2" in2="turbulence1" scale="2.3" />
</filter>
<use href="#body" x="-1"
  filter="url(#shadow)"
  opacity="0.8"
  transform-origin="-0.3 3.3"
  style="mix-blend-mode: multiply; transform: rotate(-90deg)"
/>
<use href="#body" stroke="black" stroke-width="0.16" />
