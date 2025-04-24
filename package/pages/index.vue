<script setup lang="ts">
import BlogCards from "~/components/dashboards/BlogCards.vue";
import EarningReport from "~/components/dashboards/EarningReport.vue";
import PopularProducts from "~/components/dashboards/PopularProducts.vue";
import SalesProfit from "~/components/dashboards/SalesProfit.vue";
import TotalFolllowers from "~/components/dashboards/TotalFolllowers.vue";
import Totalincome from "~/components/dashboards/Totalincome.vue";
</script>

<template>
  <v-row>
    <v-col cols="12" md="8"><SalesProfit /></v-col>
    <v-col cols="12" md="4"
      ><TotalFolllowers class="mb-6" />
      <Totalincome />
    </v-col>
    <v-col cols="12" md="8"><PopularProducts /></v-col>
    <v-col cols="12" md="4"><EarningReport /></v-col>
    <v-col cols="12"><BlogCards /></v-col>
    <v-col class="text-center mt-2">
      <p class="text-muted">
        Design and Developed by
        <a
          flat
          variant="text"
          href="https://wrappixel.com"
          target="_blank"
          class="pl-1 text-primary"
          >wrappixel.com</a
        >
      </p>
    </v-col>
  </v-row>
</template>
