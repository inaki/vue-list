<template>
  <div id="app" class="container">
      <nr-header/>
      <nr-table :documents="documents"></nr-table>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Table from "./components/Table.vue";
import Header from "./components/Header.vue";

export default {
  name: "app",
  components: {
    nrTable: Table,
    nrHeader: Header
  },
  data() {
    return {
      documents: []
    };
  },
  mounted() {
    axios.get("http://localhost:3000/documents").then(response => {
      this.documents = response.data;
      console.log(response.data);
    });
  }
};
</script>

<style lang="scss">
.container {
  max-width: 1200px;
  margin: auto;
}
</style>
