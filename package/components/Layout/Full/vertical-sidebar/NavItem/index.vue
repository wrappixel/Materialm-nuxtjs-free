<script setup>
import { Icon } from '@iconify/vue';
const props = defineProps({ item: Object, level: Number });
</script>

<template>
    <!---Single Item-->
    <v-list-item
        :href="item.external ? item.to : undefined"
        :to="!item.external ? item.to : undefined"
        rounded
        class="mb-1"
        :disabled="item.disabled"
        :target="item.external === true ? '_blank' : undefined"
    >
        <!---If icon-->
        <template v-slot:prepend>
            <Icon :icon="'solar:' + item.icon" height="18" width="18" :level="level" class="dot" :class="'text-' + item.BgColor" />
        </template>
        <v-list-item-title
            >{{ item.title }}

            <span v-if="item.children">
                <span v-if="item.chip" class="ps-3">
                    <v-chip color="info" class=" hide-menu bg-lightinfo" size="x-small">
                        {{ item.chip }}
                    </v-chip>
                </span>
            </span>
        </v-list-item-title>
        <!---If Caption-->
        <v-list-item-subtitle v-if="item.subCaption" class="text-caption mt-n1 hide-menu">
            {{ item.subCaption }}
        </v-list-item-subtitle>
        <!---If any chip or label-->
        <template v-slot:append v-if="item.chip">
            <v-chip color="info" class=" hide-menu" size="x-small">
                {{ item.chip }}
            </v-chip>
        </template>
    </v-list-item>
</template>
