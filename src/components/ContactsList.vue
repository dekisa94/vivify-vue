<template>
  <div>
    <table>
      <thead>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Email</th>
      </thead>
      <tbody>
        <tr v-for= "(contact,key) in contacts" :key="key" v-if="contact.firstName==='John'">
        <td> {{contact.firstName}} </td>
        <td> {{contact.lastName}} </td>
        <td> {{contact.email}} </td>
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
     contacts: [
       {firstName: 'John', lastName: 'Doe', email: 'john@mail.com'},
       {firstName: 'Joan', lastName: 'Conol', email: 'joan@mail.com'},
       {firstName: 'Mike', lastName: 'Daglas', email: 'mike@mail.com'}
     ]
   }
  }
}
</script>
