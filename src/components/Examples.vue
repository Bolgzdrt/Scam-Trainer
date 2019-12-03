<template>
  <div>
    <div @click="showModal" class="card">
      <img src="../assets/image-placeholder.jpg" alt="Example Image" />
      <div class="container">
        <h4>
          <b>Example Title</b>
        </h4>
      </div>
    </div>
    <ExampleItem v-show="isModalVisible" @close="closeModal" />
  </div>
</template>

<script>
import ExampleItem from "./ExampleItem";

export default {
  name: "Examples",
  components: {
    ExampleItem
  },
  data() {
    return {
      isModalVisible: false
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
};
</script>

<style scoped>
.card {
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  border-radius: 5px;
  display: inline-block;
  padding: 10px;
  background: white;
  cursor: pointer;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
  text-align: center;
}

img {
  border-radius: 5px 5px 0 0;
}
</style>