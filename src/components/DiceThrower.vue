<script setup>
import { ref } from 'vue';

const diceCount = ref({
    1: 0,
    2: 0,
    3: 0,
    4: 0,
    5: 0,
    6: 0
});

const throwDice = () => {
    diceCount.value = {1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0};
    for (let i = 0; i < 8; i++) {
        const result = Math.floor(Math.random() * 6) + 1;
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
            <tr v-for="(amount, index) in diceCount" :key="index">
                <td>{{ index }}</td>
                <td>{{ amount }}</td>
            </tr>
        </tbody>
    </table>

    <button @click="throwDice">Gooi!</button>
</template>

<style scoped>
</style>
