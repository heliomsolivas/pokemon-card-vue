<template>
<div class="w-cards">
	<div v-for="pokemon in pokemons" class="card">
	<h1>{{pokemon.name}}</h1>
	<!-- <img v-bind:src="pokemon.foto" v-bind:alt="pokemon.name"> -->
	<!-- <p>{{pokemon.descricao}}</p> -->
</div>
</div>
</template>

<script>

import axios from 'axios'

export default {
	data() {
		return {
			pokemons: {

			},
		}
	},

  	created: function() {
  		this.buscaPokemons();
  	},

  	methods: {
  		buscaPokemons: function(){
  			var vm = this;
  			axios.get('http://pokeapi.co/api/v2/pokemon')
  			.then(function(res){
  				console.log(res);
  				console.log(res.data.results);
  				vm.pokemons = res.data.results;
  			})
  			.catch(function(err){
  				console.log(err);
  			})
  		}
  	},
  }
</script>

<style scoped>
.w-cards{
	max-width: 1170px;
	margin: 0 auto;
	display: flex;
	justify-content:space-between;
	flex-wrap:wrap;
}
	.card{
		border:1px solid black;
		border-radius: 10px;
		padding: 10px 20px;
		height: 450px;
	}
	img{
		max-width: 100%;
		display: block;
	}
	h1{
		font-size: 20px;
	}
	p{
		font-size: 16px;
	}
</style>
