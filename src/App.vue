<template>
  <div class="main">
    <h2>VueJs Exercise 2</h2>
    <input type="text" ref="input">
    <button @click="focusBtn">Focus</button>
    <br />
    <Modal title="Sign up for the giveaway!" content="Grab your ninja swag for half price!" theme="sale" ref="modal">
      <template v-slot:links>
        <a href="#" id="slot-link" @click="show = !show">Close</a>
      </template>
    </Modal>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  components: {
    Modal
  },
  data() {
    return {
    }
  },
  methods: {
    focusBtn() {
      this.$refs.input.focus();
      console.log("focus");
    },
    childDataFn(name) {
      alert(name)
    }

  }
}
</script>

<style>
* {
  margin: 0px;
  padding: 0;
}

.main {
  position: relative;
  height: 100%;
  padding: 20px;
}

button {
  margin: 5px 0px;
  padding: 5px 10px;
  background-color: dodgerblue;
  color: white;
  font-size: 1rem;
  border: 1px solid dodgerblue;
}

input {
  font-size: 1rem;
  padding: 5px;
}

#slot-link {
  text-align: center;
  color: white;
  background-color: black;
  padding: 4px 20px;
  text-decoration: none;
  font-size: 1.1rem;
  width: 80px;
  white-space: nowrap;
}
</style>


