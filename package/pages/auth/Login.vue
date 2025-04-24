<script setup lang="ts">
import { LayoutFullLogo } from '#components';

/*-For Set Blank Layout-*/
definePageMeta({
  layout: "blank",
});
</script>
<template>
    <div class="authentication">
        <v-container fluid class="pa-3">
            <v-row class="h-100vh d-flex justify-center align-center">
                <v-col cols="12" class="d-flex align-center">
                    <div class="boxed-auth-wrap">
                        <v-card rounded="xl" elevation="10" class="px-sm-1 px-0  mx-auto index-2" max-width="450">
                            <v-card-item class="pa-sm-8">
                                <div class="d-flex justify-center mb-5">
                                    <LayoutFullLogo />
                                </div>
                              
                                <AuthLoginForm />
                                <h6 class="text-subtitle-1 font-weight-medium justify-center d-flex align-center mt-3">
                                    New to Materialm ?
                                    <v-btn variant="text" class="pl-0 text-primary text-body-1 font-weight-medium  opacity-1 pl-2" height="auto"
                                        to="/auth/register">Create an account</v-btn>
                                </h6>
                            </v-card-item>
                        </v-card>
                    </div>
                </v-col>
            </v-row>

        </v-container>
    </div>
</template>
