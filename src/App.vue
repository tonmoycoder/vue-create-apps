<template>
  <h1>Dc superheros</h1>
  <ul>
    <li v-for="(hero, index) in dcHeros" :key="index">{{ hero.name }}</li>
  </ul>
  <input v-model.lazy="newhero" />
  <button :disabled="isDisabled">Click Here</button>
  <!-- <h1 v-once>count is : {{ counter }}</h1>

  <h2 v-else-if="isShowing === null">This is v-else-if part</h2>
  <h2 v-else>This is v-else part of vuejs</h2>

  <p>Somethings else</p> -->
</template>

<script>
export default {
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
