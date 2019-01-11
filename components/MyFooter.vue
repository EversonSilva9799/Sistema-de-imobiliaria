<template>
    <div>
        <footer class="footer">
            <div class="footer_container">
                <div class="content_footer">
                    <h2>Footer Content</h2>
                    <p>You can use roes and columns here to organize your footer content</p>
                </div>
                <div class="footer_links">
                    <h2>Links</h2>
                    <ul>
                        <li>Home</li>
                        <li>Sobre</li>
                        <li>Contatos</li>
                    </ul>	
                </div>
            </div>

            <div class="copy">
                <div class="copy_container">
                    <p>copy 2018 Copyright text</p>
                    <a href="#">More links</a>
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

.footer_container {
	max-width: 960px;
	margin: 0 auto;
}

.footer_container::before, .footer_container::after {
	content: '';
	display: table;
	clear: both;
}

.content_footer {
	float: left;
	margin: 0 10px;
	max-width: 460px;
}

.content_footer h2 {
	font-size: 1.5em;
	margin-bottom: 20px;
}

.content_footer p {
	max-width: 320px;
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

.copy_container {
	max-width: 960px;
	margin: 0 auto;
}

.copy_container::before, .copy_container::after {
	content: '';
	display: table;
	clear: both;
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

