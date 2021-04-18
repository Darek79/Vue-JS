<template>
  <h2>hello {{ name }}</h2>

  <button @click="clickUp">up</button>
  <button @click="clickDown">down</button>
  <p>my count: {{ counter }}</p>
  <ul>
    <li v-for="(nr, i) in arr" :key="nr">
      {{ nr }} - {{ i + 5 }}
    </li>
  </ul>
  <input :value="txt" @input="write($event)" />
  <p>{{ txt }}</p>
  <input v-model="msg" placeholder="edit-me" />
  <p>{{ msg }}</p>
</template>
<script>
export default {
  data() {
    return {
      name: "Darek",
      counter: 0,
      arr: [1, 2, 3, 4, 5],
      txt: "",
      msg: "",
    };
  },
  methods: {
    clickUp() {
      this.counter = this.counter + 1;
    },
    clickDown() {
      this.counter = this.counter - 1;
    },
    write(event) {
      console.log(event.target);
      this.txt = event.target.value;
    },
  },
  beforeCreate() {
    console.log("1");
  },
  created() {
    console.log("2");
  },
  beforeMount() {
    console.log("3");
  },
  mounted() {
    this.counter = 2;
  },
  beforeUnmount() {
    console.log("4");
  },
  unmounted() {
    console.log("5");
  },
};
</script>

<style scoped></style>
