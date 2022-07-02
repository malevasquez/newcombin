<template>
  <div class="form-container">
    <v-row>
      <v-col>
        <v-form
            ref="form"
            v-model="valid"
        >
          <v-text-field
              v-model="formData.firstName"
              :rules="firstNameRules"
              label="First Name"
              outlined
              required
          ></v-text-field>
          <v-text-field
              v-model="formData.lastName"
              :rules="lastNameRules"
              label="Last Name"
              outlined
              required
          ></v-text-field>
          <v-text-field
              v-model="formData.address"
              :rules="addressRules"
              label="Address"
              outlined
              required
          ></v-text-field>
          <v-text-field
              v-model="formData.ssn"
              :rules="ssnRules"
              label="SSN"
              outlined
              required
          ></v-text-field>

        </v-form>
      </v-col>
      <v-col>
      </v-col>
    </v-row>

    <v-row>
      <v-col class="ml-lg-16" >
        <div class="buttons">
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
            @click="send"
        >
          Send
        </v-btn>
        </div>
      </v-col>
      <v-col>
      </v-col>
    </v-row>
  </div>
</template>

<script>


import axios from "axios";

export default {

  name: "AppForm",

  data (){
    return {
      formData: {
        firstName: '',
        lastName: '',
        address: '',
        ssn: ''
      },
      ssns: [],
      valid: true,
      firstNameRules: [
        v => !!v || 'First name is required',
        v => (v && v.length > 1) || 'First name must be at least 2 characters long',
      ],
      lastNameRules: [
        v => !!v || 'Last name is required',
        v => (v && v.length > 1) || 'Last name must be at least 2 characters long',
      ],
      addressRules: [
        v => !!v || 'Address is required',
        v => (v && v.length > 1) || 'Address must be at least 2 characters long',
      ],
      ssnRules: [
        (v) => !!v || 'SSN is required',
        (v) => /^\d{3}-\d{2}-\d{4}$/.test(v) || 'SSN must be valid',
        (v) => !this.ssns.includes(v) || 'SSN must be unique',
      ],
    }
  },
  methods: {
    reset() {
      this.$refs.form.reset()
    },
    async send () {
      this.$refs.form.validate();
      this.ssns.push(this.formData.ssn)
      await axios.post("http://localhost:8081/api/members", this.formData)
          .catch(err => console.log(err.message))
    },
  }
}
</script>

<style scoped>
form {
  width: 180%;
  margin: auto 35px;
  background: white;
  border-radius: 10px;
  text-align: center;
  align-content: center;
}

v-text-field {
  display: block;
  width: 100%;
  box-sizing: border-box;
  border: 1px solid black;
  text-align: center;
}

.buttons {
  text-align: center;
  padding-left: 90px;
  margin-bottom: 100px;
  float: left;
  display:inline-flex;
}

.form-container {
  background-color: white;
  width: 100%;
  height: 90%;
  align-content: center;
  text-align: left;
  margin-top: 10px;
  margin-bottom: 10px;
  margin-right: 20px;
  padding-right: 20px;
}


</style>