<template>
  <main>
    Hello world

    <input type="number" v-model="inputValue" />

    <div>
      {{ fizzBuzz }}
    </div>

    <div> <!-- ici rajouter une condition si inputValue > 5 -->
      <b>Student :</b>
    </div>
    <div class="student"> <!-- afficher tout les étudiants ici -->
      <div>
        name: ici le nom
      </div>
      <div>
        age: ici l'age
      </div>
    </div>
    <div>
      <b>Cas 1, je veux avoir tout les étudiants qui moins de 21 ans (afficher la donnée brute) :</b>
    </div>
    <div>
      under21 ici
    </div>
    <div>
      <b>Cas 2, je veux trier les étudiants par leur age du plus petit au plus grand (afficher la donnée brute) :</b>
    </div>
    <div>
      order ici
    </div>
  </main>
</template>

<script setup lang="ts">
import {computed, ref} from "vue";
import type Student from "@/type/Student.ts";

const students: Student[] = [
  {
    name: 'Toto',
    age: 23
  },
  {
    name: 'Tata',
    age: 20
  },
  {
    name: 'Titi',
    age: 21
  },
  {
    name: 'Tutu',
    age: 22
  },
  {
    name: 'Léo',
    age: 19
  },
  {
    name: 'Léa',
    age: 24
  },
  {
    name: 'Paul',
    age: 20
  },
  {
    name: 'Sophie',
    age: 21
  },
  {
    name: 'Marc',
    age: 23
  },
  {
    name: 'Julie',
    age: 22
  }
];

const inputValue = ref<number>(0);

const under21 = computed(() => {
  return students;
});

const order = computed(() => {
  return students;
});

const fizzBuzz = computed(() => {
  return inputValue;
});

</script>

<style>
main {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  padding: 3rem;
}

input {
  max-width: 300px;

}

.student {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
</style>
