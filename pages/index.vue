<template>
  <section class="container">


	<section class="intro">
		<h1>Titulo da imagem</h1>
		<p>Descrição da imagem</p>
	</section>

	<section class="produtos">
		<h1>Imóveis</h1>
		<ul class="produtos_item">
			<li v-for="casa of casas" :key="casa.id" class="item">
				<img :src="casa.imagem" alt="">
				<div class="descricao">
					<p class="status">{{ casa.status }}</p>
					<p>Descrição do imóvel</p>
					<p>R$ {{ casa.valor }}</p>
				</div>
				<a :href="'/imovel/' + casa.id">Ver Mais...</a>
			</li>	

		</ul>
		
	</section>

  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  layout: 'page',
  data () {
    return {
      casas: []
    }
  },
  created() {
    this.index()
  },
  methods: {
    async index() {
      const res = await this.$axios.get('http://localhost:8080/casas');
      this.casas = res.data;
      console.log(this.casas);
    }
  }
}
</script>

<style>

  .intro {
	width: 100%;
	background: url('/bg.jpg') no-repeat center center;
	background-size: cover;
	height: 380px;
	text-align: center;
	padding: 120px 0;
	color: #fff;
}

.intro h1 {
	font-size: 3.5em;
	text-transform: uppercase;
}

.intro p {
	font-size: 1.2em;
	
}

/*Produtos*/

.produtos {
	width: 100%;
	padding-top: 60px;
	
}

.produtos h1 {
	font-size: 2.25em;
	color: #000;
	text-align: center;
	margin-bottom: 30px;

}

.produtos_item {
  max-width: 960px;
  
	margin: 0 auto;
}

.produtos_item::before, .produtos_item::after {
	content: '';
	display: table;
	clear: both;
}

.item {
  list-style: none;
	float: left;
	width: 220px;
	box-shadow: 0 0 1px 0px #000;
	margin: 0 10px 20px 10px;
	padding-bottom: 20px;

}

.item img {
  width: 100%;
  height: 150px;
	display: block;
	margin-bottom: 25px;
}

.descricao {
	padding-left: 20px;
	margin-bottom: 13px;
	border-bottom: 1px solid rgba(0, 0, 0, 0.2)
}

.descricao .status {
	font-size: 1.25em;
	color:  rgba(255, 177, 76, 0.9);
}



.descricao p {
	margin-bottom: 7px;
}


.item a {
	text-transform: uppercase;
	font-size: 1.25em;
	margin-left: 20px;
	color:  rgba(255, 177, 76, 0.7);
}

</style>
