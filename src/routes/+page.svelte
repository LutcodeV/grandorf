<script>
	import TestForm from "../components/test-form.svelte";
</script>

<section class="hero section">
	<div class="container">
		<h1 class="section__title hero__title">Как подобрать полезный <br> рацион для вашего питомца?</h1>
	</div>
</section>

<section class="about section">
	<div class="container">
		<div class="about-item">
			<p class="about-item__title">Насколько важна клетчатка в рационе?</p>
			<img src="assets/images/about-element-01.png" alt="" class="about-item__img">
		</div>
		<div class="about-item">
			<p class="about-item__title">Какое мясо  полезнее питомцу <br> и в каком количестве его давать?</p>
			<img src="assets/images/about-element-02.png" alt="" class="about-item__img">
		</div>
		<div class="about-item">
			<p class="about-item__title">Почему питомец ест траву?</p>
			<img src="assets/images/about-element-03.png" alt="" class="about-item__img">
		</div>
		<div class="about-item">
			<p class="about-item__title">Какой корм лучше, сухой или влажный?</p>
			<img src="assets/images/about-element-04.png" alt="" class="about-item__img">
		</div>
	</div>
</section>

<section class="dogs section">
	<picture>
		<source srcset="assets/images/dogs-mobile.png" media="(max-width: 767px)">
		<source srcset="assets/images/dogs-tablet.png" media="(max-width: 1023px)">
		<img src="assets/images/dogs-desktop.png" alt="" class="dogs__img">
	</picture>
</section>

