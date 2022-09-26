<template>
  <main>
    <h1>{{ title }}</h1>
    <div v-if="showModal">
      <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">Click Here</a>
          <a href="#">Sign up</a>
        </template>
        <h1>Unbelievable Give Aways</h1>
        <p>You ain't ready for these prices</p>
      </Modal>
    </div>
    <p></p>
    <button @click="toggleModal">Show Modal</button>
  </main>
</template>

<script>
import Modal from '@/components/Modal.vue'

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "Glorious Purpose",
      header: "Receive the best discounts",
      showModal: false
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
    },
    toggleModal() {
      this.showModal = !this.showModal
      // console.log('show modal')
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
