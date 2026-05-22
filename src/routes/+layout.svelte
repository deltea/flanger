<script lang="ts">
	import "./layout.css";
	import "iconify-icon";

	let { children } = $props();
</script>

<head>
	<title>Flanger ▪︎ Hack Club</title>
</head>

<div class="h-screen bg-black lg:p-12 p-4 crt relative overflow-hidden">
	{@render children()}
</div>
