<template>
<div>
  <div class="sidenav">
        <div class="login-main-text">
            <h2>Application<br> Login Page</h2>
            <p>Login or register from here to access.</p>
        </div>
      </div>
      <div class="main">
        <div class="col-md-6 col-sm-12">
            <div class="login-form">
              <form @submit.prevent="handleSubmit">
                  <div class="form-group">
                    <label>Email Address</label>
                    <input type="text" class="form-control" placeholder="Email" v-model="login.email">
                  </div>
                  <div class="form-group">
                    <label>Password</label>
                    <input type="password" class="form-control" placeholder="Password" v-model="login.password">
                  </div>


                  <button type="submit" class="btn btn-black">Login</button>


                  <router-link to="register">
                  <button type="submit" class="btn btn-secondary">Register</button>
                  </router-link>

              </form>
            </div>
        </div>
      </div>
</div>
</template>
<script>
export default {
    name: 'login',
    data : function (){
        return{
            login: {
            email: '',
            password: ''
        }
        }
    },
    methods: {
        handleSubmit : function (){
                //console.log(this.login);
                this.$http.post('http://localhost:8090/api/auth/login', this.login).then(function (response) {
                     //console.log(response);
                    if(response.bodyText == '[]') {
                          //alert('Error'+response.bodyText);
                        swal("error", "THANK YOU!", "error");
                        } else {
                            localStorage.setItem("token",response.data.token);
                            this.$router.push('/admin');
                            location.reload();
                        }
                });
        }
    }
}
</script>

<style scoped>
body {
    font-family: "Lato", sans-serif;
}
.main-head{
    height: 150px;
    background: #FFF;
}
.sidenav {
    height: 100%;
    background-color: #000;
    overflow-x: hidden;
    padding-top: 20px;
}
.main {
    padding: 0px 10px;
}

@media screen and (max-height: 450px) {
    .sidenav {padding-top: 15px;}
}

@media screen and (max-width: 450px) {
    .login-form{
        margin-top: 10%;
    }

    .register-form{
        margin-top: 10%;
    }
}

@media screen and (min-width: 768px){
    .main{
        margin-left: 40%;
    }

    .sidenav{
        width: 40%;
        position: fixed;
        z-index: 1;
        top: 0;
        left: 0;
    }

    .login-form{
        margin-top: 80%;
    }

    .register-form{
        margin-top: 20%;
    }
}


.login-main-text{
    margin-top: 20%;
    padding: 60px;
    color: #fff;
}

.login-main-text h2{
    font-weight: 300;
}

.btn-black{
    background-color: #000 !important;
    color: #fff;
}
</style>
