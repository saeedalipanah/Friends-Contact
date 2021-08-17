<template>
  <form @submit.prevent="submitData">
    <div>
      <label>Name:</label>
      <input v-model="enteredName" type="text" />
    </div>
    <div>
      <label>Number:</label>
      <input v-model="enteredPhone" type="number" />
    </div>
    <div>
      <label>Email:</label>
      <input v-model="enteredEmail" type="email" />
    </div>
    <button>Add Contact</button>
  </form>
</template>

<script>
export default {
  emits: ["add-contacts"],
  data() {
    return {
      enteredName: "",
      enteredPhone: "",
      enteredEmail: "",
    };
  },
  methods: {
    submitData() {
      this.$emit(
        "add-contacts",
        this.enteredName,
        this.enteredPhone,
        this.enteredEmail
      );
    },
  },
};
</script>

<style>
form {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 1rem auto;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
  width: 90%;
  max-width: 40rem;
}

input {
  font: inherit;
  padding: 1rem;
}
label {
  font-weight: bold;
  margin-right: 1rem;
  width: 7rem;
  display: inline-block;
}
div {
  margin: 1rem;
}
</style>
