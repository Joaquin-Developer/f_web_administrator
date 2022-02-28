<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Administrador</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarScroll"
        aria-controls="navbarScroll"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarScroll">
        <ul
          class="navbar-nav me-auto my-2 my-lg-0 navbar-nav-scroll"
          style="--bs-scroll-height: 100px"
        >
          <li class="nav-item">
            <router-link :to="'/'">
              <a class="nav-link active" aria-current="page" href="#">Listar</a>
            </router-link>
          </li>
          <li class="nav-item">
            <router-link :to="'/update'">
              <a class="nav-link active" aria-current="page" href="#"
                >Actualizar</a
              >
            </router-link>
          </li>
          <li class="nav-item">
            <router-link :to="'/create'">
              <a class="nav-link active" aria-current="page" href="#">Añadir</a>
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>


<script>
export default {
  name: "NavbarComponent",
};
</script>