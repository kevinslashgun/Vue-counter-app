<template>
    <section>
        <h2>Count</h2>
        <p>{{ count }}</p>
        <div id="btn-wrapper">
            <div id="box1">
                <button @click="increment">Increment</button>
            </div>
            <div id="box2">
                <button @click="decrement">Decrement</button>
            </div>
            <div id="box3">
                <button @click="reset">Reset</button>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ref, watch } from 'vue';

const count = localStorage.getItem('count') ? ref(Number(localStorage.getItem('count'))) : ref(0);

const increment = () => {
    count.value++;
};

const decrement = () => {
    count.value > 0 ? count.value-- : count.value;
};

const reset = () => {
    count.value = 0;
};

watch(count, () => {
    localStorage.setItem('count', count.value);
});

</script>

<style scoped>
section {
    background-color: white;
    padding: 1rem;
    text-align: center;
    border-radius: 16px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
}

#btn-wrapper {
    margin-top: 1em;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    row-gap: 0.5rem;
    column-gap: 0.5rem;
}

#box3 {
    grid-column: 1 / span 2;
}

button {
    background-color: black;
    color: white;
    padding: 0.25em 0.5em;
    border: none;
    border-radius: 6px;
}

button:hover {
    background-color: rgba(0, 0, 0, 0.8);
    cursor: pointer;
}
</style>