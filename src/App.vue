<template>
  <div id="app">
    <ContactsList />
    <PropsExample
    :message="message"
    @notify-parent="handleNotifyParent"
    />
  </div>
</template>

<script>
import ContactsList from './components/ContactsList.vue'
import PropsExample from './components/PropsExample.vue'

export default {
  name: 'app',
  components: {
    ContactsList,
    PropsExample
  },
  data(){
    return{
      message: "Hello"
    }
  },
  created(){
    setTimeout(() => {
      this.message="new Message"
    }, 3000)
  },
  methods:{
    handleNotifyParent(message){
      this.message=message
    }
  }
}
</script>

<style>
#app {

}
</style>
