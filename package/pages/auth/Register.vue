<script setup lang="ts">
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
                                
                                <AuthRegisterForm />
                                <h6 class="text-subtitle-1 d-flex justify-center align-center mt-3 font-weight-medium">
                                    Already have an Account?
                                    <v-btn variant="text" to="/auth/login"
                                        class="text-primary text-body-1 opacity-1 font-weight-medium pl-2">Sign In</v-btn>
                                </h6>
                            </v-card-item>
                        </v-card>
                    </div>
                </v-col>
            </v-row>
        </v-container>
    </div></template>
