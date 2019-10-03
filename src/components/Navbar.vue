<template>
<div id="nav-bar">
        <nav class="navbar navbar-expand-lg navbar-light bg-light border-bottom shadow">
        <span  @click="toggler" id="navbar-icon"><i class="fa fa-bars"></i></span>
        <a class="navbar-brand ml-2  display-1" href="#">Navbar</a>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav  mt-2  mt-lg-0">
            <li class="nav-item ">
              <a class="nav-link" href="#">Dashboard</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Tasks</a>
            </li>
            <li class="nav-item ">
              <a class="nav-link" href="#">
                Configurations
              </a>
            </li>
          </ul>

    <div class="ml-auto mr-4">
         <span class="mr-1">
        <img src="../assets/logo.png" alt="">
      </span>
     <a class="text-black mr-1">John Doe</a>
</div>
        </div>
      </nav>
     <div class="d-flex" id="page-content-wrapper">
    <!-- /#sidebar-wrapper -->
    <div class="bg-light border-right" id="sidebar-wrapper" v-show="toggle">
      <div class="list-group list-group-flush">
        <a href="#" class="list-group-item list-group-item-action bg-light">Dashboard</a>
        <a href="#" class="list-group-item list-group-item-action bg-light">Shortcuts</a>
        <a href="#" class="list-group-item list-group-item-action bg-light">Overview</a>
        <a href="#" class="list-group-item list-group-item-action bg-light">Events</a>
        <a href="#" class="list-group-item list-group-item-action bg-light">Profile</a>
        <a href="#" class="list-group-item list-group-item-action bg-light">Status</a>
      </div>
    </div>
      <div class="container-fluid ml-auto mt-4">
        <h1 class="mt">Simple Sidebar</h1>
        <p>The starting state of the menu will appear collapsed on smaller screens, and will appear non-collapsed on larger screens. When toggled using the button below, the menu will change.</p>
        <p>Make sure to keep all page content within the <code>#page-content-wrapper</code>. The top navbar is optional, and just for demonstration. Just create an element with the <code>#menu-toggle</code> ID which will toggle the menu when clicked.</p>
      </div>

    </div>
     
    <!-- /#page-content-wrapper -->
  </div>
  <!-- </div> -->
</template>
<script>
export default {
    name:'nav-bar',
    data(){
        return {
            toggle : true,
        }
    },
    methods:{
        toggler(){
            this.toggle = !this.toggle
        }
}
};
</script>
<style scoped>
#sidebar-wrapper {
  min-height: 100vh;
  margin-left: -15rem;
  -webkit-transition: margin .25s ease-out;
  -moz-transition: margin .25s ease-out;
  -o-transition: margin .25s ease-out;
  transition: margin .25s ease-out;
}
#sidebar-wrapper .sidebar-heading {
  padding: 0.875rem 1.25rem;
  font-size: 1.2rem;
}

#sidebar-wrapper .list-group {
  width: 15rem;
}

#page-content-wrapper {
  max-width: 100vw;
}

#wrapper.toggled #sidebar-wrapper {
  margin-left: 0;
}
#navbar-icon:hover {
    cursor: pointer;
}
img{
  max-height: 50px;
  border: 2px solid white;
  display: inline;
  border-radius: 50%;
}
@media (min-width: 768px) {
  #sidebar-wrapper {
    margin-left: 0;
  }

  #page-content-wrapper {
    min-width: 0;
    width: 100%;
  }

  #wrapper.toggled #sidebar-wrapper {
    margin-left: -15rem;
  }
}
</style>