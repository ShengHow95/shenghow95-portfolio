<template>
  <span class="badge">
    {{ name }}
  </span>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true
  }
})
</script>

<style scoped>
.badge {
  display: inline-flex;
  align-items: center;
  padding: 0.4rem 0.8rem;
  border-radius: var(--radius-sm);
  font-family: var(--font-mono);
  font-size: 0.75rem;
  font-weight: 500;
  background: rgba(88, 166, 255, 0.1);
  color: var(--color-primary);
  border: 1px solid rgba(88, 166, 255, 0.3);
  transition: var(--transition);
}
.badge:hover {
  background: rgba(88, 166, 255, 0.2);
  border-color: var(--color-primary);
  box-shadow: 0 0 10px var(--color-primary-glow);
  transform: translateY(-2px);
}
</style>
