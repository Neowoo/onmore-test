<template>
  <div class="about">
    <h1>隨機1~5 請看console</h1>

  </div>
</template>
<script>
  export default {
    name: 'About',
    data() {
      return {
        testArray: [1,2,3,4,5]
      }
    },
    mounted() {
      let that = this
      setInterval(() => {
        let randonIndex = Math.floor(Math.random() * that.testArray.length);
        console.log(that.testArray[randonIndex])
        that.testArray.splice(randonIndex, 1)
        if (that.testArray.length === 0) {
          that.testArray = [1,2,3,4,5]
        }
      }, 1000)
    }
  }
</script>
