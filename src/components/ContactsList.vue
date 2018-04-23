<template>
  <div>
    <form @submit.prevent="add">
      <label>First Name</label>
      <input v-model="newContact.firstName" type="text" placeholder="First Name"/>
      <label>Last Name</label>
      <input v-model="newContact.lastName" type="text" placeholder="Last Name"/>
      <label>Email</label>
      <input v-model="newContact.email" type="text" placeholder="Email"/>
      <button type="submit">Add Contact</button>
    </form>
    <table>
      <thead>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Email</th>
      </thead>
      <tbody>
        <tr v-for= "(contact,key) in contacts" :key="key">
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
     ],
     newContact:{
       firstName:'',
       lastName:'',
       email:''
     }
   }
  },
  methods:{
    add(){
      this.contacts.push(this.newContact)
      this.newContact={}
    }
  }
}
</script>
