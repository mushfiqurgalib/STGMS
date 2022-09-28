<template>
  <nav class="navbar navbar-dark bg-dark navbar-expand fixed-top">
    <div class="container">



    <router-link to="/home" class="navbar-brand"> HOME </router-link>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ml-auto">

  
    
          <li class="nav-item">
            <router-link to="/adprofile" class="navbar-brand">PROFILE </router-link>
          </li>

           <li class="nav-item">
            <router-link to="/emplist" class="navbar-brand"> EMPLOYEE LIST</router-link>
          </li>

          <li class="nav-item">
            <router-link to="/flist" class="navbar-brand"> FARMER LIST</router-link>
          </li>

          <li class="nav-item">
            <router-link to="/adminpayslip" class="navbar-brand"> MONTHLY PAYSLIP </router-link>
          </li>

          <li class="nav-item">
            <router-link to="/adminyearlypayslip" class="navbar-brand"> YEARLY PAYSLIP</router-link>
          </li>

           <li class="nav-item">
            <router-link to="/download" class="navbar-brand"> APPLICATIONS</router-link>
          </li>



               <li class="nav-item">
            <router-link to="/sin" class="navbar-brand"> SET SALARY </router-link>
          </li>

        
                <li class="nav-item">
            <router-link to="/win" class="navbar-brand"> WAREHOUSE INSERT</router-link>
          </li>


          <li class="nav-item">
            <router-link to="/alltrans" class="navbar-brand">  HISTORY </router-link>
          </li>

          <li class="nav-item">
            <router-link to="/wreport" class="navbar-brand"> INVENTORY REPORT</router-link>
          </li>

          
          <li class="nav-item">
            <router-link to="/ssl" class="navbar-brand">SSL</router-link>
          </li>


        </ul>
      </div>
    </div>
  </nav>
  <!-- <nav class="navbar navbar-expand navbar-dark fixed-top">
      
    </nav > -->
</template>

<script>
export default {};
</script>


<style scoped>
.nav-item{
  font-weight: 700;
font-weight: bold; /* same as 700 */

font-weight: lighter; /* relative to the parent element */
}

.nav-bar{

}
</style>