<template>
    <!-- se os parametros forem verdadeiros sera aplicada a classe -->
    <button class="button" :class="{ operation, double, triple }">
        {{ label }}
    </button>
</template>

<script>
    export default {
        props: {
            label: {},
            operation: { type: Boolean },
            double: { type: Boolean },
            triple: { type: Boolean }
        }
    }
</script>

<style>
    :root { /* cria uma pseudo classe */
        --bg-button: #f0f0f0; /* para criar variavies deve começar com -- */
        --boder-button: solid 1px #888
    }

    .button {
        font-size: 1.4em;
        background-color: var(--bg-button); /* usando a variavel */
        border: none;
        border-right: var(--boder-button);
        border-bottom: var(--boder-button);
        outline: none;
    }

    .button:active {
        background-color: #ccc;
    }

    .button.double {
        grid-column: span 2;
    }

    .button.triple {
        grid-column: span 3;
    }

    .button.operation {
        background-color: #fa8231;
        color: #fff;
    }

    .button.button.operation:active {
        background-color: #fa8231cc;
    }
</style>
