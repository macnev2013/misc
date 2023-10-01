<script>
    export let title = undefined;
</script>

<div class="card">
    {#if title}
        <h2>{title}</h2>
    {/if}
    <slot/>
</div>

<style>
    .card {
        padding: 1rem;
        width: 70vh;
        border: 1px solid #ccc;
        border-radius: 5px;
        margin-bottom: 1rem;
    }

</style>
