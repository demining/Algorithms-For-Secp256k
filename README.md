<!DOCTYPE html>
<!-- saved from url=(0050)https://cryptodeeptech.ru/algorithms-for-secp256k/ -->
<html lang="ru-RU"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="profile" href="https://gmpg.org/xfn/11">

	<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">

	<!-- This site is optimized with the Yoast SEO plugin v19.2 - https://yoast.com/wordpress/plugins/seo/ -->
	<style type="text/css"></style><title>Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»</title>
	<meta name="description" content="Consider several useful and efficient algorithms for an elliptic curve E over a field GF(p) given by the short Weierstrass equation">
	<link rel="canonical" href="https://cryptodeeptech.ru/algorithms-for-secp256k/">
	<meta property="og:locale" content="ru_RU">
	<meta property="og:type" content="article">
	<meta property="og:title" content="Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»">
	<meta property="og:description" content="Consider several useful and efficient algorithms for an elliptic curve E over a field GF(p) given by the short Weierstrass equation">
	<meta property="og:url" content="https://cryptodeeptech.ru/algorithms-for-secp256k/">
	<meta property="og:site_name" content="«CRYPTO DEEP TECH»">
	<meta property="article:published_time" content="2022-07-14T18:58:36+00:00">
	<meta property="article:modified_time" content="2022-08-25T19:14:56+00:00">
	<meta property="og:image" content="https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png">
	<meta name="author" content="Crypto Deep Tech">
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:label1" content="Написано автором">
	<meta name="twitter:data1" content="Crypto Deep Tech">
	<meta name="twitter:label2" content="Примерное время для чтения">
	<meta name="twitter:data2" content="6 минут">
	<script async="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/tag.js"></script><script type="application/ld+json" class="yoast-schema-graph">{"@context":"https://schema.org","@graph":[{"@type":"WebSite","@id":"https://cryptodeeptech.ru/#website","url":"https://cryptodeeptech.ru/","name":"«CRYPTO DEEP TECH»","description":"Cryptanalysis and data financial security services","potentialAction":[{"@type":"SearchAction","target":{"@type":"EntryPoint","urlTemplate":"https://cryptodeeptech.ru/?s={search_term_string}"},"query-input":"required name=search_term_string"}],"inLanguage":"ru-RU"},{"@type":"ImageObject","inLanguage":"ru-RU","@id":"https://cryptodeeptech.ru/algorithms-for-secp256k/#primaryimage","url":"https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png","contentUrl":"https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png"},{"@type":"WebPage","@id":"https://cryptodeeptech.ru/algorithms-for-secp256k/#webpage","url":"https://cryptodeeptech.ru/algorithms-for-secp256k/","name":"Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»","isPartOf":{"@id":"https://cryptodeeptech.ru/#website"},"primaryImageOfPage":{"@id":"https://cryptodeeptech.ru/algorithms-for-secp256k/#primaryimage"},"datePublished":"2022-07-14T18:58:36+00:00","dateModified":"2022-08-25T19:14:56+00:00","author":{"@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0"},"description":"Consider several useful and efficient algorithms for an elliptic curve E over a field GF(p) given by the short Weierstrass equation","breadcrumb":{"@id":"https://cryptodeeptech.ru/algorithms-for-secp256k/#breadcrumb"},"inLanguage":"ru-RU","potentialAction":[{"@type":"ReadAction","target":["https://cryptodeeptech.ru/algorithms-for-secp256k/"]}]},{"@type":"BreadcrumbList","@id":"https://cryptodeeptech.ru/algorithms-for-secp256k/#breadcrumb","itemListElement":[{"@type":"ListItem","position":1,"name":"Главная страница","item":"https://cryptodeeptech.ru/"},{"@type":"ListItem","position":2,"name":"Useful and efficient algorithms for secp256k1 elliptic curve"}]},{"@type":"Person","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0","name":"Crypto Deep Tech","sameAs":["https://cryptodeeptech.ru","https://www.youtube.com/channel/UCd8W6qtRSiBn0Q0wy6HuNkQ/"],"url":"https://cryptodeeptech.ru/author/cryptodeeptech/"}]}</script>
	<!-- / Yoast SEO plugin. -->


