<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
      <a class="navbar-brand" href="#">Star Wars <small class="text-secondary">Nuxt Optimized</small></a>
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
          <li class="nav-item active">
            <nuxt-link :to="{ name: 'index' }" class="nav-link" href="#">
              Home
            </nuxt-link>
          </li>
          <li class="nav-item">
            <nuxt-link :to="{ name: 'about' }" class="nav-link" href="#">
              About
            </nuxt-link>
          </li>
          <li class="nav-item">
            <a v-b-modal.modalLogin class="nav-link" href="#">Login</a>
          </li>
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
    </div>
  </nav>
</template>