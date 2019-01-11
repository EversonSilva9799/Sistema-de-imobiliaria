<template>
    <div>
        <section class="imovel">
            <h1>Imóvel</h1>
            <div>
                <img :src="casa.imagem" :alt="casa.titulo">
                <div class="wrap">
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

                    <a @click="activeForm">Entrar em contato</a>
                </div>


            </div>
            
            <div class="clear"></div>

        </section>

		<div class="contato_casa" v-show="form_contato">
			<span class="close" @click="closeForm">X</span>
			<h2>Entre em contato sobre a casa</h2>
			<form action="" @submit.prevent="login">
				<label for="codigo">Código da casa</label>
				<input type="text" name="codigo" placeholder="Código da casa" :value="casa.código">
				<label for="titulo">Título da casa</label>
				<input type="text" name="titulo" placeholder="Título da casa" :value="casa.titulo">
				<label for="valor">Valor da casa</label>
				<input type="text" name="valor" placeholder="Valor da casa" :value="'R$ ' +casa.valor">
				<textarea placeholder="Mensagem"></textarea>
				<button type="submit">Enviar</button>

			</form>
		</div>
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
			this.form_contato = true;
		},
		closeForm() {
			this.form_contato = false;
		}
	}

    


}
</script>


<style scoped>
    .imovel {
	max-width: 960px;
	margin: 0 auto;
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
	width: 100%;
	height: 1px;
	margin: 20px 0 50px 0;
	background-color: rgba(0, 0, 0, 0.2);
}

.imovel img {
	width: 600px;
	margin-right: 40px;
	float: left;
}

.imovel .wrap{
	float: left;
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

.imovel .wrap a {
	display: block;
	cursor: pointer;
	border: 3px solid #4286f4;
	width: 170px;
	text-align: center;
	padding: 10px 20px;
	font-weight: bold;
}

.contato_casa {
	position: absolute;
	width: 40%;
	/* height: 400px; */
	top: 0;
	left: 200px;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	background-color: #f7f8f9;
}

.contato_casa h2 {
	text-align: center;
}

.contato_casa form{
	widows: 100%;
}

.contato_casa form input{
	width: 60%;
	height: 35px;
	display: block;
	margin: 10px auto 0 auto;
	border-radius: 3px;
	border: none;
	border-bottom: 1px solid rgba(0,0,0,0.4);
	outline: none;
	padding-left: 20px;
}

.contato_casa textarea {
	margin: 30px;
	width: 480px;
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


</style>