<link rel="dns-prefetch" href="https://fonts.googleapis.com/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента" href="https://cryptodeeptech.ru/feed/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента комментариев" href="https://cryptodeeptech.ru/comments/feed/">
<link rel="stylesheet" id="itng-block-style-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_8f426a1779caff96bb3f2afbcff86bc9.css" media="all">
<link rel="stylesheet" id="wp-block-library-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/style.min.css" media="all">
<style id="global-styles-inline-css">
body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--duotone--dark-grayscale: url('#wp-duotone-dark-grayscale');--wp--preset--duotone--grayscale: url('#wp-duotone-grayscale');--wp--preset--duotone--purple-yellow: url('#wp-duotone-purple-yellow');--wp--preset--duotone--blue-red: url('#wp-duotone-blue-red');--wp--preset--duotone--midnight: url('#wp-duotone-midnight');--wp--preset--duotone--magenta-yellow: url('#wp-duotone-magenta-yellow');--wp--preset--duotone--purple-green: url('#wp-duotone-purple-green');--wp--preset--duotone--blue-orange: url('#wp-duotone-blue-orange');--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
</style>
<link rel="stylesheet" id="wp-date-remover-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_e6094661d8923e95b233019ebff7c8f0.css" media="all">
<link rel="stylesheet" id="itng-fonts-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/css" media="all">
<link rel="stylesheet" id="itng-style-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_8de4505c66a21eefd3c1c98b6400e4e1.css" media="all">
<link rel="stylesheet" id="itng-main-style-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_d1cf6f49400112d539e59eee9b75e10d.css" media="all">
<style id="itng-main-style-inline-css">
.custom-logo-link img {width: 400px;}@media screen and (min-width: 992px) {#header-image .header-overlay {
            opacity: 0.01;
        }}
