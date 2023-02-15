<template>
  <h1>Dc superheros {{ heroCount }}</h1>
  <h3>This is a random nummber {{ randomNumber }}</h3>
  <h3>This is a random nummber {{ randomNumber }}</h3>
  <h3>This is a random nummber {{ randomNumber }}</h3>
  <h3>This is method number {{ randomNumberM() }}</h3>
  <h3>This is method number {{ randomNumberM() }}</h3>
  <h3>This is method number {{ randomNumberM() }}</h3>
  <ul>
    <li v-for="(hero, index) in dcHeros" :key="index">{{ hero.name }}</li>
  </ul>
  <form @submit.prevent="addHero()">
    <input v-model.lazy="newhero" placeholder="Type hero name here" />
    <button :disabled="isDisabled">Click Here</button>
    <button type="submit">Add Hero</button>
  </form>
  <!-- <h1 v-once>count is : {{ counter }}</h1>

  <h2 v-else-if="isShowing === null">This is v-else-if part</h2>
  <h2 v-else>This is v-else part of vuejs</h2>

  <p>Somethings else</p> -->
</template>

<script>
export default {
  computed: {
    heroCount() {
      return this.dcHeros.length + " " + "herosses";
    },
    randomNumber() {
      return Math.floor(Math.random() * 100);
    },
  },
  methods: {
    addHero() {
      if (this.newhero !== "") {
        this.dcHeros.unshift({ name: this.newhero });
        this.newhero = "";
      }
    },
    randomNumberM() {
      return Math.floor(Math.random() * 100);
    },
  },
  data() {
    return {
      title: `<h1>This is a vue testing</h1>`,
      newhero: "iron man",
      isDisabled: true,
      isShowing: true,
      counter: 0,
      dcHeros: [
        { name: "supergirl" },
        { name: "batman" },
        { name: "aquaman" },
        { name: "superman" },
        { name: "wonder woman" },
      ],
    };
  },
  // mounted() {
  //   setInterval(() => {
  //     this.counter++;
  //   }, 1000);
  // },
};
</script>
