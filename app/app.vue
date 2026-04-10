<template>
  <div class="container">
    <h1>Greeting Form</h1>
    <form @submit.prevent="handleSubmit">
      <div class="field">
        <label for="firstName">First Name</label>
        <input id="firstName" v-model="firstName" type="text" placeholder="First name" />
      </div>
      <div class="field">
        <label for="lastName">Last Name</label>
        <input id="lastName" v-model="lastName" type="text" placeholder="Last name" />
      </div>
      <button type="submit" class="submit-btn">Submit</button>
    </form>
    <p v-if="submittedName" class="greeting">
      Hello {{ submittedName }}
    </p>
  </div>
</template>

<script setup lang="ts">
const firstName = ref('')
const lastName = ref('')
const submittedName = ref('')

function handleSubmit() {
  const fullName = `${firstName.value} ${lastName.value}`.trim()
  submittedName.value = fullName
}
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

.submit-btn {
  width: 100%;
  padding: 10px 16px;
  font-size: 16px;
  font-weight: 600;
  color: #fff;
  background-color: #3b82f6;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  transition: background-color 0.2s;
}

.submit-btn:hover {
  background-color: #2563eb;
}

.greeting {
  margin-top: 24px;
  font-size: 20px;
  font-weight: 500;
}
</style>
