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
    <tr class="noBorder"
        v-for="member in members"
        v-bind:key="member.ssn"
    >
      <td class="noBorder">{{member.firstName}}</td>
      <td class="noBorder">{{member.lastName}}</td>
      <td class="noBorder">{{member.address}}</td>
      <td class="noBorder">{{member.ssn}}</td>
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
  border: 1px solid black;

}
td {
  padding: 3px 3px 3px 3px;
  text-align: center;
  border: 1px solid black;
}

td.noBorder {
  border-bottom: 0;
  border-top: 0;
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