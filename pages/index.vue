<template>
  <div> 
    <loginComponent :id="userRobert.id" />
  </div>
</template>

<script>

import Customer from '~/components/userpanel/customer.js';
import LoginJS from '~/components/userpanel/login.js';
import loginComponent from '~/components/userpanel/loginComponent.vue';

export default {
  name: 'IndexPage',

  components: { loginComponent },

  data(){
    return{
      userRobert: null
    }
  },

  created(){
    this.person()
    this.userRobert = this.login("12345","kielbaaaa")
  },

  methods:{

    person() {
       let oneperson = new Customer("robert","200","25");
       let secondperson = {
          name: "Agata",
          age: 17,
          school: true
       }
       console.log(oneperson)
       console.log(secondperson)
    },

    login(id, password){
      return new LoginJS(id, password);
    }
    
  }

}
</script>

<style scoped>
@import "@/assets/css/index.css";

</style>
