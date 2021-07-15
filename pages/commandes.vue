<template>
  <div>
    <h1 class="m-1">Commandes</h1>
    <h2>Produits disponibles:</h2>
    <div class="row">
      <div v-for="produit in produits" class="card col-3" style="width: 18rem;">
        <div class="card-body">
          <h5 class="card-title">{{produit.nom}}</h5>
          <h6 class="card-title">Ingrédients:</h6>
            <ul v-for="ingredient in produit.ingredients" class="list-group list-group-flush">
              <li class="list-group-item">{{ingredient.name}}</li>
            </ul>
          <button class="btn btn-success m-2 txt-center" @click="commandePlus(commandes, produit.nom, produit.ingredients)" >Ajouter</button>
        </div>
      </div>
    </div>
    <h2>Produits commandés:</h2>
    <div class="row">
      <div v-for="commande in commandes" class="card col-3" style="width: 18rem;">
        <div class="card-body">
          <h5 class="card-title">{{commande.nom}}</h5>
          <h6 class="card-title">Ingrédients:</h6>
          <ul v-for="ingredient in commande.ingredients" class="list-group list-group-flush">
            <li class="list-group-item">{{ingredient.name}}</li>
          </ul>
          <button class="btn btn-danger m-2 txt-center" @click="commandeMoins(produits, commande.nom, commande.ingredients)" >Retirer</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Produit from "../components/Produit";
export default {
  components:{
    Produit,
  },
  data(){
    return{
      produits:[
        {nom: 'Chorizo',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Chorizo"}
          ]
        },
        {nom: 'Forestière',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Champignon"}
          ]},
        {nom: 'Acnhois',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Anchois"}
          ]},
        {nom: 'Saumon',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Saumon"}
          ]},
        {nom: 'Végétarienne',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Aubergine"}
          ]},
        {nom: 'Calzone',
          ingredients:[
            {name:"Sauce tomate"},
            {name:"Fromages"},
            {name:"Oeuf"}
          ]},
        {nom: 'Comté',
          ingredients:[
            {name:"Sauce tomate"},
            {name: "Fromages"},
            {name:"Comté"}
          ]},
      ],
      commandes:[
      ]
    }
  },
  methods:{
    commandePlus(commandes, nom, ingredients){
      this.commandes.push({
        nom: nom,
        ingredients: ingredients
      });
    },
    commandeMoins(commandes, nom, ingredients){
      this.commandes.splice({
        nom: nom,
        ingredients: ingredients
      });
    },
  },
  mounted() {
    console.log("Le tablau des commandes : " + this.commandes)
  }
}
</script>


