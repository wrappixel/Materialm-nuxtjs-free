<script setup lang="ts">
import { onMounted, ref, shallowRef, watch } from "vue";
import sidebarItems from "@/components/Layout/Full/vertical-sidebar/sidebarItem";
import { Icon } from '@iconify/vue';
// Icon Imports
import { Menu2Icon, BellRingingIcon } from "vue-tabler-icons";
import { LayoutFullVerticalHeaderNotificationDD } from "#components";
import { useDisplay } from "vuetify";
const sidebarMenu = shallowRef(sidebarItems);
const { mdAndDown } = useDisplay();
const sDrawer = ref(true);
onMounted(() => {
  sDrawer.value = !mdAndDown.value; // hide on mobile, show on desktop
});
watch(mdAndDown, (val) => {
  sDrawer.value = !val;
});
</script>

<template>
  <v-navigation-drawer
    left
    v-model="sDrawer"
    app
    class="leftSidebar bg-containerBg"
    width="270"
  >
    <div class="px-4 py-5">
      <LayoutFullLogo />
    </div>
    <!-- ---------------------------------------------- -->
    <!---Navigation -->
    <!-- ---------------------------------------------- -->
    <perfect-scrollbar class="scrollnavbar bg-containerBg overflow-y-hidden">
      <v-list class=" px-4 bg-containerBg">
        <!---Menu Loop -->
        <template v-for="(item, i) in sidebarMenu">
          <!---Item Sub Header -->
          <LayoutFullVerticalSidebarNavGroup
            :item="item"
            v-if="item.header"
            :key="item.title"
          />
          <!---If Has Child -->
          <LayoutFullVerticalSidebarNavCollapse
            class="leftPadding"
            :item="item"
            :level="0"
            v-else-if="item.children"
          />
          <!---Single Item-->
          <LayoutFullVerticalSidebarNavItem
            :item="item"
            v-else
            class="leftPadding"
          />
          <!---End Single Item-->
        </template>
        <!-- <Moreoption/> -->
      </v-list>
      <div class="pa-4">
        <v-sheet
          rounded="md"
          color="lightprimary"
          class="position-relative extrabox hide-menu mx-1 px-4 py-3"
        >
          <div class="d-flex align-center">
            <div>
              <h6 class="text-h6 text-10 mb-3">Check Pro Version</h6>
              <v-btn
                target="_blank"
                href="https://www.wrappixel.com/templates/materialm-vuetify-nuxt-js-admin-template/?ref=376#demos"
                color="primary"
                class="px-5"
                rounded="pill"
                flat
                >check</v-btn
              >
            </div>
            <div class="">
              <img
                src="/images/backgrounds/upgrade.svg"
                height="100"
                width="100"
                class="px-2 ms-8"
              />
            </div>
          </div>
        </v-sheet>
      </div>
    </perfect-scrollbar>
  </v-navigation-drawer>


   <!------Header-------->
    <v-app-bar elevation="0" height="70" class="bg-background top-header px-5">
        <div class="d-flex align-center justify-space-between w-100">
            <div>
                <v-btn class="hidden-lg-and-up text-muted" @click="sDrawer = !sDrawer" icon variant="flat" size="small">
                    <Icon icon="solar:hamburger-menu-outline" height="22"></Icon>
                </v-btn>
                <!-- Notification -->
                <LayoutFullVerticalHeaderNotificationDD/>
            </div>
            <div>
                <!-- Upgrade button -->
                <v-btn class="mr-2 bg-primary" rounded="pill" href="https://www.wrappixel.com/templates/materialm-vuetify-nuxt-js-admin-template/?ref=376#demos" target="_blank">Check Pro Template</v-btn>
                <!-- User Profile -->
                <LayoutFullVerticalHeaderProfileDD/>
            </div>
        </div>
    </v-app-bar>
  
</template>
