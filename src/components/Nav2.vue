<template>
  <nav class="navbar navbar-dark bg-dark navbar-expand fixed-top">
    <div class="container">



      <router-link to="/home2" class="navbar-brand"> HOME </router-link>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ml-auto">

<!--   
          <li class="nav-item">
            <router-link to="/about" class="navbar-brand"> ABOUT US</router-link>
          </li> -->

          <li class="nav-item">
            <router-link to="/gallery" class="navbar-brand">
              GALLERY
            </router-link>
          </li>

          <li class="nav-item">
            <router-link to="/profilepage" class="navbar-brand">PROFILE </router-link>
          </li>

          <li class="nav-item">
            <router-link to="/payslip" class="navbar-brand"> MONTHLY PAYSLIP </router-link>
          </li>

          <li class="nav-item">
            <router-link to="/ypayslip" class="navbar-brand"> YEARLY PAYSLIP</router-link>
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
font-weight: normal; /* same as 400 */
font-weight: lighter; /* relative to the parent element */
}
</style>