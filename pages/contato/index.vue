<template>
    <div>
        <section class="contato">
            <h1>Contato</h1>
            <div>
                <img src="/sobre.jpg" alt="">
                <form action="">
                    <label for="nome">Nome</label>
                    <input type="text" name="nome" placeholder="Nome">
                    <label for="email">E-mail</label>
                    <input type="email" name="email" placeholder="E-mail">
                    <label for="mensagem">Mensagem</label>
                    <input type="text" name="mensagem" placeholder="Mensagem">
                    <button type="submit">Enviar</button>
                </form>
                
            </div>
        </section>
    </div>
</template>

<script>
export default {
    layout: 'page'
}
</script>

<style scoped>
    .contato {
	max-width: 960px;
	margin: 0 auto;
	padding-top: 60px;
	text-align: center;
}

.contato h1 {
	font-size: 2.25em;
	margin-bottom: 30px;
}

.contato h1::after {
	content: '';
	display: block;
	width: 100%;
	height: 1px;
	margin: 20px 0 50px 0;
	background-color: rgba(0, 0, 0, 0.2);
}

.contato > div::before, .contato > div::after {
	content: '';
	display: table;
	clear: both;
}

.contato img {
	float: left;
	width: 350px;
	max-width: 100%;
	margin: 0 40px 10px 40px;
}

.contato form {
	float: left;
	width: 350px;
	margin: 0 10px;
	text-align: justify;

}

.contato form label {
	display: none;
	margin-bottom: 10px;
}

.contato form input {
	width: 300px;
	height: 40px;
	outline: none;
	display: block;
	border: none;
	margin-bottom: 40px;
	border-bottom: 1px solid #4286f4;
}

.contato form button {
	margin-top: 40px;
	width: 90px;
	height: 35px;
	background-color: #4286f4;
	padding: 10px 20px;
	color: #fff;
	border: none;
	cursor: pointer;

}

</style>


