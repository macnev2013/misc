<script>
    export let id;
    export let name;
    export let value;
</script>

<div class="checkbox">
    <input {id} {name} type="checkbox" {value}>
    <label for={id}>{name}</label><br>
</div>


<style>
    .checkbox {
        display: flex;
        align-items: center;
        margin-bottom: 10px;
    }

    label {
        margin-left: 10px;
    }

</style>