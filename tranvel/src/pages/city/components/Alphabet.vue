<template>
  <ul class="list">
    <li class="item"
        v-for="(item,key) in letter"
        :key="item"
        :ref="item"
        @click="changeletter"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
    >
      {{item}}
    </li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props:{
    cities:Object
  },
  data(){
    return {
      touchStatus: false,
      startY: 0
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed:{
    letter(){
      const letter=[];
      for(let i in this.cities){
        letter.push(i);
      }
      return letter;
    }
  },
  methods:{
    changeletter(e){
      this.$emit('change',e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - this.startY) / 20)
          if (index >= 0 && index < this.letter.length) {
          this.$emit('change', this.letter[index])
        }
      }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.58rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor
</style>
