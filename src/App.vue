<template>
  <div id="app">
    <Header />
    <span style="padding-top: 170px">
      <Examples />
      <Examples />
      <Examples />
    </span>
    <span>
      <Examples />
      <Examples />
      <Examples />
    </span>
    <Sidebar />
  </div>
</template>

<script>
import Header from "./components/layout/Header";
import Examples from "./components/Examples";
import Sidebar from "./components/layout/Sidebar";

export default {
  name: "app",
  components: {
    Header,
    Examples,
    Sidebar
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

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  background: #acb9e8;
  font-size: 20px !important;
}

button {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  font-size: 20px !important;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #2c2c2c;
}

span {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  padding: 10px 10px 10px 10px;
}
</style>
