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
          {{ dateInLocalLalguage(data.show_date) }}
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

    dateInLocalLalguage: (date) => {
      return new Date(date).toLocaleString(navigator.language, {
        day: "numeric",
        month: "long",
        year: "numeric",
      });
    },
  },

  created() {
    Axios.get("http://localhost:5000/api/v2/tour_dates").then((result) => {
      console.log(result.data);
      this.fetchData = result.data;
    });
  },
};
</script>
