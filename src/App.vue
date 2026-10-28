<script setup lang="ts">
import { onMounted } from 'vue'
import { storeToRefs } from 'pinia'
import { RouterLink, RouterView } from 'vue-router'
import { useDeliveryStore } from './store'
const store = useDeliveryStore()
const { approvedShare, offers, urgent } = storeToRefs(store)
onMounted(store.load)
</script>

<template><div class="shell"><aside><div class="brand">GigabitFlowEU<span>CONNECTIVITY PERMITS</span></div><nav><RouterLink to="/">Permit journeys</RouterLink><RouterLink to="/insights">System guidance</RouterLink></nav><div class="health"><i /> Java gigabit permit investment service connected</div></aside><main><header><div><span class="eyebrow">Accelerate fibre and 5G rollout through simpler permits</span><h1>Gigabit Permit Investment Desk</h1></div><button @click="store.addOffer">Add permit journey</button></header><section class="summary"><article><small>Permits ready</small><strong>{{ approvedShare }}%</strong><div class="bar"><span :style="{ width: `${approvedShare}%` }" /></div></article><article><small>Permit journeys tracked</small><strong>{{ offers.length }}</strong><p>Shared rollout view</p></article><article><small>High-priority gaps</small><strong>{{ urgent }}</strong><p>Needs attention</p></article></section><RouterView /></main></div></template>
