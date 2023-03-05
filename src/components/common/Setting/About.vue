<script setup lang='ts'>
import { computed } from 'vue'
import { useAuthStore } from '@/store'

const authStore = useAuthStore()

const config = computed(() => authStore.config ?? {})
</script>

<template>
  <div class="p-4 space-y-4">
    <p>{{ $t("setting.api") }}：{{ config?.apiModel ?? '-' }}</p>
    <p>{{ $t("setting.reverseProxy") }}：{{ config?.reverseProxy ?? '-' }}</p>
    <p>{{ $t("setting.timeout") }}：{{ config?.timeoutMs ?? '-' }}</p>
    <p>{{ $t("setting.socks") }}：{{ config?.socksProxy ?? '-' }}</p>
  </div>
</template>
