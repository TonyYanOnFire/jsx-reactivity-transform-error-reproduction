<script>
import Vue from 'vue'

Vue.component("my-h", {
  name: "MyH",
  props: {
    level: {
      type: Number,
      required: true
    }
  },
  render(h) {
    const Tag = `h${this.level}`
    return <Tag>{this.$slots.default}</Tag>;
  }
});

export default {
  setup () {
    const randomLevel = $ref(Math.ceil(Math.random() * 6))

    return {
      ...$$({
        randomLevel
      })
    }
  }
}
</script>

<template>
  <div>
    <my-h level="1">I'm h1</my-h>
    <my-h level="2">I'm h2</my-h>
    <my-h :level="randomLevel">I'm random</my-h>
  </div>
</template>
