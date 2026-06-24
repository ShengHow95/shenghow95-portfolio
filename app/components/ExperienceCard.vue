<template>
  <div class="terminal-card experience-card">
    <div class="card-header">
      <div class="header-row">
        <span class="duration font-mono">{{ duration }}</span>
        <h3 class="role">{{ role }}</h3>
        <div class="company font-mono">@{{ company }} // {{ location }}</div>
      </div>
    </div>
    <ul v-if="responsibilities && responsibilities.length" class="responsibilities">
      <li v-for="(item, index) in responsibilities" :key="index">> {{ item }}</li>
    </ul>
  </div>
</template>

<script setup>
defineProps({
  role: String,
  company: String,
  duration: String,
  location: String,
  responsibilities: {
    type: Array,
    default: () => []
  }
})
</script>

<style scoped>
.experience-card {
  margin-bottom: 1.5rem;
  background: var(--color-surface);
  border: 1px solid rgba(255, 255, 255, 0.05);
  border-left: 2px solid var(--color-primary);
  border-radius: var(--radius-sm);
  transition: var(--transition);
}
.experience-card:hover {
  border-left-color: var(--color-terminal);
  background: var(--color-surface-hover);
}
.card-header {
  padding: 1rem;
  border-bottom: 1px dashed rgba(255, 255, 255, 0.1);
}
@media (min-width: 768px) {
  .card-header {
    padding: 1.5rem;
  }
}
.header-row {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0.4rem;
}
.role {
  color: var(--color-text);
  margin-bottom: 0.25rem;
  font-size: 1.1rem;
  margin: 0;
}
.company {
  color: var(--color-primary);
  font-size: 0.85rem;
  word-break: break-word;
  overflow-wrap: break-word;
}
.duration {
  font-size: 0.7rem;
  color: var(--color-text-muted);
  background: rgba(255, 255, 255, 0.05);
  padding: 0.2rem 0.45rem;
  border-radius: var(--radius-sm);
  white-space: nowrap;
}
.responsibilities {
  list-style-type: none;
  padding: 1rem;
  margin: 0;
}
@media (min-width: 768px) {
  .responsibilities {
    padding: 1.5rem;
  }
}
.responsibilities li {
  margin-bottom: 0.5rem;
  color: var(--color-text-muted);
  font-family: var(--font-mono);
  font-size: 0.85rem;
}
</style>
