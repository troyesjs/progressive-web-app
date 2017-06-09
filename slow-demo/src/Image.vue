<template>
  <div class="troyes-image">
    <img :src="src" :width="width" :height="height" :alt="alt" />
  </div>
</template>

<script>
export default {
  props: ['src', 'low', 'dominantColor', 'width', 'height', 'alt'],

  data() {
    return {
      applied: null,
      appliedStyle: {
        backgroundColor: this.dominantColor,
        filter: 'blur(10px)'
      }
    }
  },

  mounted() {
    this.loadLowRes()
      .then(() => this.loadHighRes())
  },

  methods: {
    loadLowRes() {
      return new Promise((resolve) => {
        const lowRez = new Image(this.width, this.height)
        lowRez.src = this.low

        lowRez.onload = () => {
          this.applied = this.low
          resolve()
        }
      })
    },

    loadHighRes() {
      return new Promise((resolve) => {
        const lowRez = new Image(this.width, this.height)
        lowRez.src = this.src

        lowRez.onload = () => {
          this.applied = this.src
          this.appliedStyle.filter = 'blur(0px)'
          resolve()
        }
      })
    }
  }
}
</script>

<style scoped>
.troyes-image {
  overflow: hidden;
}

.troyes-image > img {
  transition: filter 1s ease;
}
</style>
