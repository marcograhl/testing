<!-- filter playground: -->
<!-- https://yoksel.github.io/svg-filters/#/ -->
<filter id="noise" filterUnits="objectBoundingBox">
	<feTurbulence out="noise" baseFrequency="130" />
	<feColorMatrix values="6 6 6 255 -6
                         6 6 6 255 -9
                         6 6 6 255 -3
                         6 6 6 0 1"
	 in="noise" out="matrix" />
	<feComposite operator="in" in="matrix" in2="SourceAlpha" result="combined" />
	<feBlend mode="color-burn" in="SourceGraphic" in2="combined" result="blend" />
</filter>

<radialGradient id="radial-fade" cx="0.55" cy="0.38" fr="0.45" r="0.7">
	<stop stop-color="white" stop-opacity="0" offset="0" />
	<stop stop-color="white" offset="1" />
</radialGradient>

<mask id="fade" maskContentUnits="objectBoundingBox">
	<circle cx="0.5" cy="0.5" r="0.5" fill="url(#radial-fade)" />
</mask>

<circle cy="3" r="1"
	filter="url(#noise)" mask="url(#fade)" />
<circle cy="2" r="0.8"
	filter="url(#noise)" mask="url(#fade)" />
<circle cy="1" r="0.6"
	filter="url(#noise)" mask="url(#fade)" />