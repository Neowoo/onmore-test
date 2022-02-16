<template>
  <div id="popup">
    <div class="mask"></div>
    <div class="pop-container">
      <div class="content">
        <div class="form-area">
          <slot></slot>
        </div>
        <div class="close-btn" @click="closePop">
          X
        </div>
        {{count}}
        <div class="add-btn" @click="increase">add</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Popup",
  computed: {
    count () {
      return this.$store.state.count
    }
  },
  mounted() {
    console.log(this.count)
  },
  methods: {
    closePop() {
      this.$emit('closePop')
    },
    increase () {
      this.$store.dispatch('increment')
    }
  }
};

</script>
<style lang="scss" scoped>
#popup {
  .pop-container {
    width: 300px;
    height: 300px;
    background-color: #FFF;
    position: absolute;
    z-index: 1000;
    transform: translate(-50%, -50%);
    left: 50%;
    .content {
      position: relative;
      .add-btn {
        width: 50px;
        margin: 0 auto;
        background-color: yellow;
      }
      .close-btn {
        position: absolute;
        top: 0;
        right: 0;
        width: 30px;
        height: 30px;
        background-color: red;
        border-radius: 15px;
      }
    }
  }

  .mask {
    background-color: rgba(0, 0, 0, 0.5);
    width: 100vw;
    height: 100%;
    position: fixed;
    top: 0;
    z-index: 999;
  }
}


</style>