ins,
	.nav-wrapper,
	#menu,
	.main-navigation ul#menu-desktop ul,
	#itng-featured-news .slider-post-wrapper .posted-on a,
	#itng-featured-news #itng-featured-news-list-container .posted-on a,
	#itng-featured-posts .itng-featured-post-date,
	#itng-featured-news #itng-featured-news-carousel-container .posted-on a,
	#colophon,
	[class^=itng-search] form,
	#itng-featured-cat .featured-cat-thumb h2,
	#itng-featured-cat .featured-cat-thumb h3
	{background-color: #008bca}article .entry-meta a,
	article .blog-footer,
	article .blog-footer a,
	.widget a,
	.nav-links a,
	.itng-pagination .nav-links > a,
	.itng-pagination .dots
	{color: #008bca !important}blockquote,
	#itng-content-title span
	{border-color: #008bca}button.top-menu-mobile
	{background-color: #43bdf2 !important}#footer-sidebar .widget-title
	{color: #43bdf2 !important}
</style>
<link rel="stylesheet" id="bootstrap-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_d26191bd0380b0cf97525a613b8b566c.css" media="all">
<link rel="stylesheet" id="owl-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_c8322bd5bffc8e2856f2cbcd03c61d18.css" media="all">
<link rel="stylesheet" id="mag-popup-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_30b593b71d7672658f89bfea0ab360c9.css" media="all">
<link rel="stylesheet" id="font-awesome-css" href="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_c495654869785bc3df60216616814ad1.css" media="all">
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/jquery.min.js" id="jquery-core-js"></script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/jquery-migrate.min.js" id="jquery-migrate-js"></script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_49cea0a781874a962879c2caca9bc322.js" id="wp-date-remover-js"></script>
<link rel="https://api.w.org/" href="https://cryptodeeptech.ru/wp-json/"><link rel="alternate" type="application/json" href="https://cryptodeeptech.ru/wp-json/wp/v2/posts/270"><meta name="generator" content="WordPress 6.0.1">
<link rel="alternate" type="application/json+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Falgorithms-for-secp256k%2F">
<link rel="alternate" type="text/xml+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Falgorithms-for-secp256k%2F&amp;format=xml">
		<style type="text/css">
						#header-image {
						background-image: url(https://cryptodeeptech.ru/wp-content/uploads/2022/07/header3.jpg);
						background-size: cover;
						background-repeat: repeat;
						background-position: center center;
				}
							.site-title, .site-description {
				display: none;
				position: absolute;
				clip: rect(1px, 1px, 1px, 1px);
				}
					</style>
		<style id="custom-background-css">
body.custom-background { background-color: #eff3fd; }
</style>
	<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-32x32.png" sizes="32x32">
<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-192x192.png" sizes="192x192">
<link rel="apple-touch-icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-180x180.png">
<meta name="msapplication-TileImage" content="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-270x270.png">
</head>

<body data-rsssl="1" class="post-template-default single single-post postid-270 single-format-standard custom-background wp-custom-logo no-sidebar">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-dark-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0.49803921568627"></fefuncr><fefuncg type="table" tableValues="0 0.49803921568627"></fefuncg><fefuncb type="table" tableValues="0 0.49803921568627"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.54901960784314 0.98823529411765"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.71764705882353 0.25490196078431"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-red"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 0.27843137254902"></fefuncg><fefuncb type="table" tableValues="0.5921568627451 0.27843137254902"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-midnight"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0"></fefuncr><fefuncg type="table" tableValues="0 0.64705882352941"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-magenta-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.78039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.94901960784314"></fefuncg><fefuncb type="table" tableValues="0.35294117647059 0.47058823529412"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-green"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.65098039215686 0.40392156862745"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.44705882352941 0.4"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-orange"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.098039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.66274509803922"></fefuncg><fefuncb type="table" tableValues="0.84705882352941 0.41960784313725"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><div id="page" class="site">
	<a class="skip-link screen-reader-text" href="https://cryptodeeptech.ru/algorithms-for-secp256k/#primary">Skip to content</a>

	
	    <header id="masthead" class="site-header style-1">

		    
	        <div id="header-image">
		        <div class="site-branding">
					<a href="https://cryptodeeptech.ru/" class="custom-logo-link" rel="home"><img width="1279" height="319" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/cropped-header4.png" class="custom-logo" alt="«CRYPTO DEEP TECH»" srcset="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png 1279w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-300x75.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-1024x255.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-768x192.png 768w" sizes="(max-width: 1279px) 100vw, 1279px" title="Useful and efficient algorithms for secp256k1 elliptic curve"></a>	<h2 class="site-title"><a href="https://cryptodeeptech.ru/" rel="home">«CRYPTO DEEP TECH»</a></h2>
		<p class="site-description">Cryptanalysis and data financial security services</p>
	        	</div>
				<div class="header-overlay"></div>
	        </div>

			<div class="nav-wrapper">
				 <div class="container">
					 <div class="d-flex">

						<div id="site-navigation" class="main-navigation col-lg-11" role="navigation">
							<ul id="menu-desktop" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>						</div>

						<button href="#menu" class="menu-link mobile-nav-btn col-auto"><i class="fa fa-bars" aria-hidden="true"></i></button>

						<div id="search-wrapper" class="ml-auto col-auto d-flex">
							<button type="button" id="go-to-field" tabindex="-1"></button>
					    	<button class="search-btn-main"><i class="fa fa-search"></i></button>
					    	
<div class="itng-search-main">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>
						</div>
					</div>
				</div>
			</div>

		</header><!-- #masthead -->
			<div id="content-wrapper" class="container row">
		
	<main id="primary" class="site-main container order-1">

		
<article id="post-270" class="post-270 post type-post status-publish format-standard hentry category-1">
	
	<header class="entry-header">
		<h1 class="entry-title">Useful and efficient algorithms for secp256k1 elliptic curve</h1>	</header><!-- .entry-header -->
	
	
	
			<div class="entry-meta">
			<span class="posted-on" style="display: none;"><a href="https://cryptodeeptech.ru/algorithms-for-secp256k/" rel="bookmark"><time class="entry-date published" datetime="" style="display: none;"></time><time class="updated" datetime=""></time></a></span><span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>		</div><!-- .entry-meta -->
		
	
	<div class="entry-content">
		<div class="entry-meta"></div>
<div class="entry-content">
<p class="has-text-align-center"><iframe title="Youtube video player" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/gFbiBCNPsFk.html" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen" data-mce-fragment="1"></iframe></p>
<p>In this article, we will consider several useful and efficient algorithms for an elliptic curve&nbsp;&nbsp;<strong><em>E</em></strong>&nbsp;&nbsp;over a field&nbsp;&nbsp;<strong><em>GF(p)</em></strong>&nbsp;&nbsp;given by the short Weierstrass equation</p>
<p><code>у^2&nbsp;= х^3&nbsp;+ Ах + В</code></p>
<ul>
<li>&nbsp;<strong>Algorithm for generating a point on curve&nbsp;&nbsp;<em>E</em></strong></li>
<li>&nbsp;<strong>Algorithm for adding points</strong></li>
<li>&nbsp;<strong>Doubling Point Algorithm</strong></li>
<li>&nbsp;<strong>Algorithm for finding an integer multiple point</strong></li>
<li>&nbsp;<strong>Algorithm for finding an integer multiple point (scalar multiplication)</strong></li>
<li>&nbsp;<strong>Algorithm for constructing a divisor&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;over a curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;with support&nbsp;&nbsp;<em>supp(D)</em>&nbsp;&nbsp;of a given size&nbsp;&nbsp;<em>d</em></strong></li>
<li>&nbsp;<strong>Miller’s algorithm for calculating the value of the Weyl function&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>n, P</sub></em>&nbsp;&nbsp;from a divisor&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;such that&nbsp;&nbsp;</strong><em>supp(D)</em>&nbsp;&nbsp;∩ {P, O} = ∅</li>
<li>&nbsp;<strong>Pairing&nbsp;</strong>&nbsp;<em>Weil</em></li>
</ul>
<h4>Modular operations (integers) on a finite field (or Galois field)</h4>
<ol>
<li><em>x mod n</em>&nbsp;&nbsp;means «the remainder of n after dividing x».&nbsp;In other words, if&nbsp;&nbsp;<em>x = an + b</em>&nbsp;&nbsp;and a, b ∈ integer, and also 0 ≤ b ≤ n − 1, then&nbsp;&nbsp;<em>x mod n = b</em>&nbsp;&nbsp;.</li>
<li><strong>Reverse</strong>&nbsp;&nbsp;: if&nbsp;&nbsp;<em>ax = 1 mod n</em>&nbsp;&nbsp;, then&nbsp;&nbsp;<em>a</em>&nbsp;&nbsp;is the reciprocal of&nbsp;&nbsp;<em>x mod n</em>&nbsp;&nbsp;.&nbsp;There are two popular&nbsp;&nbsp;<em>solution</em>&nbsp;methods &nbsp;: •&nbsp;&nbsp;<strong><em>Method 1</em></strong>&nbsp;&nbsp;: Try each value for&nbsp;&nbsp;<em>a &lt; n as</em>&nbsp;&nbsp;long as&nbsp;&nbsp;<em>xa mod n = 1</em>&nbsp;&nbsp;.•&nbsp;&nbsp;<strong><em>Method 2</em></strong>&nbsp;&nbsp;: Euclidean method which is usually used to solve the inverse problem of large integers, so it is recommended to use method 1 to solve inverse problem of small integers.</li>
</ol>
<h4>Elliptic Curve Point Operation</h4>
<p>The point&nbsp;&nbsp;<em>P(x&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;)</em>&nbsp;&nbsp;on the elliptic curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;means: its coordinates&nbsp;&nbsp;<em>x&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>y&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;are elements of the field, and the coordinates&nbsp;&nbsp;<em>x&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>y&nbsp;&nbsp;<sub>0</sub></em>&nbsp;&nbsp;satisfy the equation.</p>
<ol>
<li><strong>Adding points on an elliptic curve</strong>&nbsp;&nbsp;: Let&nbsp;&nbsp;<em>P, Q</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>R</em>&nbsp;&nbsp;be three points on an elliptic curve.&nbsp;Adding points P + Q = R.</li>
<li><strong>Doubling points on an elliptic curve</strong>&nbsp;&nbsp;: Let&nbsp;&nbsp;<em>P, Q</em>&nbsp;&nbsp;be two points on an elliptic curve.&nbsp;Doubling Points P + P = 2P = Q</li>
<li><strong>Dot multiplication</strong>&nbsp;&nbsp;: let&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;be a point on the curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;, defined in the equation
<ul>
<li>Dot multiplication&nbsp;&nbsp;<em>nP</em>&nbsp;&nbsp;is defined as&nbsp;&nbsp;<em>nP = P + P + P + … + P</em>&nbsp;&nbsp;(&nbsp;&nbsp;<em>n</em>&nbsp;&nbsp;times), where&nbsp;&nbsp;<em>n</em>&nbsp;&nbsp;is an integer;&nbsp;<em>nP</em>&nbsp;&nbsp;is also a point on the same&nbsp;&nbsp;<em>E</em>&nbsp;curve &nbsp;.</li>
<li>The minimal natural number a with&nbsp;&nbsp;<em>aP = O</em>&nbsp;&nbsp;is called&nbsp; the&nbsp;<strong>order&nbsp; of&nbsp;<em>P</em></strong>&nbsp;&nbsp;.</li>
<li>Dot multiplication is widely required in elliptic curve cryptosystems.</li>
</ul>
</li>
</ol>
<h4>Divider</h4>
<p><strong>Divisor</strong>&nbsp;&nbsp;(Divisor)&nbsp;&nbsp;<em>D</em>&nbsp;&nbsp;on a curve&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is a convenient way to denote a&nbsp;&nbsp;<strong>multiset of points on&nbsp;&nbsp;<em>E</em></strong>&nbsp;&nbsp;, written as a formal sum</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/0b13e2fbec01a2ea5635bbcb1a36ade1.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<ul>
<li>The set of all divisors on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is denoted&nbsp; by&nbsp;<em>Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;and forms a group in which the addition of divisors is natural.</li>
<li>Zero Divisor: This is the divisor for all n&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;= 0, the zero divisor is&nbsp;&nbsp;<em>0 ∈ Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;.</li>
<li>If the field&nbsp;&nbsp;<em>F&nbsp;&nbsp;<sub>q</sub></em>&nbsp;&nbsp;is not specific, it can be omitted and simply written as&nbsp;&nbsp;<em>Div(E)</em>&nbsp;&nbsp;to denote the divisor group.</li>
</ul>
<h4>Function f divided by E</h4>
<p>The divisor of a function&nbsp;&nbsp;<em>f</em>&nbsp;&nbsp;by&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;is used to denote the intersection points (and their multiplicities) of the functions&nbsp;&nbsp;<em>f</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;.</p>
<h4>Pairing Weil</h4>
<p>The Weil pairing, which is denoted&nbsp; by&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub></em>&nbsp;&nbsp;, takes as input a pair of points&nbsp;&nbsp;<em>P, Q ∈ E[m] and&nbsp;&nbsp;<sub>produces</sub></em>&nbsp;&nbsp;as output a root _m of unity&nbsp;&nbsp;<em><sup>e&nbsp;&nbsp;<sub>m</sub></sup><sub>&nbsp;(</sub>&nbsp;&nbsp;P , Q)</em>&nbsp;&nbsp;.&nbsp;The bilinearity of the Weyl pairing is expressed by the equations</p>
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ P&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;, Q) \u003d e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;, Q) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P2, B),</em></p>
<p><em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;+ Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;) = e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;) * e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P, Q&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;).</em></p>
<p><strong>The Weil&nbsp;</strong>&nbsp;pair&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>Q</em>&nbsp;&nbsp;is the number</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/5ebb8530fd881d89d3f396460464af79.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>where&nbsp;&nbsp;<em>S ∈ E</em>&nbsp;&nbsp;is any point satisfying the condition&nbsp;&nbsp;<em>S ∉ {O, P, −Q, P − Q}</em>&nbsp;&nbsp;.&nbsp;(This ensures that all quantities on the right hand side are defined and non-zero.) One can check that the value of&nbsp;&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P,Q)</em>&nbsp;&nbsp;does not depend on the choice of&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;,&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>Q</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>S</em>&nbsp;&nbsp;.</p>
<h4>An Efficient Weil Pairing Computation Algorithm</h4>
<p>Let&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;be an elliptic curve and let P = (x&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;,y&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;) and Q = (x&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;) be nonzero points on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;.</p>
<p>Let&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;be the slope of the line connecting&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>Q</em>&nbsp;&nbsp;, or the slope of the tangent to&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;at P if&nbsp;&nbsp;<em>P =</em>&nbsp;&nbsp;Q. (If the line is vertical, we set&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;= ∞.) Define a function g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;on&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;as follows:</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/dbc8cdefc33de28911b8e41530a16687.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>then</p>
<p>div(g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;) = [P] + [Q] — [P + Q] — [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;].</p>
<p><strong>Miller’s algorithm</strong></p>
<p>Let&nbsp;&nbsp;<em>m ≥</em>&nbsp;&nbsp;and write the binary extension of&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;as</p>
<p><em>m \u003d m&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;+ m&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;* 2 + m&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;* 2&nbsp;&nbsp;<sup>2</sup>&nbsp;&nbsp;+ + m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;2&nbsp;&nbsp;<sup>n — 1</sup></em></p>
<p>for&nbsp;&nbsp;<em>m&nbsp;&nbsp;<sub>i</sub>&nbsp;&nbsp;∈ {0, 1}</em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;≠ 0</em>&nbsp;&nbsp;.&nbsp;The following algorithm returns a function&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;whose divisor satisfies the condition</p>
<p>div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] — [&nbsp;&nbsp;<em>mP</em>&nbsp;&nbsp;] — (&nbsp;&nbsp;<em>m — 1</em>&nbsp;&nbsp;) [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;],</p>
<p>where the functions&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, T</sub></em>&nbsp;&nbsp;and&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, P</sub></em>&nbsp;&nbsp;used by the algorithm are defined in (a).</p>
<figure class="wp-block-image"><img title="" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/bc1d75c6060123845b0b7f4b153096b0.png" alt="Useful and efficient algorithms for secp256k1 elliptic curve"></figure>
<p>In particular, if&nbsp;&nbsp;<em>P ∈ E[m]</em>&nbsp;&nbsp;, then div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] −&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;].</p>
<h3>Requirement</h3>
<ul>
<li><code>Python 3.5</code></li>
<li><code>numpy</code></li>
</ul>
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/04AlgorithmsForSecp256k/

