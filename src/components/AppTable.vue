<template>

  <div class="table-container">
  <table>
    <thead>
    <tr>
      <td>First Name</td>
      <td>Last Name</td>
      <td>Address</td>
      <td>SSN</td>
    </tr>
    </thead>
    <tbody>
    <tr
        v-for="member in members"
        v-bind:key="member.ssn"
    >
      <td>{{member.firstName}}</td>
      <td>{{member.lastName}}</td>
      <td>{{member.address}}</td>
      <td>{{member.ssn}}</td>
    </tr>
    </tbody>
  </table>
  </div>
</template>


<script>
export default {
  name: "AppTable",
  data () {
    return {
      members: [],
    }
  },
  mounted() {
    fetch("http://localhost:8081/api/members")
        .then(res => res.json())
        .then(data => this.members = data)
        .catch(err => console.log(err.message))
  }
}
</script>

<style scoped>

table {
  width: 80%;
  height: 40%;
  border-spacing: 0;
  margin-bottom: 10px;
  padding-top: 10px;
  text-align: center;
  padding-right: 40px;
  padding-left: 10px;

}
td {
  padding: 3px 3px 3px 3px;
  outline: 1px solid black;
  text-align: center;
}

.table-container {
  background-color: white;
  width: 140%;
  height: 140%;
  align-content: center;
  text-align: left;
  margin-right: 20px;
  padding-right: 20px;
}

</style>