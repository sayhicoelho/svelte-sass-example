<script>
	export let name;
</script>

<h1>Hello {name}!</h1>

<style type="text/scss">
	@import '../scss/vars';

	h1 {
		color: $color;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
</style>
