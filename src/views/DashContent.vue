<template>
    <div class="col-10 p-0 " style="z-index: 2000">
       <nav class="navbar navbar-expand-md navbar-light bg-white text-dark navSty " style="height:60px;top:15px;">
            <div class="container-fluid">
                <a class="navbar-brand" href="#" >
                          <!-- <p style="font-size: 14px; line-height: 0px;"><b>xxxxxxxxxxxxxx</b></p>
                          <p style="font-size: 10px; line-height: 0px; ">Admin</p>
                          style="margin-left:820px;margin-top:25px" -->
                </a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarSupportedContent">
                
                </div>
                <div>
                    <!-- <button title="Notifications" class="btn btn-white text-dark"><i class="fas fa-bell"></i></button>
                    <button title="Fullscreen" class="btn btn-white text-dark"><i class="fas fa-expand"></i></button>
                    <router-link to="/about"><button title="About Us" class="btn btn-white text-dark"><i class="fa fa-info-circle text-secondary" aria-hidden="true"></i></button></router-link>
                    <router-link to="/about"><button class="btn btn-white text-dark"><i class="fas fa-ellipsis-v"></i></button></router-link> -->
                      
                       <div>
                         <table>
                           <tr>
                             <td>
                                  <p style="font-size: 14px; line-height: 0px;margin-right:40px;margin-top:22px"><b>xxxxxxxxxxxxxx</b></p>
                                  <p style="font-size: 10px; line-height: 0px;margin-right:40px ">Admin</p>

                             </td>
                             
                          
                             <td>
                              <router-link to="/"> <img
                                  src="data:image/jpeg;base64,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"
                                  alt="profile"
                                  class="rounded-circle overflow-hidden avatar-image"
                                /></router-link>
                              </td>
                            </tr>
                        </table>
                      </div>
 

 
                </div>
            </div>
        </nav>
        <div class="p-5 dash-content overflow-auto" >
            <router-view/>
        </div>
    </div>
</template>

<script>

export default {
  
}
</script>


<style scoped>
.dash-content{
  height: calc(100vh - 80px);
}
.navSty{
  border-radius:15px;
  z-index: 2000;
  margin-left:4%;
  margin-right:4%;
  /* border: 1px solid black;
  background-color: aqua; */
  
}
.avatar-image {
    width: 40px;
    height: 40px;
    
}
 
</style>