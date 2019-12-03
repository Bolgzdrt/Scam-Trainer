<template>
  <transition name="modal2-fade">
    <div class="modal2-backdrop">
      <div class="modal2">
        <header class="modal2-header">
          <slot name="header">
            <button type="button" class="btn-close" @click="close">
              <img
                class="close-icon"
                src="@/assets/iconmonstr-arrow-2-240.png"
                alt="right arrow icon"
              />
            </button>
            <div class="header-title">Example Quiz</div>
          </slot>
        </header>
        <section class="modal2-body">
          <slot name="body">
            <form class="form-quiz" action>
              Question 1
              <br />
              <input class="option" type="radio" name="1" value="1" /> Answer
              <br />
              <input class="option" type="radio" name="1" value="2" /> Answer
              <br />
              <input class="option" type="radio" name="1" value="3" /> Answer
              <br />
              <br />Question 2
              <br />
              <input class="option" type="radio" name="2" value="1" /> Answer
              <br />
              <input class="option" type="radio" name="2" value="2" /> Answer
              <br />
              <input class="option" type="radio" name="2" value="3" /> Answer
              <br />
              <br />Question 3
              <br />
              <input class="option" type="radio" name="3" value="1" /> Answer
              <br />
              <input class="option" type="radio" name="3" value="2" /> Answer
              <br />
              <input class="option" type="radio" name="3" value="3" /> Answer
            </form>
          </slot>
        </section>
        <footer class="modal2-footer">
          <slot name="footer">
            <button type="button" class="btn-green" @click="close">Submit</button>
          </slot>
        </footer>
      </div>
    </div>
  </transition>
</template>

<script>
export default {
  name: "Quiz",
  methods: {
    close() {
      this.$emit("close");
    }
  }
};
</script>

<style>
.modal2-backdrop {
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

.modal2 {
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

.modal2-header {
  padding: 15px;
  display: flex;
}

.modal2-footer {
  padding: 15px;
  display: flex;
}

.modal2-header {
  border-bottom: 1px solid #eeeeee;
  justify-content: flex-start;
}

.modal2-footer {
  border-top: 1px solid #eeeeee;
  justify-content: flex-end;
}

.modal2-body {
  position: relative;
  padding: 20px 10px;
  height: 600px;
}

.form-quiz {
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

.modal2-fade-enter,
.modal2-fade-leave-active {
  opacity: 0;
}

.modal2-fade-enter-active,
.modal2-fade-leave-active {
  transition: opacity 0.5s ease;
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

.option {
  margin-left: 20px;
}
</style>