pip3 install numpy</code></pre>
<pre class="wp-block-code"><code>├── Curves.py             &lt;- Набор данных эллиптических кривых
├── Divisor.py            &lt;- Создать делитель
├── EllipticCurve.py      &lt;- Классы эллиптической кривой и точки на эллиптической кривой
├── EuclideanAlg.py       &lt;- Расширенный алгоритм Евклида
├── Helper.py             &lt;- Вспомогательные функции (обратные биты, мощность по модулю) 
├── Pairing.py            &lt;- Спаривания Вейля, а так же Алгоритм Миллера
├── Tests.py              &lt;- Модульные тесты для функций
├── Tonelli_ShanksAlg.py  &lt;- Алгоритм Тонелли – Шенкса
├── main.py               &lt;- main
</code></pre>
<h3></h3>
<hr class="wp-block-separator has-alpha-channel-opacity">
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/04AlgorithmsForSecp256k" target="_blank" rel="noreferrer noopener">Source</a></strong></p>
<p><strong>Telegram:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<p><strong>Video:&nbsp;&nbsp;<a href="https://youtu.be/gFbiBCNPsFk" target="_blank" rel="noreferrer noopener">https://youtu.be/gFbiBCNPsFk</a></strong></p>
<p><strong>Source: <a href="https://cryptodeeptech.ru/algorithms-for-secp256k">https://cryptodeeptech.ru/algorithms-for-secp256k</a></strong></p>
<p class="has-text-align-center"><iframe title="Youtube video player" src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/gFbiBCNPsFk(1).html" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen" data-mce-fragment="1"></iframe></p>
</div>
<footer class="entry-footer">
<div class="cat-links"></div>
</footer>
	</div><!-- .entry-content -->

	<footer class="entry-footer">
		<div class="cat-links"><i class="fa fa-folder-open" aria-hidden="true"></i> <a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a></div>	</footer><!-- .entry-footer -->
