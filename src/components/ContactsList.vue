<template>
  <div>
    <table>
      <thead>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Email</th>
      </thead>
      <tbody>
        <tr v-for= "(user,key) in users" :key="key">
        <td> {{user.firstName}} </td>
        <td> {{user.lastName}} </td>
        <td> {{user.email}} </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'ContactsList',
  data() {
   return{
     users: [
       {firstName: 'John', lastName: 'Doe', email: 'john@mail.com'},
       {firstName: 'Joan', lastName: 'Conol', email: 'joan@mail.com'},
       {firstName: 'Mike', lastName: 'Daglas', email: 'mike@mail.com'}
     ]
   }
  }
}
</script>
