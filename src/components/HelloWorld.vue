<template>
  <div class="hello">
    <button @click="popup">彈窗</button>
    <Popup v-if="popupShow" @closePop="closePop">
      <input type="text" placeholder="title">
      <input type="text" placeholder="content">
    </Popup>
  </div>
</template>

<script>
import Popup from "./Popup";
export default {
  name: "HelloWorld",
  components: {
    Popup
  },
  data () {
    return {
      popupShow: false
    }
  },
  methods: {
    popup () {
      this.popupShow = true
    },
    closePop () {
      this.popupShow = false
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
input {
  display: block;
  margin: 20px auto
}
</style>