</article><!-- #post-270 -->

	<nav class="navigation post-navigation" aria-label="Записи">
		<h2 class="screen-reader-text">Навигация по записям</h2>
		<div class="nav-links"><div class="nav-previous"><a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/" rel="prev">How to Convert Bitcoin-PUBKEY HEX Public Keys to Base58 Bitcoin Address and Check Balance for BTC Coins</a></div><div class="nav-next"><a href="https://cryptodeeptech.ru/vulnerable-openssl/" rel="next">Search for BTC coins on earlier versions of Bitcoin Core with critical vulnerability OpenSSL 0.9.8 CVE-2008-0166</a></div></div>
	</nav>		<div id="itng_related_posts_wrapper">
			<h3 id="itng_related_posts_title">Related Posts</h3>
			<div class="itng-related-posts row">
				<article id="post-82" class="itng-blog col-md-6 col-lg-4 post-82 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/bitcoin-wallet-silk-road/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/bitcoin-wallet-silk-road/">The biggest hack in the history of Bitcoin</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					Bitcoin Wallet Silk Road this is probably the largest hack in the history of Bitcoin, since the balance of coins was 69,369&nbsp;&nbsp;BTC&nbsp;&nbsp;in terms of dollars, the amount exceeded more than&nbsp;&nbsp;$1 billion&nbsp;. This notorious bitcoin wallet&nbsp;&nbsp;1HQ3Go3ggs8pFnXuHVHRytPCq5fGG8Hbhx &nbsp;was tied to a darknet marketplace that was closed in 2013 and its creator, Ross Ulbricht. In 2019, an encrypted wallet.dat&nbsp;file was…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-82 --><article id="post-322" class="itng-blog col-md-6 col-lg-4 post-322 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/kangaroo/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/kangaroo/">Pollard’s Kangaroo find solutions to the discrete logarithm secp256k1 PRIVATE KEY + NONCES in a known range</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will look at the fastest algorithm for ECDLP from the field of computational number theory, Pollard's kangaroo is also called Pollard's lambda algorithm. Pollard's kangaroo method computes&nbsp;&nbsp;discrete logarithms&nbsp;&nbsp;in arbitrary cyclic groups.&nbsp;It is applied if the discrete logarithm is known to lie in a certain range, say&nbsp;&nbsp;[ a , b ], and then has…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-322 --><article id="post-127" class="itng-blog col-md-6 col-lg-4 post-127 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/">How to Convert Bitcoin-PUBKEY HEX Public Keys to Base58 Bitcoin Address and Check Balance for BTC Coins</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will learn how to check the balance of Bitcoin coins in a large amount of data using the bitcoin-checker.py Python script for&nbsp;&nbsp;this&nbsp;. The result of checking the Python script bitcoin-checker.py We will also learn how to convert the public key of Bitcoin&nbsp;&nbsp;PUBKEY (HEX)&nbsp;to Bitcoin Address&nbsp;&nbsp;(Base58)&nbsp;All this big work is done&nbsp;&nbsp;by the Python script&nbsp;&nbsp;pubtoaddr.py…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-127 -->			</div>
		</div>
			<div id="author_box" class="row no-gutters">
			<div class="author_avatar col-2">
							</div>
			<div class="author_info col-10">
				<h4 class="author_name title-font">
					Crypto Deep Tech				</h4>
				<div class="author_bio">
									</div>
			</div>
		</div>
	
	</main><!-- #main -->

