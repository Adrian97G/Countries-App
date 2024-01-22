<script setup lang="ts">
import { defineProps } from 'vue';
import { Country } from "../models/country.models";
import CountryItem from "../components/CountryItem.vue"

interface Props {
  countries: Country[];
}

defineProps<Props>();
</script>

<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3">
    <div v-for="(country, index) in countries" :key="index" class="border border-white border-2 rounded p-5"
    >
      <CountryItem :country="country" />
    </div>
  </div>
</template>
