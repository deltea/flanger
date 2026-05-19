<script lang="ts">
	import "./layout.css";

	let { children } = $props();
</script>

<head>
	<title>Flanger ⋅ Hack Club</title>
</head>

<div class="h-screen bg-black p-12 crt relative overflow-hidden">
	{@render children()}
</div>
