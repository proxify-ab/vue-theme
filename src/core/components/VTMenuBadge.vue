<script setup lang="ts">
import { computed } from 'vue'
import { MenuBadgeItem } from '../../core'

const props = defineProps<{ item: string | MenuBadgeItem }>()

const text = computed(() => typeof props.item === 'string' ? props.item : props.item.text)
const type = computed(() => typeof props.item === 'string' ? 'primary' : (
  props.item.type || 'primary'
))

</script>

<template>
  <span class="vt-menu-badge" :class="type">{{ text }}</span>
</template>
