<template>
<v-app>
<div class ="Background">
<v-container class="content" id="container">
          <img src="./assets/monitra-favicon.png" class="logo" alt="" />
          <header id="head">Login</header>
          <v-text-field
            id="field"
            label="User Name"
            solo
            
            append-icon="mdi-account" 
          ></v-text-field>
       
     
          <v-text-field
            id="field1"
            :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
           
            :type="show2 ? 'text' : 'password'"
            name="input-10-2"
            label="Password"
            hint="At least 8 characters"
           
            class="input-group--focused"
            @click:append="show2 = !show2"
            solo
          >
          
        </v-text-field>
        
            <v-btn
      class="ma-2"
      id="button"
      :loading="loading4"
      :disabled="loading4"
      color="info"
      @click="loader = 'loading4'"
      large
    >
      Login
      <template v-slot:loader>
        <span class="custom-loader">
          <v-icon color="white">mdi-cached</v-icon>
        </span>
      </template>
    </v-btn>

</v-container>

</div>
  
</v-app>
</template>

<script>
 export default {
  
  
    data () {
      return {
        name: 'login',
        show2: true,
        password: 'Password',
         loader: null,
        loading4:false,

      }
    },
    watch: {
      loader () {
        const l = this.loader
        this[l] = !this[l]

        setTimeout(() => (this[l] = false), 6000)

        this.loader = null
      },
    },
 }
    


</script>

<style >
.Background{

 background: url('./assets/ecg1.jpg');
  height: 100vh;
  background-size: cover;
  background-position: center;
  
}
.Background:after{
  position: absolute;
  content: '';
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: rgba(0,0,0,0.8);
}
#button{
  width: 90%;
}
#field {

    width: 60%;
}

.custom-loader {
    animation: loader 1s infinite;
    display: flex;
  }
  @-moz-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-webkit-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-o-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  .content{
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 999;
  text-align: center;
  padding: 60px 32px;
  width: 10px;
  transform: translate(-50%,-50%);
  background: rgba(255,255,255,0.04);
  box-shadow: -1px 4px 28px 0px rgba(0,0,0,0.75);
}
.content header{
  color: white;
  font-size: 33px;
  font-weight: 600;
  margin: 0 0 35px 0;
  font-family: 'Montserrat',sans-serif;
}
#container{
  width: auto;
  height:auto;
  
}
#head{
  margin-top: 10%;
}
.logo{

  margin-left: 80%;
  margin-top: 1%;
  height: 65px;
  width: 65px;
}

</style>
<style scoped>
 .v-text-field{
      width: 330px;
      
 }
</style>
