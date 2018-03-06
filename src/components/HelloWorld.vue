<template>
  <div class="hello">
    <h1>messgae : {{ msg }}</h1>
    <p>computed message : {{rMsg}}</p>
    <p>Watch message : {{wMsg}}</p>
    <p>Method message : {{mMsg()}}</p>
    <input type='text' v-model='msg' />
  </div>
</template>

<script>
export default {
  name: "HelloWorld",

  data() {
    return {
      msg: "Welcome to VnoMvk VueLab",
      wMsg: "hi"
    };
  },
  methods: {
    mMsg: function() {
      return this.msg;
    }
  },
  computed: {
    rMsg: function() {
      return this.msg
        .split("")
        .reverse()
        .join("");
    }
  },
  watch: {
    msg: function() {
      return (this.wMsg = "Changes Accurs" + this.msg);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
</style>
