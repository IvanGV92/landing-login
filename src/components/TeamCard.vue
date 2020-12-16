<template>
  <div class="col">
    <div class="card h-100">
      <img v-bind:src="member.imagen" class="card-img-top" alt="Foto Equipo" />
      <div class="card-body">
        
        <p class="card-text text-center font-weight-bold">
          <span>Team Member: </span>
          {{ member.codigo }}
        </p>
        <p class="card-text text-center  font-weight-bold">
          {{ member.rol }}
        </p>
        <p class="card-text text-center font-weight-bold">{{ member.nombre }}</p>
        <p class="card-text text-center">
          {{member.descripcion}}
        </p>
        
        
      </div>
      <div class="card-footer">
        <small class="text-muted">Last updated 3 mins ago</small>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TeamCard",
  props: ["member"],
};
</script>

<style scoped>
</style>
