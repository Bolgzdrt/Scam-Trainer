<template>
  <transition name="modal-fade">
    <div class="modal-backdrop">
      <div class="modal">
        <header class="modal-header">
          <slot name="header">
            <button type="button" class="btn-close" @click="close">
              <img
                class="close-icon"
                src="@/assets/iconmonstr-arrow-2-240.png"
                alt="right arrow icon"
              />
            </button>
            <div class="header-title">Example Title</div>
          </slot>
        </header>
        <section class="modal-body">
          <slot name="body">
            <img
              src="../assets/image-placeholder.jpg"
              class="example-item-image"
              alt="Example Image"
            />
            <div
              class="example-explanation"
            >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
          </slot>
        </section>
        <footer class="modal-footer">
          <slot name="footer">
            <button type="button" class="btn-green" @click="showModal2">Quiz</button>
          </slot>
        </footer>
      </div>
      <Quiz v-show="isModal2Visible" @close="closeModal2" />
    </div>
  </transition>
</template>

<script>
import Quiz from "./Quiz";

export default {
  name: "ExampleItem",
  components: {
    Quiz
  },
  data() {
    return {
      isModal2Visible: false
    };
  },
  methods: {
    close() {
      this.$emit("close");
    },
    showModal2() {
      this.isModal2Visible = true;
    },
    closeModal2() {
      this.isModal2Visible = false;
    }
  }
};
</script>

<style>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background: #ffffff;
  box-shadow: 2px 2px 20px 1px;
  overflow-x: auto;
  display: flex;
  flex-direction: column;
  width: 50%;
  border-radius: 5px;
  width: 740px;
  height: 750px;
}

.modal-header {
  padding: 15px;
  display: flex;
}

.modal-footer {
  padding: 15px;
  display: flex;
}

.modal-header {
  border-bottom: 1px solid #eeeeee;
  justify-content: flex-start;
}

.modal-footer {
  border-top: 1px solid #eeeeee;
  justify-content: flex-end;
}

.modal-body {
  position: relative;
  padding: 20px 10px;
}

.example-explanation {
  padding-top: 20px;
  padding-right: 10px;
  padding-left: 10px;
}

.btn-close {
  border: none;
  font-size: 20px;
  cursor: pointer;
  font-weight: bold;
  color: #000000;
  background: transparent;
}

.btn-green {
  color: white;
  background: #000000;
  border: 10px solid #000000;
  border-radius: 4px;
  cursor: pointer;
}

.modal-fade-enter,
.modal-fade-leave-active {
  opacity: 0;
}

.modal-fade-enter-active,
.modal-fade-leave-active {
  transition: opacity 0.5s ease;
}

.example-item-image {
  display: block;
  margin-left: auto;
  margin-right: auto;
  border-radius: 5px;
}

.close-icon {
  -webkit-transform: scaleX(-1);
  transform: scaleX(-1);
  height: 36px;
  width: 36px;
  vertical-align: middle;
}

.header-title {
  padding-left: 15px;
  padding-top: 3px;
}
</style>