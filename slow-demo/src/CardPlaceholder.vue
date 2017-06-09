<template>
  <div class="troyes-card-placeholder-wrapper" v-show="loaded">
    <div class="troyes-card-placeholder troyes-card troyes-card-hoverable">
      <div ref="bg" class="troyes-card-placeholder__title">
        <h2 v-html="title"></h2>
      </div>
      <div class="troyes-card-placeholder__info">
        <div class="troyes-card-placeholder__info__tags">
          <span class="troyes-card-placeholder__info__tags__tag" v-html="tag"></span>
        </div>
        <p class="troyes-card-placeholder__info__description" v-html="desc"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['bin'],

  data() {
    const desc = '<span class="troyes-card-placeholder__info__description__line">&nbsp;</span>'.repeat(3)


    return {
      loaded: false,
      title: '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;',
      tag: '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;',
      desc
    }
  },

  mounted() {
    fetch(this.bin)
      .then((res) => res.json())
      .then((bin) => {
        this.$refs.bg.style.backgroundColor = bin.header
        this.loaded = true
        this.title = bin.title
        this.tag = bin.tag
        this.desc = bin.content
      })
  }
}
</script>

<style>
.troyes-card-placeholder {
  border: ;
  cursor: pointer;
  min-height: 340px;
  position: relative;
  border-radius: 2px;
  border: 1px solid rgba(0,0,0,.12);
  box-shadow: 0 2px 2px 0 rgba(0,0,0,.14), 0 3px 1px -2px rgba(0,0,0,.2), 0 1px 5px 0 rgba(0,0,0,.12);
}

.troyes-card-placeholder__title {
  align-items: flex-end;
  background: #eee;
  border-bottom: 1px solid #dedede;
  display: flex;
  height: 150px;
  padding: 24px;
}

.troyes-card-placeholder__title > h2 {
  background-color: rgba(0, 0, 0, .5);
  color: #fff;
  font-size: 32px;
  margin: 0;
  padding: 5px 20px;
}

.troyes-card-placeholder__info {
  padding: 15px;
  text-align: left;
}

.troyes-card-placeholder__info__tags > :first-child {
  margin-left: 0;
}

.troyes-card-placeholder__info__tags__tag {
  background-color: #1abc9c;
  border-radius: 4px;
  font-size: 12px;
  padding: 3px 10px;
}

.troyes-card-placeholder__info__description {
  color: #444;
  margin-bottom: 0;
  text-align: justify;
}

.troyes-card-placeholder__info__description__line {
  background-color: #ddd;
  display: block;
  margin-bottom: 5px;
}

.troyes-card-placeholder__info__description__line:last-child {
  margin-bottom: 0;
  width: 50%;
}
</style>
