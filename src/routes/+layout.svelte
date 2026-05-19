<script lang="ts">
	import "./layout.css";

	let { children } = $props();
</script>

<head>
	<title>Flanger ⋅ Hack Club</title>
</head>

<div class="h-screen bg-black p-12 crt lens-distortion relative">
	{@render children()}

	<!-- lens distortion -->
	<!-- <svg style="display: none;">
		<filter id="lens-distortion">
			<feImage href="distort-map.png" result="map" />
			<feDisplacementMap in="SourceGraphic" in2="map" scale="50" xChannelSelector="R" yChannelSelector="G" />
		</filter>
	</svg> -->
</div>
