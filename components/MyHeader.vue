<template>
    <div>
        <header class="menu">
            <div class="menu_container">
                <nuxt-link class="logo" to="/">Imob</nuxt-link>
                <nav class="nav_bar">
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

.menu_container {
	max-width: 960px;
	margin: 0 auto;
}

.menu_container::before, .menu_container::after {
	content: '';
	display: table;
	clear: both;
}

.logo {
	float: left;
	font-size: 2.5em;
	margin: 0 10px;
	color: #fff;
}

.nav_bar {
	float: right;
	margin: 0 10px;
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

