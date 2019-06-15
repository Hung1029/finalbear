<template>
  <div class="login">
      <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
      <link rel="stylesheet" href="../firebase">
      <b-container class="bv-example-row">
<b-row>
    <b-col cols="4"></b-col>
    <b-col cols="4"><img src="../img/47c.jpg.png" alt=""></b-col>
    <b-col cols="4"></b-col>
</b-row>

<b-row>
    <b-col cols="4"></b-col>
    <b-col cols="4">
        <h1 id="topic">Login Page</h1>
</b-col>
<b-col cols="4"></b-col>


  </b-row>

<b-row>
<b-col cols="4"></b-col>
<b-col cols="4">

<form @submit.prevent="login">
      <input type="text" v-model="email" placeholder="Email"><br>
    <input type="password" v-model="password" placeholder="Password"><br>
      <br>
      <button @click="login">Login</button>
      <br>
      <button @click="LoginWithGoogle" class="btn btn-bg btn-lg btn-block">Login With Google</button>
      <br>
      <br>
      <p>You don't have an account ? You can <router-link to="/signup">create one</router-link></p>
    </form>

</b-col>
<b-col cols="4"></b-col>


  </b-row>


    
    </b-container>
    <!-- <form @submit.prevent="login">
      <label>User Name</label>
      <input type="text" v-model="userName" required>
      <br>
      <label>Password</label>
      <input type="password" v-model="password" required>
      <br>
      <button type="submit">Log In</button>
    </form> -->
  </div>
</template>
<script>
import firebase from 'firebase'
  export default {
      name:'login',

    data () {
      return {
        email: "",
        password: "",
        errors:[],
        loading:false,
        user:""
      }
    },
    methods: {  
        async LoginWithGoogle(){
            this.loading=true;
            this.errors=[];
            try{
                let response = await firebase
                .auth()
                .signInWithPopup(new firebase.auth.GoogleAuthProvider());
                this.user=response.user;
                this.$router.push('/');
            }catch(error){
                this.errors.push(error.message);
                this.loading=false;
            }
        },
        login: function() {
        firebase.auth().signInWithEmailAndPassword(this.email, this.password).then(
          (user) => {
              
            this.$router.replace('/')
          },
          (err) => {
            alert('Oops. ' + err.message)
          }
        );
        }
    }
  }
</script>

<style scoped>
.login {
    margin-top: 40px;
  }
  input {
    margin: 10px 0;
    padding: 15px;
  }
  button {
    margin-top: 20px;
    cursor: pointer;
  }
  p {
    margin-top: 40px;
    font-size: 13px;
  }
  p a {
    text-decoration: underline;
    cursor: pointer;
  }
#topic{
    color:#B50943;
    font-size:3vw;
    font-family:'Arial';
}
</style>
