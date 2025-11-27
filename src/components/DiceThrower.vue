<script setup>
import { ref } from 'vue';

const diceArray = ref([]);
const diceCount = ref({
    1: 0,
    2: 0,
    3: 0,
    4: 0,
    5: 0,
    6: 0
});

const throwDice = () => {
    diceArray.value = [];
    diceCount.value = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0};
    for (let i = 0; i < 8; i++) {
        const result = Math.floor(Math.random() * 6) + 1;
        diceArray.value.push(result);
        diceCount.value[result]++;
    }
}
</script>

<template>
    <table>
        <thead>
            <tr>
                <th>Getal</th>
                <th>Aantal</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(amount, number) in diceCount" :key="number">
                <td>{{ number }}</td>
                <td>{{ amount }}</td>
            </tr>
        </tbody>
    </table>

    <button @click="throwDice">Gooi!</button>
</template>

<style scoped>
</style>
