<template>
  <div>
    <Header />
  </div>
  <div>
    <Controller />
    <Geometry />
  </div>

</template>

<style>
</style>

<script>
import Geometry from "./components/Geometry";
import Controller from "./components/Controller";
import Header from "./components/Header";

export default {
  name: "My_Geometry_3D",
  components: {
    Header,
    Geometry,
    Controller,
  }
}
</script>