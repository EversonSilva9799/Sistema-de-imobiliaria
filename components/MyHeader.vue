<template>
    <div>
        <header class="menu">
            <div class="container">
                <nuxt-link class="grid-4" to="/">Imob</nuxt-link>
                <nav class="nav_bar grid-8">
                    <ul>
                        <li><nuxt-link to="/">Home</nuxt-link></li>
                        <li><nuxt-link to="/sobre">Sobre</nuxt-link></li>
                        <li><nuxt-link to="/contato">Contato</nuxt-link></li>
                
                    </ul>
                </nav>
            </div>
        </header>
    </div>
</template>

<style scoped>
.menu {
	width: 100%;
	background-color: #4286f4;
	padding: 20px 0;
	color: #fff;
}



.nav_bar li {
	display: inline-block;
	font-size: 1.225em;
	position: relative;
	top: 10px;
	margin-left: 15px;
}

.nav_bar li a {
	color: #fff;
}
</style>

