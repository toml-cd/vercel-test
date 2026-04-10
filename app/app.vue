<template>
  <div class="container">
    <h1>Greeting Form</h1>
    <form @submit.prevent>
      <div class="field">
        <label for="firstName">First Name</label>
        <input id="firstName" v-model="firstName" type="text" placeholder="First name" />
      </div>
      <div class="field">
        <label for="lastName">Last Name</label>
        <input id="lastName" v-model="lastName" type="text" placeholder="Last name" />
      </div>
    </form>
    <p v-if="firstName || lastName" class="greeting">
      Hello {{ firstName }} {{ lastName }}
    </p>
  </div>
</template>

<script setup lang="ts">
const firstName = ref('')
const lastName = ref('')
</script>

<style scoped>
.container {
  max-width: 400px;
  margin: 60px auto;
  font-family: sans-serif;
}

.field {
  display: flex;
  flex-direction: column;
  margin-bottom: 16px;
}

label {
  margin-bottom: 4px;
  font-weight: 600;
}

input {
  padding: 8px 12px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 6px;
}

.greeting {
  margin-top: 24px;
  font-size: 20px;
  font-weight: 500;
}
</style>
