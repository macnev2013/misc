<script>
    export let id;
    export let min = 1;
    export let max = 64;
    export let value = 32;
    export let title;

    if (value < min) {
        value = min;
    }
    if (value > max) {
        value = max;
    }

</script>

<p class="title">{title}: {value}</p>
<div class="slider">
    <p class="min label">{min}</p>
    <input bind:value {id} max={max} {min} type="range"/>
    <p class="max label">{max}</p>
</div>

<style>
    .title {
        margin-bottom: 10px;
        text-align: center;
    }

    .slider {
        width: 100%;
        display: flex;
        align-items: center;
        padding: 0;
        margin: 0;
    }

    input {
        -webkit-appearance: none;
        appearance: none;
        width: 100%;
        height: 4px;
        background: white;
        outline: none;
        opacity: 0.7;
        -webkit-transition: .2s;
        transition: opacity .2s;

    }

    input::-webkit-slider-thumb {
        -webkit-appearance: none;
        appearance: none;
        width: 25px;
        height: 25px;
        border-radius: 100px;
        background: aqua;
        cursor: pointer;
    }

    input:hover {
        opacity: 1;

    }

    .label {
        padding: 3px 8px;
        background: aqua;
        color: black;
        border-radius: 4px;
        margin-top: 0;
        margin-bottom: 0;
    }

    .min {
        margin-right: 10px;
    }

    .max {
        margin-left: 10px;
    }
</style>