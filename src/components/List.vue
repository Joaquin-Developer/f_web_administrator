<template>
  <p>list</p>
</template>


<script>
import Axios from "axios";

export default {
  name: "ListComponent",
  props: {},

  data: () => ({
    fetchData: null,
  }),

  created() {
    Axios.get("http://localhost:5000/api/v2/tour_dates").then((result) => {
      console.log(result);
      this.fetchData = result.data;
    });
  },
};
</script>