<section class="advice section">
	<img src="assets/images/advice-decor.png" alt="" class="advice__decor">
	<div class="container">
		<p class="section__title advice__title">Советы экспертов</p>
		<div class="advice__items">
			<div class="advice-item">
				<p class="advice-item__number">
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M29.411 12.8909C34.8431 6.3697 44.8579 6.3697 50.29 12.8909C52.3559 15.3711 55.2374 17.0347 58.4183 17.5838C66.7818 19.0275 71.7892 27.7005 68.8577 35.6654C67.7428 38.6947 67.7428 42.0219 68.8577 45.0512C71.7892 53.0161 66.7818 61.6892 58.4183 63.1329C55.2374 63.6819 52.3559 65.3456 50.29 67.8257C44.8579 74.3469 34.8431 74.3469 29.411 67.8257C27.3451 65.3456 24.4636 63.6819 21.2827 63.1329C12.9192 61.6892 7.9118 53.0161 10.8433 45.0512C11.9582 42.0219 11.9582 38.6947 10.8433 35.6654C7.9118 27.7006 12.9192 19.0275 21.2827 17.5838C24.4636 17.0347 27.3451 15.3711 29.411 12.8909Z" fill="#DFB17C"/>
					</svg>
					1
				</p>
				<p class="advice-item__title">Влияние клетчатки на организм питомца</p>
				<p class="advice-item__text">Клетчатка помогает поддерживать здоровый уровень pH в кишечнике питомца, препятствуя росту нежелательных бактерий.</p>
			</div>
			<div class="advice-item">
				<p class="advice-item__number">
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M29.411 12.8909C34.8431 6.3697 44.8579 6.3697 50.29 12.8909C52.3559 15.3711 55.2374 17.0347 58.4183 17.5838C66.7818 19.0275 71.7892 27.7005 68.8577 35.6654C67.7428 38.6947 67.7428 42.0219 68.8577 45.0512C71.7892 53.0161 66.7818 61.6892 58.4183 63.1329C55.2374 63.6819 52.3559 65.3456 50.29 67.8257C44.8579 74.3469 34.8431 74.3469 29.411 67.8257C27.3451 65.3456 24.4636 63.6819 21.2827 63.1329C12.9192 61.6892 7.9118 53.0161 10.8433 45.0512C11.9582 42.0219 11.9582 38.6947 10.8433 35.6654C7.9118 27.7006 12.9192 19.0275 21.2827 17.5838C24.4636 17.0347 27.3451 15.3711 29.411 12.8909Z" fill="#DFB17C"/>
					</svg>
					2
				</p>
				<p class="advice-item__title">Роль мяса для организма питомца</p>
				<p class="advice-item__text">Мясо считается источником полезных веществ для питомца: оно дает энергию, восстанавливает силы. Поэтому при выборе корма, нужно выбрать корм в котором содержится до 70% мяса и животных ингредиентов.</p>
			</div>
			<div class="advice-item">
				<p class="advice-item__number">
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M29.411 12.8909C34.8431 6.3697 44.8579 6.3697 50.29 12.8909C52.3559 15.3711 55.2374 17.0347 58.4183 17.5838C66.7818 19.0275 71.7892 27.7005 68.8577 35.6654C67.7428 38.6947 67.7428 42.0219 68.8577 45.0512C71.7892 53.0161 66.7818 61.6892 58.4183 63.1329C55.2374 63.6819 52.3559 65.3456 50.29 67.8257C44.8579 74.3469 34.8431 74.3469 29.411 67.8257C27.3451 65.3456 24.4636 63.6819 21.2827 63.1329C12.9192 61.6892 7.9118 53.0161 10.8433 45.0512C11.9582 42.0219 11.9582 38.6947 10.8433 35.6654C7.9118 27.7006 12.9192 19.0275 21.2827 17.5838C24.4636 17.0347 27.3451 15.3711 29.411 12.8909Z" fill="#DFB17C"/>
					</svg>
					3
				</p>
				<p class="advice-item__title">Питомец ест траву. Почему?</p>
				<p class="advice-item__text">Не всегда можно определить причину, по которой собака ест траву. Будьте внимательны к таким проявлениям, чтобы вовремя заметить проблемы со здоровьем питомца.</p>
			</div>
			<div class="advice-item">
				<p class="advice-item__number">
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M29.411 12.8909C34.8431 6.3697 44.8579 6.3697 50.29 12.8909C52.3559 15.3711 55.2374 17.0347 58.4183 17.5838C66.7818 19.0275 71.7892 27.7005 68.8577 35.6654C67.7428 38.6947 67.7428 42.0219 68.8577 45.0512C71.7892 53.0161 66.7818 61.6892 58.4183 63.1329C55.2374 63.6819 52.3559 65.3456 50.29 67.8257C44.8579 74.3469 34.8431 74.3469 29.411 67.8257C27.3451 65.3456 24.4636 63.6819 21.2827 63.1329C12.9192 61.6892 7.9118 53.0161 10.8433 45.0512C11.9582 42.0219 11.9582 38.6947 10.8433 35.6654C7.9118 27.7006 12.9192 19.0275 21.2827 17.5838C24.4636 17.0347 27.3451 15.3711 29.411 12.8909Z" fill="#DFB17C"/>
					</svg>
					4
				</p>
				<p class="advice-item__title">Выбор между сухим и влажным кормом.</p>
				<p class="advice-item__text">Сухой корм следует давать питомцу на завтрак и в течение дня, а влажный корм оставлять на ужин. В составе продукта должны преобладать мясные ингредиенты.</p>
			</div>
		</div>
	</div>
</section>

<section class="test section">
	<picture>
		<source srcset="assets/images/test-bg-mobile.png" media="(max-width: 767px)">
		<source srcset="assets/images/test-bg-tablet.png" media="(max-width: 1023px)">
		<img src="assets/images/test-bg-desktop.png" alt="" class="test__img">
	</picture>
	<p class="test__title">Какой корм подходит вашему питомцу?</p>
	<div class="container">
		<TestForm />
	</div>
</section>

<section class="recommendation">
	<div class="container">
		<p class="section__title recomendation__title">Подобрали для вашего питомца</p>

		<!-- TODO: add recomendation -->
	</div>
</section>

