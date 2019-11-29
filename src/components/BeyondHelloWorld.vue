<template>
  <div class="hello">
    <h1>{{ message }}</h1>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

interface TextInterface {
  num: number;
  text: string;
  more_text: string;
}

export default Vue.extend({
  name: 'TypescriptWorld',
  props: {
    msg: String,
  },
  data: () => ({
    message: '',
  }),
  methods: {
    makeMessage(textObj: TextInterface) {
      const rtnText = textObj.num + ' ' + textObj.text + ' ' + textObj.more_text;
      this.message = rtnText;
    },
  },
  created() {
    this.makeMessage({
      num: 1,
      text: 'Component Loaded:',
      more_text: this.msg,
    });
  },
});
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
</style>
