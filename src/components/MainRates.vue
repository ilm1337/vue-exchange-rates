<script>
import axios from "axios";
export default {
  data() {
    return {
      rates: "",
    };
  },
  methods: {
    getRates() {
      axios
        .get(
          "https://v6.exchangerate-api.com/v6/ba05275c2706f3b27787a624/latest/EUR"
        )
        .then(({ data }) => {
          this.rates = data.conversion_rates;
        });
    },
  },
  mounted() {
    this.getRates();
  },
};
</script>

<template>
  <div class="block">
    <div class="box">
      <h1 class="title is-4">POPULAR EXCHANGE RATES</h1>

      <table
        class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth"
      >
        <thead>
          <tr>
            <th>Currency</th>
            <th>Rate</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>USD 🇺🇸</td>
            <td>{{ rates.USD }}</td>
          </tr>
          <tr>
            <td>GBP 🇬🇧</td>
            <td>{{ rates.GBP }}</td>
          </tr>
          <tr>
            <td>CHF 🇨🇭</td>
            <td>{{ rates.CHF }}</td>
          </tr>
          <tr>
            <td>CNY 🇨🇳</td>
            <td>{{ rates.CNY }}</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="box">
      <h1 class="title is-4">ALL EXCHANGE RATES</h1>
      <table
        class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth"
      >
        <thead>
          <tr>
            <th>Currency</th>
            <th>Rate</th>
          </tr>
        </thead>
        <tr v-for="(rate, currency) in rates">
          <td>{{ currency }}</td>
          <td>{{ rate }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style></style>
