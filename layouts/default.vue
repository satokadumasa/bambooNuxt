<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-12 nav">
          <ul>
            <li>
              <router-link to="/">Home</router-link>
            </li>
            <li>
              <router-link to="/users">Users</router-link>
            </li>
          </ul>
        </div>
        <div class="col-12">
          <Nuxt />
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.nav {
  position: relative;
  list-style: none;
}
.nav ul {
  margin-left: 3px;
  margin-right: 3px;
}
.nav li {
  width: 140px;
  text-align: center;
  background-color: #333;
  height: 50px;
  line-height: 50px;
  /* margin-right: 2px; */
  display: inline-block;
}

.nav li a {
  text-decoration: none;
  color: #fff;
  font-weight: bold;
  padding: 5px;
}

.detail_table {
  border-top: 1px solid gray;
  border-left: 1px solid gray;
}
.detail_label {
  border-bottom: 1px solid gray;
  border-right: 1px solid gray;
  background-color: blue;
  color: #fff;
}
.detail_val {
  border-bottom: 1px solid gray;
  border-right: 1px solid gray;
}
</style>
