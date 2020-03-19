<template>
  <section>
    <nav class="navbar navbar-expand-lg navbar-light bg-light" style="box-shadow: 1px 3px 6px #8888">
      <a class="navbar-brand" href="#">اپ من</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          
        </ul>
        <form class="form-inline my-2 my-lg-0">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
        </form>
      </div>
    </nav>
    <div class="container-fluid">
      <div class="row flex-xl-nowrap py-md-3">
        <div class="col-md-3 col-xl-3 ">
          منو
          <ul class="nav flex-column nav-pills py-md-3">
            <li class="nav-item" v-for="item in items" :key="item.id">
              <nuxt-link  class="nav-link" :active-class="($nuxt.$route.path == item.href) ? 'active': ''" :to="item.href">{{item.text}}</nuxt-link>
            </li>            
          </ul>
        </div>
        <div class="col-md-9 col-xl-9 py-md-3 pl-md-5">
          <nuxt />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data(){
    return {
      items:[
        {id:0, icon:"fa-dolar",text:"قیمت دلار", href:"/"},
        {id:1, icon:"fa-gold",text:"قیمت طلا", href:"/gold"},
      ]
    }
  }
}
</script>