<!--WCLEARFY_PAGE_TYPE_post--><!--WCLEARFY_FOOTER_START--></div><!-- #content-wrapper -->


 <div id="footer-sidebar" class="widget-area">
    <div class="container">
        <div class="row">
                    </div>
    </div>
</div>
	<footer id="colophon" class="site-footer">
		<div class="container">
			<div class="site-info">
				Donation Address: <a href="https://www.blockchain.com/btc/address/1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v" target="_blank">♥  BTC: 1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v</a>				<span class="sep"> | </span>
					Copyright © 2022 «CRYPTO DEEP TECH». 			</div><!-- .site-info -->
		</div>
	</footer><!-- #colophon -->
</div><!-- #page -->

<nav id="menu" class="panel" role="navigation" style="position: fixed; top: 0px; bottom: 0px; height: 100%; left: -15.625em; width: 15.625em;">
	<div class="menu-overlay"></div>
	<div id="panel-top-bar">
		<button class="go-to-bottom"></button>
		<button id="close-menu" class="menu-link"><i class="fa fa-chevron-left" aria-hidden="true"></i></button>
	</div>

	<ul id="menu-main" class="menu"><li class="page_item page-item-53"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="page_item page-item-43"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="page_item page-item-55"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="page_item page-item-49"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
</ul>

	<button class="go-to-top"></button>
