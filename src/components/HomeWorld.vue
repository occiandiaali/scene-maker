<template>
  <div class="shell">
    <div class="segment">
      <h1>Good Names</h1>
      <draggable v-model="meals" tag="ul" group="meals" :animation="300">
        <template #item="{ element: meal }">
          <li>{{ meal }}</li>
        </template>
      </draggable>
    </div>

    <div class="segment">
      <h1>Terrible Foods</h1>
      <draggable v-model="yuckyMeals" tag="ul" group="meals" :animation="300">
        <template #item="{ element: meal }">
          <li>{{ meal }}</li>
        </template>
      </draggable>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import draggable from "vuedraggable";
const meals = ref([
  "Hamburger",
  "Pizza",
  "Spaghetti",
  "Tacos",
  "Teriyaki Chicken",
]);

const yuckyMeals = ref([
  "Bat wing soup",
  "Spicy Octopus",
  "Anything from Taco Bell",
]);
</script>

<style scoped>
li {
  list-style: none;
  width: 350px;
  height: 40px;
  background-color: burlywood;
  margin: 8px;
  border-radius: 24px;
  cursor: pointer;
}

.segment {
  width: 450px;
  border: 1px solid grey;
  border-radius: 6px;
  margin: 8px;
}

.shell {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 6px;
}
</style>
