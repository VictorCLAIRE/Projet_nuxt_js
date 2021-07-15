<template>
    <div class="card col-3" style="width: 18rem;">
      <div class="card-body">
        <h5 class="card-title">{{nom}}</h5>
        <h6 class="card-title">{{ingredients}}</h6>
      </div>
    </div>
</template>

<script>
export default {
  name: "Produit",
  props: ["nom","ingredients"]
}
</script>


