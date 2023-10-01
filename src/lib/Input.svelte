<script>
</script>

<div class="container">
	<input {...$$restProps} />
	<div class="internal-element">
		<slot />
	</div>
</div>

<style>
	input {
		padding: 15px 20px;
		width: 70vh;
		font-size: 20px;
		background-color: black;
		color: white;
		border: none;
	}

	.container {
		display: flex;
		align-items: center;
		justify-content: center;
		border: 2px solid aqua;
		border-radius: 8px;
	}

	.internal-element {
		margin: 10px;
	}
</style>
