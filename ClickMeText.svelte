<script>
  const r = 0.9;
</script>

<!-- https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/d#elliptical_arc_curve -->
<path fill="transparent"
  d={[
    ['M', 0, r].join(' '),
    ['A', r, r, 0, 0, 1, 0, -r].join(' '),
    ['A', r, r, 0, 0, 1, 0,  r].join(' '),
  ].join(' ')}
  id="click-text-path"
  transform="translate(0, 1) rotate(-80)"
  style="pointerEvents: none"
/>
<text textAnchor="middle" class="click-me" fill="#3F594E">
  <textPath href="#click-text-path" startOffset="50%">
    Click me!
  </textPath>
</text>

<style>
	.click-me {
	  text-transform: uppercase;
	  font-size: 0.15px;
	  letter-spacing: 0.1em;
	  font-weight: 600;
	  user-select: none;
	}
</style>