<style>
	:global(body) {
		margin: 0;
		padding: 0;
	}

	@font-face {
		font-family: "GT Eesti Pro Display";
		src: url("/assets/fonts/gteestiprodisplay_regular.otf");
		font-weight: 400;
	}
	@font-face {
		font-family: "GT Eesti Pro Display";
		src: url("/assets/fonts/gteestiprodisplay_medium.otf");
		font-weight: 500;
	}
	@font-face {
		font-family: "GT Eesti Pro Text";
		src: url("/assets/fonts/gteestiprotext_regular.otf");
		font-weight: 400;
	}
	@font-face {
		font-family: "GT Eesti Pro Text";
		src: url("/assets/fonts/gteestiprotext_medium.otf");
		font-weight: 500;
	}
	@font-face {
		font-family: "GT Eesti Pro Text";
		src: url("/assets/fonts/gteestiprotext_bold.otf");
		font-weight: 700;
	}

	* {
		box-sizing: border-box;
		margin: 0;
		padding: 0;
		font-family: "GT Eesti Pro Display";
	}

	.container {
		padding: 0px 32px;
		max-width: 1264px;
		width: 100%;
		margin: 0 auto;
	}
	.section__title {
		color: #4C3125;
		font-size: 80px;
		font-weight: 400;
		line-height: 100%;
		letter-spacing: -1.6px;
	}

	.hero {
		display: flex;
		position: relative;
		background: url("/assets/images/hero-bg-desktop.png") no-repeat;
		height: 956px;
		background-size: cover;
		background-position: right;
		padding-top: 137px;
	}
	.hero__title {
		max-width: 644px;
	}

	.about {
		margin-top: -192px;
		position: relative;
		z-index: 1;
	}
	.about .container {
		display: flex;
		gap: 40px;
		flex-wrap: wrap;
	}

	.about-item {
		flex: 1 1 0;
		display: flex;
		flex-direction: column;
		min-height: 292px;
		position: relative;
		background: #DFB17C;
		padding: 24px;
	}
	.about-item__title {
		color: #4C3125;
		font-size: 28px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 28px */
	}
	.about-item__img {
		position: absolute;
		bottom: 0;
		left: 50%;
		transform: translateX(-50%);
	}
	.about-item:nth-child(1) .about-item__img {
		bottom: -27px;
	}
	.about-item:nth-child(2) .about-item__img {
		bottom: -24px;
	}
	.about-item:nth-child(3) .about-item__img {
		bottom: 0;
	}
	.about-item:nth-child(4) .about-item__img {
		bottom: -20px;
	}

	.dogs__img {
		width: 100%;
	}

	.advice {
		position: relative;
		overflow: hidden;
		padding: 150px 0px 100px;
	}
	.advice__decor {
		position: absolute;
		top: 0;
		right: 0;
		z-index: -1;
	}
	.advice__items {
		display: flex;
		gap: 40px;
		flex-wrap: wrap;
		margin-top: 70px;
	}

	.advice-item {
		flex: 1 1 0;
		display: flex;
		flex-direction: column;
		position: relative;
		background: #4C3125;
		padding: 64px 26px 24px 24px;
	}
	.advice-item__number {
		position: absolute;
		font-family: "GT Eesti Pro Text";
		left: 16px;
		top: -30px;
		color: #FFF3DC;
		text-align: center;
		font-size: 40px;
		font-style: normal;
		font-weight: 700;
		line-height: 100%;
		width: 80px;
		height: 80px;
		z-index: 1;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.advice-item__number svg {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		z-index: -1;
		width: 100%;
		height: 100%;
	}
	.advice-item__title {
		color: #FFEDD9;
		font-size: 28px;
		font-weight: 500;
		line-height: 100%; /* 28px */
	}
	.advice-item__text {
		color: #FFEDD9;
		font-family: "GT Eesti Pro Text";
		font-size: 18px;
		font-weight: 400;
		line-height: 140%; /* 25.2px */
		margin-top: 16px;
	}

	.test {
		display: flex;
		flex-direction: column;
		position: relative;
	}
	.test .container {
		margin-top: -289px;
	}
	.test__img {
		max-width: 100%;
		width: 100%;
		height: auto;
		max-height: 825px;
    object-fit: contain;
	}
	.test__title {
		color: #FFEDD9;
		text-align: center;
		font-family: "GT Eesti Pro Display";
		font-size: 60px;
		width: 100%;
		font-weight: 400;
		line-height: 100%; /* 60px */
		letter-spacing: -1.8px;
		position: absolute;
		left: 50%;
		transform: translate(-50%, 0);
		top: 285px;
		max-width: 535px;
		z-index: 1;
	}

	.recommendation {
		margin-top: 150px;
	}

	@media (max-width: 1023px) {
		.container {
			padding: 0px 24px;
		}

		.section__title {
			font-size: 55px;
			letter-spacing: -1.1px;
		}

		.hero {
			background: url("/assets/images/hero-bg-tablet.png") no-repeat;
			height: 818px;
			background-size: cover;
			background-position: right;
			padding-top: 42px;
		}

		.about {
			margin-top: -54px;
		}
		.about .container {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			gap: 40px 20px;
		}

		.about-item {
			width: 100%;
			height: 200px;
			min-height: 200px;
		}
		.about-item:nth-child(1) .about-item__img {
			bottom: -20px;
			height: 98px;
			width: 220px;
		}
		.about-item:nth-child(2) .about-item__img {
			bottom: -20px;
			width: 158px;
			height: 97px;
		}
		.about-item:nth-child(3) .about-item__img {
			bottom: 0;
			width: 206px;
			height: 131px;
		}
		.about-item:nth-child(4) .about-item__img {
			bottom: -13px;
			width: 146px;
			height: 97px;
		}

		.advice {
			padding: 60px 0px;
		}
		.advice__decor {
			display: none;
		}
		.advice__items {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			gap: 50px 20px;
			margin-top: 40px;
		}
		.advice-item {
			padding: 42px 30px 24px 24px;
		}
		.advice-item__number {
			font-size: 30px;
			width: 60px;
			height: 60px;
		}

		.test__img {
			object-fit: cover;
		}
		.test__title {
			top: 274px;
		}
		.test .container {
			margin-top: -312px;
		}

		.recommendation {
			margin-top: 60px;
		}
	}
	@media (max-width: 767px) {
		.container {
			padding: 0px 32px;
		}

		.section__title {
			font-size: 30px;
			letter-spacing: -0.6px;
		}

		.hero {
			background: url("/assets/images/hero-bg-mobile.png") no-repeat;
			height: 512px;
			background-size: cover;
			background-position: center;
			padding-top: 30px;
		}
		.hero__title {
			max-width: 296px;
		}

		.about-item {
			padding: 12px;
			height: 170px;
			min-height: 170px;
		}
		.about-item:nth-child(3),
		.about-item:nth-child(4) {
			height: 150px;
			min-height: 150px;
		}
		.about-item__title {
			font-size: 18px;
		}
		.about-item:nth-child(1) .about-item__img {
			bottom: -12px;
			height: 58px;
			width: 132px;
		}
		.about-item:nth-child(2) .about-item__img {
			bottom: -12px;
			width: 100px;
			height: 62px;
		}
		.about-item:nth-child(3) .about-item__img {
			bottom: 0;
			width: 108px;
			height: 68px;
		}
		.about-item:nth-child(4) .about-item__img {
			bottom: 10px;
			width: 86px;
			height: 57px;
		}

		.advice {
			padding: 60px 0px 30px;
		}
		.advice__items {
			display: flex;
			gap: 10px;
			overflow: auto;
			flex-wrap: nowrap;
			padding: 16px 32px 0px;
			width: calc(100% + 64px);
			margin-left: -32px;
			margin-right: -32px;
			margin-top: 20px;
		}
		.advice-item {
			min-width: 220px;
			padding: 32px 14px 12px 12px;
		}
		.advice-item__number {
			width: 40px;
			height: 40px;
			top: -16px;
			left: 0;
			font-size: 20px;
		}
		.advice-item__title {
			font-size: 18px;
		}
		.advice-item__text {
			margin-top: 16px;
			font-size: 14px;
		}

		.test__img {
			object-fit: cover;
			max-height: 480px;
		}
		.test__title {
			top: 164px;
			max-width: 249px;
			font-size: 30px;
		}
		.test .container {
			margin-top: -107px;
		}
	}
</style>
