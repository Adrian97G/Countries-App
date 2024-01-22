<script setup lang="ts">
import { defineProps } from 'vue';
import { Country } from "../models/country.models";

interface Props {
    country: Country;
}

defineProps<Props>();
</script>


<template>
    <div class="h-56 sm:h-36">
        <img class="h-56 sm:h-36 w-full"
        :src="country.flags.png"
        :alt="country.flags.alt">
    </div>
    <h4 class="text-x1 font-bold text-black-500">{{ country.name.common }}</h4>
    <p class="text-sm text-black-400">
        Capital:
        <span v-for="capital in country.capital" :key="capital" class="font-bold">{{
        capital
        }}
        <template>, </template>
    </span>
    </p>
    <p class="text-sm text-black-400">
        Population:
        <span class="font-bold"></span>{{ country.population?.toLocaleString() }}
    </p>
    <p class="text-sm text-black-400">
        Region:
        <span class="font-bold"></span>{{ country.region }}
    </p>
</template>