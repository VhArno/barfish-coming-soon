<script setup lang="ts">
defineProps<{
  label: string
  type: string
  autocomplete: string
}>()
</script>

<template>
  <div class="input-container">
    <label :for="type" class="input-label">{{ label }}</label>
    <input :type="type" :id="type" :name="type" :autocomplete="autocomplete" class="styled-input" />
  </div>
</template>

<style lang="css" scoped>
.input-container {
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
  gap: 0.5rem;
  max-width: 35rem;
}

.input-label {
  font-size: 1rem;
  font-weight: 600;
}

.styled-input {
  padding: 0.5rem;
  font-size: 1rem;
  border: 2px solid #ccc;
  border-radius: 6px;
  background-color: #f9f9f9;
  transition:
    border-color 0.3s ease,
    box-shadow 0.3s ease;
  width: 100%;
}

.styled-input:focus {
  outline: none;
  border-color: #6c63ff;
  box-shadow: 0 0 8px rgba(108, 99, 255, 0.4);
}

.styled-input:hover {
  border-color: #bbb;
}

.styled-input::placeholder {
  color: #aaa;
}
</style>
