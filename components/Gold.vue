<template>
  <div>
    <div class="row">
      <div class="col-md-12">
        <div class="card">
          <div class="card-body">
            <h6 style="direction:rtl">تاریخ آخرین بروزرسانی : {{this.$data.LastModified}}</h6>
          </div>
        </div>
      </div>
    </div>
    <h6>قیمت سکه</h6>
    <table class="table table-striped table-bordered">
      <thead class="thead-dark">
        <tr>
          <th scope="col">واحد</th>
          <th scope="col">خرید</th>
          <th scope="col">فروش</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in gold" :key="item.Code">
          <td>{{item.Coin}}</td>
          <td>{{item.Sell}} تومان</td>
          <td>{{item.Buy}} تومان</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
import * as axios from "axios";
export default {
  mounted() {
    axios.get("https://currency.jafari.pw/json").then(data => {
      this.$data.gold = data.data.Gold;
      this.$data.LastModified = data.data.LastModified;
    });
  },
  data() {
    return {
      LastModified: "",
      gold: []
    };
  }
};
</script>