<script setup lang="ts">
import UiParentCard from '@/components/shared/UiParentCard.vue';
import DefaultText from '~/components/style-components/Default-Text.vue';
import Headings from '~/components/style-components/Headings.vue';

</script>

<template>
    <v-row>
        <v-col cols="12" md="12">
            <UiParentCard title="Basic Typography">
                    <Headings/>
            </UiParentCard>
            <UiParentCard title="Default Text" class="mt-6">
                    <DefaultText/>
            </UiParentCard>
        </v-col>
    </v-row>
</template>
