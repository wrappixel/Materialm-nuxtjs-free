<script setup lang="ts">
import { ref } from "vue";
import SalesProfit from "~/components/dashboards/SalesProfit.vue";
import TotalFolllowers from "~/components/dashboards/TotalFolllowers.vue";
import Totalincome from "~/components/dashboards/Totalincome.vue";
import PopularProducts from "~/components/dashboards/PopularProducts.vue";
import EarningReport from "~/components/dashboards/EarningReport.vue";
import BlogCards from "~/components/dashboards/BlogCards.vue";
</script>

<template>
    <v-row>
        <v-col cols="12" sm="12" lg="8">
            <SalesProfit />
        </v-col>
        <v-col cols="12" sm="12" lg="4">
            <div class="mb-6">
                <TotalFolllowers/>
            </div>
            <div>
                <Totalincome/>
            </div>
        </v-col>
        <v-col cols="12" sm="12" lg="4">
            <PopularProducts/>
        </v-col>
        <v-col cols="12" sm="12" lg="8">
            <EarningReport/>
        </v-col>
        <v-col cols="12" sm="12" lg="12">
            <BlogCards/>
        </v-col>
        <v-col class="text-center mt-2">
            <p class="text-muted">Design and Developed by <a flat variant="text" href="https://www.wrappixel.com/" target="_blank" class="pl-1 text-primary">wrappixel.com</a></p>
        </v-col>
    </v-row>
</template>