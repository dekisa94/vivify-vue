<template>
    <div>
        <div>
            {{message}}
        </div>
        <div>
            {{reversedMessage}}
        </div>
        <input type="text" v-model="searchTerm" />
        <button @click="notifyParent">Notify parent</button>
    </div>
</template>

<script>
export default {
  props:['message'],
  data(){
      return{
          searchTerm: ''
      }
  },
  methods:{
      notifyParent(){
          this.$emit('notify-parent', 'Hello from child!')
      }
  },
  computed:{
    reversedMessage(){
      return this.message.split('').reverse().join('')
    }
  },
  watch:{
      searchTerm(newValue, oldValue){
          console.log('New value:', newValue)
          console.log('Old Value:', oldValue)
      }
  }
}
</script>

