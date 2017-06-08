<template>
<div>
	<div v-for="pokemon in pokemons" class="card">
	<h1>{{pokemon.nome}}</h1>
	<img v-bind:src="pokemon.foto" v-bind:alt="pokemon.nome">
	<p>{{pokemon.descricao}}</p>
</div>
</div>
</template>

<script>

//Standard Directives

export default {
  data() {
  	return {
    	pokemons: [
    		{ nome: "Bulbasaur" , descricao: "Bulbasaur can be seen napping in bright sunlight. There is a seed on its back. By soaking up the sun's rays, the seed grows progressively larger.", foto: "http://assets.pokemon.com/assets/cms2/img/pokedex/full/001.png"},
    		{ nome: "Ivysaur" , descricao: "There is a bud on this Pokémon's back. To support its weight, Ivysaur's legs and trunk grow thick and strong. If it starts spending more time lying in the sunlight, it's a sign that the bud will bloom into a large flower soon.", foto: "http://assets.pokemon.com/assets/cms2/img/pokedex/full/002.png"}
    			  ]
    		}
		}
}
</script>

<style scoped>
	.card{
		width: 300px;
		border:1px solid black;
		border-radius: 10px;
		padding: 10px 20px;
		float: left;
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
