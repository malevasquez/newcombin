<template>
  <div>
    <v-form
    ref="form"
    v-model="valid"
    >
      <v-text-field
        v-model="firstName"
        :rules="firstNameRules"
        label="First Name"
        outlined
        required
      ></v-text-field>
      <v-text-field
          v-model="lastName"
          :rules="lastNameRules"
          label="Last Name"
          outlined
          required
      ></v-text-field>
      <v-text-field
          v-model="address"
          :rules="addressRules"
          label="Address"
          outlined
          required
      ></v-text-field>
      <v-text-field
          v-model="ssn"
          :rules="ssnRules"
          label="SSN"
          outlined
          required
      ></v-text-field>

    </v-form>

    <v-row align="center">
      <v-col align="center">
        <v-btn
            color="error"
            class="mr-4"
            rounded
            @click="reset"
        >
          Reset
        </v-btn>
        <v-btn
            :disabled="!valid"
            color="success"
            class="mr-4"
            rounded
            @click="validate"
        >
          Send
        </v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "AppForm",
  data (){
    return {
      valid: true,
      firstName: '',
      firstNameRules: [
        v => !!v || 'First name is required',
        v => (v && v.length > 1) || 'First name must be at least 2 characters long',
      ],
      lastName: '',
      lastNameRules: [
        v => !!v || 'Last name is required',
        v => (v && v.length > 1) || 'Last name must be at least 2 characters long',
      ],
      address: '',
      addressRules: [
        v => !!v || 'Address is required',
        v => (v && v.length > 1) || 'Address must be at least 2 characters long',
      ],
      ssn: '',
      ssns: [],
      ssnRules: [
        (v) => !!v || 'SSN is required',
        (v) => /\d{3}-\d{2}-\d{4}$/.test(v) || 'SSN must be valid',
      ],
    }
  },
  methods: {
    send() {
      if(!this.ssns.includes(this.ssn)) {
        this.ssns.push(this.ssn)
      }
      this.ssn = ''
    },
    reset() {
      this.$refs.form.reset()
    },
    validate () {
      this.$refs.form.validate()
    },

  }
}
</script>

<style scoped>
form {
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}

v-text-field {
  display: block;
  padding: 8px 4px;
  width: 100%;
  box-sizing: border-box;
  border: 1px solid black;
  margin: 4px 0;
}






</style>