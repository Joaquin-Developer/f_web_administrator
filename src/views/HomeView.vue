<template>
  <div class="title">
    <h2>Registro</h2>
  </div>

  <table class="table">
    <thead>
      <tr>
        <th scope="col">ID</th>
        <th scope="col">Tour show</th>
        <th scope="col">Scenary</th>
        <th scope="col">Place</th>
        <th scope="col">Show date</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(data, index) in fetchData" v-bind:key="index">
        <th scope="row">{{ data.tour_id }}</th>
        <td>{{ data.tour_show }}</td>
        <td>{{ data.scenary }}</td>
        <td>{{ data.place }}</td>
        <td>
          {{
            new Date(data.show_date).toLocaleString(navLanguage(), {
              day: "numeric",
              month: "long",
              year: "numeric",
            })
          }}
        </td>
        <td></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import Axios from "axios";

export default {
  name: "HomeView",

  data: () => ({
    fetchData: null,
  }),

  methods: {
    navLanguage: () => navigator.language,
  },

  created() {
    Axios.get("http://localhost:5000/api/v2/tour_dates").then((result) => {
      console.log(result.data);
      this.fetchData = result.data;
    });
  },
};
</script>

<style>
.title {
  margin-top: 2em;
  margin-bottom: 2em;
}
</style>
