<template>
    <div>
        <section class="sobre">
            <h1>Sobre</h1>
            <div>
                <img src="/sobre.jpg" alt="">
                <div class="wrap">
                    <h2>A Empresa</h2>
                    <h3>Descrição breve sobre a Empresa</h3>
                    <p>A Intel Corporation foi fundada em 1968 por Robert Noyc e Gordon Earle Moore. Seu primeiro produto foi um circuito integrado de Memória RAM e logo depois, nos anos 70, se tornou líder de mercado. Criaram o microprocessador Intel 4004, que evoluiu até o que temos hoje, suas linhas Intel Core i3, Core i5 e Core i7. A Intel trabalhou na evolução de processamento com o Core Duo, Dual Core e Core 2 Duo. Na década de 90 foi criado o Intel Inside, um selo de qualidade criado pela empresa para destacar que o computador utilizava processador da marca e não de seus concorrentes, como a AMD. Seu último lançamento, em 2015, foi a sexta geração dos processadores Intel Core, o Skylake. Seus chipsets são os preferidos dos gamers por serem bons para jogos.</p>	
                </div>
                
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
    .sobre {
	max-width: 960px;
	margin: 0 auto;
	padding-top: 60px;
	text-align: center;
}

.sobre h1 {
	font-size: 2.25em;
	margin-bottom: 30px;
}

.sobre h1::after {
	content: '';
	display: block;
	width: 100%;
	height: 1px;
	margin: 20px 0 50px 0;
	background-color: rgba(0, 0, 0, 0.2);
}

.sobre > div::before, .sobre > div::after {
    content: '';
    display: table;
    clear: both;
}

.sobre img {
	float: left;
	width: 300px;
	max-width: 100%;
	margin-right: 20px;
	margin-left: 10px;
}

.sobre .wrap{
	float: left;
	text-align: justify;
}

.sobre .wrap h2 {
	font-weight: normal;
	font-size: 2em;
	margin-bottom: 30px;
}


.sobre .wrap h3 {
	font-weight: normal;
	font-size: 0.9em;
	position: relative;
	left: 20px;
	margin-bottom: 20px;

}

.sobre .wrap p {
	max-width: 400px;
}

.sobre .wrap h3::before {
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
</style>


