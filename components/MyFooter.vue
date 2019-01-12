<template>
    <div>
        <footer class="footer">
            <div class="container">
                <div class="content_footer grid-8">
                    <h2>Footer Content</h2>
                    <p>You can use roes and columns here to organize your footer content</p>
                </div>
                <div class="footer_links grid-4">
                    <h2>Links</h2>
                    <ul>
                        <li>Home</li>
                        <li>Sobre</li>
                        <li>Contatos</li>
                    </ul>	
                </div>
            </div>

            <div class="copy">
                <div class="container">
                    <p class="grid-8">copy 2018 Copyright text</p>
                    <a class="grid-4" href="#">More links</a>
                </div>
            </div>
            
        </footer>
    </div>
</template>


<style scoped>
    .footer {
	width: 100%;
	background-color: #42a7f4;
	margin-top: 90px;
	color: #fff;
	padding-top: 30px;
}





.content_footer h2 {
	font-size: 1.5em;
	margin-bottom: 20px;
}



.footer_links {
	float: left;

}

.footer_links h2 {
	font-size: 1.5em;
	margin-bottom: 20px;
}

.copy {
	width: 100%;
	margin-top: 40px;
	padding: 15px 0;
	background-color:#419af4;
}


.copy p {
	font-weight: normal;
	float: left;
}

.copy a {
	float: right;
	color: #fff;
}
</style>

