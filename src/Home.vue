<template>
  <div>
    <input placeholder="type to edit MockData" v-on:input="handleInput" v-bind:value="getMockData" />
    <div>this is data in vuex called mockData: {{getMockData}}</div>
    <button v-on:click="goToPageTwo">go to page 2</button>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import { router } from "./main";
export default {
  name: "Home",
  data: function() {
    return {};
  },
  computed: {
    ...mapGetters(["getMockData"])
  },
  methods: {
    ...mapActions(["setMockDataAction"]),
    handleInput: function(event) {
      this.setMockDataAction(event.target.value);
    },
    goToPageTwo: function() {
      router.push("/pagetwo");
    }
  },
  components: {},
  props: {}
};
</script>

<style scoped>
</style>