</nav>

<div id="sticky-navigation">
	<div class="nav-wrapper">
		 <div class="container">

			 <div class="row justify-content-end align-items-center justify-content-between no-gutters">


				<div class="main-navigation col-lg-9" role="navigation">
					<ul id="menu-desktop" class="menu"><li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>				</div>

				<button href="#menu" class="menu-link mobile-nav-btn"><i class="fa fa-bars" aria-hidden="true"></i></button>

				<button type="button" id="go-to-field" tabindex="-1"></button>

				<button class="search-btn-sticky ml-auto col-auto"><i class="fa fa-search"></i></button>
				
<div class="itng-search-sticky">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>

			</div>
		</div>
	</div>
</div>

<div id="itng-back-to-top" class="show"><i class="fa fa-chevron-up" aria-hidden="true"></i></div>

		<script type="text/javascript">
							jQuery("#post-270 .entry-meta .date").css("display","none");
					jQuery("#post-270 .entry-date").css("display","none");
					jQuery("#post-270 .posted-on").css("display","none");
							jQuery("#post-82 .entry-meta .date").css("display","none");
					jQuery("#post-82 .entry-date").css("display","none");
					jQuery("#post-82 .posted-on").css("display","none");
							jQuery("#post-322 .entry-meta .date").css("display","none");
					jQuery("#post-322 .entry-date").css("display","none");
					jQuery("#post-322 .posted-on").css("display","none");
							jQuery("#post-127 .entry-meta .date").css("display","none");
					jQuery("#post-127 .entry-date").css("display","none");
					jQuery("#post-127 .posted-on").css("display","none");
				</script>
	<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_2b1ae4cca3cc8d12c39be42768565308.js" id="big-slide-js"></script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_ccdf893e7d8b26933af0c336bcc3943e.js" id="owl-js-js"></script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/jquery.magnific-popup.min.js" id="mag-lightbox-js-js"></script>
<script id="itng-custom-js-js-extra">
var itng = {"toTopEnable":"1","stickyNav":""};
</script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_ea8874ba65dbd53bf5c7fb5c619ac579.js" id="itng-custom-js-js"></script>
<script src="./Useful and efficient algorithms for secp256k1 elliptic curve - «CRYPTO DEEP TECH»_files/wmac_single_6ec0e9b3201c83a442e24aba829a5f05.js" id="itng-navigation-js"></script>
<!-- Yandex.Metrika counter --> <script type="text/javascript"> (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)}; m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)}) (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym"); ym(89424273, "init", {  id:89424273, clickmap:true, trackLinks:true, webvisor:true, accurateTrackBounce:true }); </script> <noscript><div><img src="https://mc.yandex.ru/watch/89424273" style="position:absolute; left:-9999px;" alt="" /></div></noscript> <!-- /Yandex.Metrika counter -->
<!-- Yandex.Metrika counter -->
<script type="text/javascript">
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   var z = null;m[i].l=1*new Date();
   for (var j = 0; j < document.scripts.length; j++) {if (document.scripts[j].src === r) { return; }}
   k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(89995532, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true,
        webvisor:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/89995532" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
<!-- /Yandex.Metrika counter -->


</body></html>