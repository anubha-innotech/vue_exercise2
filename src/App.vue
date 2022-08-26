<template>
  <div class="main">
    <h2>VueJs Exercise 2</h2>
    <input type="text" ref="input">
    <button @click="focusBtn">Focus</button>
    <br />
    <button @click="show = !show">Modal</button>
    <div class="prompt" v-if="show">
      <div id="modal-box">
        <Modal title="Sign up for the giveaway!" content="Grab your ninja swag for half price!" theme="sale"
          ref="modal">
          <template v-slot:links>
            <a href="#" id="slot-link" @click="show = !show">Close</a>
          </template>
        </Modal>
      </div>
    </div>
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
      show: false
    }
  },
  methods: {
    focusBtn() {
      this.$refs.input.focus();
      console.log("focus");
    },

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
  width: 100vw;
  height: 100vh;
  padding: 20px;
}

.prompt {
  background-color: rgba(0, 0, 0, .3);
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

#modal-box {
  position: relative;
  background-color: blue;
}

#slot-link {
  position: absolute;
  display: block;
  right: 40%;
  margin: 3px;
  bottom: 0;
  text-align: center;
  color: white;
  background-color: black;
  padding: 2px 10px;
  text-decoration: none;
  font-size: 1.1rem;
  width: 80px;
  white-space: nowrap;
}

button {
  margin: 5px 0px;
  padding: 5px 10px;
  background-color:dodgerblue;
  color: white;
  font-size: 1rem;
  border: 1px solid dodgerblue;
}
input{
  font-size: 1rem;
  padding: 5px;

}
</style>


