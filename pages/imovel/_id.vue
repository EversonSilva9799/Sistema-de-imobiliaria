<template>
    <div>
        <section class="imovel">
            <h1>Imóvel</h1>
            <div class="container">
				<div class="grid-7">
					<img  :src="casa.imagem" :alt="casa.titulo">
				</div>
                
                <div class="wrap grid-5">
                    <h2 class="titulo">{{ casa.titulo }}</h2>
                    <h3>Descrição breve sobre o imóvel</h3>
                    <ul>
                        <li>Código: {{ casa.código }}</li>
                        <li>Status: {{ casa.status }}</li>
                        <li>Tipo: {{ casa.tipo }}</li>
                        <li>Endereço: {{ casa.endereço }}</li>
                        <li>Cep: {{ casa.cep }}</li>
                        <li>Cidade: {{ casa.cidade }}</li>
                        <li>Valor: R$ {{ casa.valor }}</li>
                    </ul>

                </div>
            </div> 

			<div class="container">
			<a class="btn" @click="activeForm">Entrar em contato</a>
			<nuxt-link class="btn" to="/">Voltar</nuxt-link>
			</div>
			
            <div class="container contato_casa " v-show="form_contato">
				<span class="close" @click="closeForm">X</span>
				<h2>Fale conosco</h2>
				<form action="" @submit.prevent="login" class="grid-12">
					<label for="codigo">Código da casa</label>
					<input disabled type="text" name="codigo" placeholder="Código da casa" :value="casa.código">
					<label for="titulo">Título da casa</label>
					<input  disabled type="text" name="titulo" placeholder="Título da casa" :value="casa.titulo">
					<label for="valor">Valor da casa</label>
					<input  disabled type="text" name="valor" placeholder="Valor da casa" :value="'R$ ' +casa.valor">
					<textarea placeholder="Mensagem"></textarea>
					<button type="submit">Enviar</button>
				</form>
			</div>
        </section>

		<!-- <div class="contato_casa container" v-show="form_contato">
			<span class="close" @click="closeForm">X</span>
			<h2>Fale conosco</h2>
			<form action="" @submit.prevent="login" class="grid-12">
				<label for="codigo">Código da casa</label>
				<input disabled type="text" name="codigo" placeholder="Código da casa" :value="casa.código">
				<label for="titulo">Título da casa</label>
				<input  disabled type="text" name="titulo" placeholder="Título da casa" :value="casa.titulo">
				<label for="valor">Valor da casa</label>
				<input  disabled type="text" name="valor" placeholder="Valor da casa" :value="'R$ ' +casa.valor">
				<textarea placeholder="Mensagem"></textarea>
				<button type="submit">Enviar</button>

			</form>
		</div> -->
    </div>
</template>

<script>
export default {
	layout:  'page',
	data() {
		return {
			form_contato: false,
			casa: []
		}
	},
	created() {
		this.id = this.$route.params.id
		this.show()
		
	},
	methods: {
		async show() {
			const res = await this.$axios.get('http://localhost:8080/casas/' + this.id);
			this.casa = res.data;
		},

		activeForm() {
			// window.scrollTop = 0;
			this.form_contato = true;
			var el = document.querySelector('.contato_casa');
			
			//el.classList = 'show'
			window.scrollTo(0, 0);
			
		},
		closeForm() {
			this.form_contato = false;
		},

		
	}

    


}
</script>


<style scoped>
    .imovel {
	/* max-width: 960px;
	margin: 0 auto; */
	padding-top: 60px;
	text-align: center;
}

.imovel > div::before, .imovel > div::after {
    content: '';
    display: table;
    clear: both;
}

.imovel h1 {
	font-size: 2.25em;
	margin-bottom: 30px;
}



.imovel h1::after {
	content: '';
	display: block;
	max-width: 940px;
	height: 1px;
	margin: 20px auto 50px auto;
	text-align: center;
	background-color: rgba(0, 0, 0, 0.2);
}




.imovel .wrap{
	text-align: justify;
}

.imovel .wrap h2 {
	font-weight: normal;
	font-size: 1.5em;
	margin-bottom: 30px;
}

.imovel .wrap h3 {
	font-weight: normal;
	font-size: 0.9em;
	position: relative;
	left: 20px;
	margin-bottom: 20px;

}

.imovel .wrap h3::before {
	content: '';
	width: 5px;
	height: 25px;
	display: inline-block;
	position: relative;
	top: 7px;
	left: -23px;
	background-color: #4286f4;
	/* margin-right: 30px. */
}

.imovel ul li {
	margin-bottom: 10px;
}

.btn {
	display: inline-block;
	cursor: pointer;
	color: #000;
	border: 3px solid #4286f4;
	width: 120px;
	height: 52px;
	margin-left: 10px;
	text-align: center;
	padding: 5px 10px;
	font-weight: normal;
	float: left;
	display: flex;
   	justify-content: center;
   	align-items: center;
}

.btn:hover {
	border: 3px solid #000;
}

.ccontato_casa {
	position: absolute;
	/* width: 40%; */
	padding-top: 15px;

	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	background-color: #4286f4;
	border: 1px solid rgba(255,255,255,0.4);
	text-align: center;
	color: #fff;
}

.contato_casa {
	position: absolute;
	top: 0px;
	right: 0px;
	left: 0;
	background-color: #4286f4;
	border: 1px solid rgba(255,255,255,0.4);
	text-align: center;
	color: #fff; 

}

.close {
	cursor: pointer;
	font-size: 1.5em;
	float: left;
}


.close:hover {
	background-color: rgba(244, 92, 66, 1);
}

.contato_casa h2 {
	text-align: center;
	text-transform: uppercase;
	margin-bottom: 10px;
}

.contato_casa form{
	width: 100%;
}

.contato_casa form label {
	display: block;
	margin-top: 15px;
}

.contato_casa form input{
	width: 60%;
	height: 35px;
	display: block;
	margin: 0 auto 0 auto;
	border-radius: 3px;
	border: none;
	border-bottom: 1px solid rgba(0,0,0,0.4);
	outline: none;
	padding-left: 5px;
}

.contato_casa textarea {
	margin-top: 30px;
	/* width: 480px; */
	width: 89%;
	height: 180px;

}

.contato_casa form button {
	margin: 40px auto 10px auto;
	width: 90px;
	display: block;
	height: 35px;
	background-color: #4286f4;
	padding: 10px 20px;
	color: #fff;
	border: none;
	cursor: pointer;
}

@media only screen and (max-width: 739px) {
	.btn {
		margin: 0;
		margin-right: 10px;
	}
}




</style>


