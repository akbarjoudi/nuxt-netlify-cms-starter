<template>
  <section>
    <div class="row py-md-3">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <currency></currency>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <gold></gold>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Currency from "~/components/Currency";
import Gold from "../components/Gold";
export default {
  components: {
    Currency,
    Gold
  }
};
</script>

