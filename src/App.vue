<template>
  <div id="app">
    <div style="width:100%; height:700px;" id="orgchart"/>
  </div>
</template>

<script>
//import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    // HelloWorld
  },

  mounted() {
    this.getChart();
  },
  computed: {
    getChart() {
      return {
        chart: new OrgChart(document.getElementById("orgchart"), {
          nodeBinding: {
            field_0: "name"
          },
          nodes: [
            { id: 1, name: "Amber McKenzie" },
            { id: 2, pid: 1, name: "Ava Field" },
            { id: 3, pid: 1, name: "Peter Stevens" }
          ]
        })
      };
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
