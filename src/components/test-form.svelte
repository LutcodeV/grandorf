<script>
	let step = $state(0);
	let form = $state({
		animalType: null,
		name: '',
		sex: '',
		age: '',
		breed: '',
		weight: '',
	})
	let error = $state(false);
	let openDropdown = $state(false);

	const buttonHandler = () => {
		if((form.animalType === null && step === 0) || (form.name === '' && step === 1) || (form.sex === '' && step === 2) || (form.age === '' && step === 3) || (form.breed === '' && step === 4) || (form.weight === '' && step === 5)) {
			error = true
			return
		}
		step += 1
		error = false
	}
</script>

<form class="test-form">
	{#if step !== 0}
		<div class="test-form__top">
			<button class="test-form__back" type="button" onclick={() => {
				if(step === 6) {
					step = 0
					form = {
						animalType: null,
						name: '',
						sex: '',
						age: '',
						breed: '',
						weight: '',
					}
					error = false
				}
				else step -= 1; error = false
				}}>
				{step === 6 ? "← пройти тест еще раз" : '← Назад'}</button>
			<div class="test-form__progress" style="--step: {step}">
				<p class="test-form__progress-value">{step < 5 ? step : 5} / 5</p>
			</div>
		</div>
	{/if}
	<div class="test-form__header">
		{#if step === 0}
		<p class="test-form__title">Расскажите о вашем питомце, и мы подберем подходящий рацион правильного питания</p>
		<p class="test-form__title">В конце предложим скидку</p>
		{:else if step === 1}
		<p class="test-form__title">Как зовут вашего питомца?</p>
		{:else if step === 2}
		<p class="test-form__title">Мальчик или девочка?</p>
		{:else if step === 3}
		<p class="test-form__title">Примерный возраст?</p>
		{:else if step === 4}
		<p class="test-form__title">Какая порода?</p>
		{:else if step === 5}
		<p class="test-form__title">Какого размера питомец?</p>
		{:else if step === 6}
		<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg" class="test-form__checkmark">
			<circle cx="40" cy="40" r="40" fill="#DFB17C" fill-opacity="0.1"/>
			<path d="M33 55.7082C32.4428 55.7084 31.891 55.5987 31.3762 55.3854C30.8614 55.172 30.3937 54.8592 30 54.4648L20.7317 45.2015L24.2684 41.6665L33 50.3982L55.7317 27.6665L59.2684 31.2015L36 54.4648C35.6063 54.8592 35.1387 55.172 34.6239 55.3854C34.1091 55.5987 33.5573 55.7084 33 55.7082Z" fill="#DFB17C"/>
		</svg>
		<p class="test-form__title">Тест успешно пройден. <br> Корм для Вашего питомца подобран!</p>
		<p class="test-form__promocode">ПРОМОКОД123</p>
		<p class="test-form__text">Вам доступна скидка на всю продукцию рациона 20% по промокоду:</p>
		{/if}
	</div>
	<div class="test-form__content">
		{#if step === 0}
			<div class="test-form__step" >
				<button type="button" class="test-form__select-button" class:selected={form.animalType === 'cat'} onclick={() => form.animalType = 'cat'}>
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M78.1567 0.349888C77.0233 -0.216779 75.67 -0.0934457 74.6667 0.666554L69.0333 4.88989C66.7767 3.89322 64.2867 3.33322 61.6667 3.33322C59.0467 3.33322 56.5567 3.89655 54.3 4.88989L48.6667 0.666554C47.6567 -0.0934457 46.3033 -0.216779 45.1767 0.349888C44.0467 0.913221 43.3333 2.06989 43.3333 3.33322V21.6666C43.3333 31.7766 51.5567 39.9999 61.6667 39.9999C71.7767 39.9999 80 31.7766 80 21.6666V3.33322C80 2.06989 79.2867 0.916554 78.1567 0.349888ZM80 76.6632C80 78.5066 78.5067 79.9966 76.6667 79.9966H60V73.3299C60 63.6132 53.0367 55.4932 43.84 53.6999C41.8367 53.3099 40 54.9599 40 57.0032V57.0166C40 58.6332 41.1767 59.9499 42.76 60.2866C48.79 61.5632 53.3333 66.9266 53.3333 73.3332V79.9999H21.86C11.1133 79.9999 0 73.1399 0 61.6666C0 54.5499 3.15 49.4699 5.93 44.9866C8.11333 41.4666 10 38.4232 10 34.9999C10 31.2166 9.07667 27.6832 2.97667 26.8499C1.29667 26.6199 0 25.2432 0 23.5499C0 21.5732 1.73 19.9699 3.69 20.2266C14.88 21.6932 16.6667 29.9099 16.6667 34.9999C16.6667 40.3232 14.09 44.4799 11.5967 48.5032C9.06333 52.5899 6.66667 56.4499 6.66667 61.6666C6.66667 67.6366 11.5567 71.1699 16.6567 72.5965C16.68 68.2666 17.87 45.9766 39.0533 35.6732C39.5833 35.4399 40.0767 35.2366 40.5733 35.0299C45.0133 42.0099 52.7967 46.6666 61.6667 46.6666C65.88 46.6666 69.8467 45.6099 73.3333 43.7599V73.3332H76.6667C78.5067 73.3332 80 74.8232 80 76.6632Z" fill="#4C3125"/>
					</svg>
					Кот
				</button>
				<button type="button" class="test-form__select-button" class:selected={form.animalType === 'dog'} onclick={() => form.animalType = 'dog'}>
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M73.3333 16.6669H72.06C71.03 16.6669 70.1067 16.0969 69.6467 15.1769C68.05 11.9836 64.84 10.0002 61.2733 10.0002H56.6667V2.56689C56.6667 0.816894 54.9267 -0.446439 53.2833 0.146894C49.4267 1.53356 46.6667 5.22356 46.6667 9.56023V15.0002L43.4533 24.4636C42.9767 25.7802 41.7167 26.6636 40.32 26.6669L23.3267 26.6769C19.69 26.6769 16.3267 27.8536 13.5833 29.8369C11.5833 28.9136 6.66667 26.0336 6.66667 20.0002C6.66667 18.1602 5.17333 16.6669 3.33333 16.6669C1.49333 16.6669 0 18.1602 0 20.0002C0 28.2402 5.32 32.7802 8.96 34.9202C7.50333 37.3936 6.67 40.2736 6.67 43.3469L6.67667 71.6902C6.67667 76.2802 10.4167 80.0169 15.0067 80.0169C19.5967 80.0169 23.3367 76.2802 23.3367 71.6869V60.0002L43.3367 59.9902V71.6702C43.3367 76.2636 47.0767 80.0036 51.67 80.0036C56.2633 80.0036 60.0033 76.2636 60.0033 71.6702V60.7869C60.0033 59.4536 60.14 58.1169 60.4033 56.8102L67.27 36.3169C74.3467 36.0036 80.0033 30.1469 80.0033 22.9969C80.0033 19.9302 77.6667 16.6702 73.3367 16.6702L73.3333 16.6669Z" fill="#4C3125"/>
					</svg>
					Собака
				</button>
			</div>
		{:else if step === 1}
			<div class="test-form__step" >
				<input class="test-form__input" type="text" placeholder="Имя" bind:value={form.name}>
			</div>
		{:else if step === 2}
			<div class="test-form__step" >
				<button type="button" class="test-form__select-button" class:selected={form.sex === 'male'} onclick={() => form.sex = 'male'}>
					<svg width="80" height="80" viewBox="0 0 80 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M70.039 0H53.4374C51.6037 0 50.1171 1.48906 50.1171 3.32578C50.1171 5.1625 51.6037 6.65156 53.4374 6.65156H68.6645L45.9799 29.3736C33.703 19.6736 15.9001 21.7791 6.21617 34.0762C-3.46773 46.3734 -1.36586 64.2056 10.911 73.9056C23.1879 83.6056 40.9909 81.5002 50.6748 69.203C58.7857 58.9034 58.7857 44.3759 50.6748 34.0764L73.3595 11.3544V26.6066C73.3595 28.4434 74.846 29.9323 76.6798 29.9323C78.5135 29.9323 80.0001 28.4433 80.0001 26.6066V9.9775C80.0001 4.46703 75.5404 0 70.039 0ZM28.5348 73.168C16.6152 73.168 6.95258 63.4894 6.95258 51.5502C6.95258 39.6109 16.6152 29.9323 28.5348 29.9323C40.4543 29.9323 50.117 39.6109 50.117 51.5502C50.1024 63.4833 40.4482 73.1533 28.5348 73.168Z" fill="#4C3125"/>
					</svg>
					Мальчик
				</button>
				<button type="button" class="test-form__select-button" class:selected={form.sex === 'female'} onclick={() => form.sex = 'female'}>
					<svg width="54" height="80" viewBox="0 0 54 80" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M53.6666 26.6665C53.6706 21.5337 52.1932 16.5088 49.4117 12.195C46.6302 7.88113 42.6629 4.46169 37.9858 2.34712C33.3088 0.232536 28.1209 -0.487324 23.0449 0.273943C17.9688 1.03521 13.2203 3.24526 9.3694 6.63879C5.51846 10.0323 2.72872 14.4651 1.33505 19.4051C-0.0586171 24.3451 0.00301419 29.5824 1.51255 34.4882C3.02208 39.394 5.91536 43.76 9.84509 47.0619C13.7748 50.3639 18.574 52.4616 23.6666 53.1032V63.3332H16.9999C16.1159 63.3332 15.268 63.6844 14.6429 64.3095C14.0178 64.9346 13.6666 65.7825 13.6666 66.6665C13.6666 67.5506 14.0178 68.3984 14.6429 69.0236C15.268 69.6487 16.1159 69.9999 16.9999 69.9999H23.6666V76.6665C23.6666 77.5506 24.0178 78.3984 24.6429 79.0236C25.268 79.6487 26.1159 79.9999 26.9999 79.9999C27.884 79.9999 28.7318 79.6487 29.3569 79.0236C29.9821 78.3984 30.3332 77.5506 30.3332 76.6665V69.9999H36.9999C37.884 69.9999 38.7318 69.6487 39.3569 69.0236C39.9821 68.3984 40.3332 67.5506 40.3332 66.6665C40.3332 65.7825 39.9821 64.9346 39.3569 64.3095C38.7318 63.6844 37.884 63.3332 36.9999 63.3332H30.3332V53.1032C36.7716 52.2863 42.6918 49.1518 46.9864 44.286C51.281 39.4202 53.6558 33.1565 53.6666 26.6665ZM6.99991 26.6665C6.99991 22.7109 8.17289 18.8441 10.3705 15.5551C12.5681 12.2661 15.6917 9.70269 19.3462 8.18894C23.0008 6.67519 27.0221 6.27912 30.9017 7.05083C34.7813 7.82253 38.345 9.72735 41.142 12.5244C43.9391 15.3214 45.8439 18.8851 46.6156 22.7647C47.3873 26.6443 46.9913 30.6657 45.4775 34.3202C43.9638 37.9747 41.4003 41.0983 38.1113 43.2959C34.8223 45.4936 30.9555 46.6665 26.9999 46.6665C21.6972 46.6612 16.6132 44.5524 12.8636 40.8028C9.11404 37.0532 7.00521 31.9692 6.99991 26.6665Z" fill="#4C3125"/>
					</svg>
					Девочка
				</button>
			</div>
		{:else if step === 3}
			<div class="test-form__step" >
				<div class="test-form__radios">
					<label class="test-form-radio">
						<input type="radio" bind:group={form.age} class="test-form-radio__input" name="age" value="До 1,5 лет">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">До 1,5 лет</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.age} class="test-form-radio__input" name="age" value="1,5 – 7 лет">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">1,5 – 7 лет</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.age} class="test-form-radio__input" name="age" value="7 – 12 лет">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">7 – 12 лет</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.age} class="test-form-radio__input" name="age" value="Больше 12 лет">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">Больше 12 лет</div>
					</label>
				</div>
			</div>
		{:else if step === 4}
			<div class="test-form__step">
				<div class="test-form-dropdown">
					<button type="button" class="test-form-dropdown__header" onclick={() => openDropdown = !openDropdown}>
						<p class="test-form-dropdown__title">
							{form.breed !== '' ? form.breed : 'Выберите породу'}
						</p>
						<svg width="16" height="11" viewBox="0 0 16 11" fill="none" xmlns="http://www.w3.org/2000/svg">
							<path d="M8.77145 10.0647C8.37147 10.5496 7.62853 10.5496 7.22854 10.0647L0.68933 2.13628C0.151372 1.48404 0.615317 0.5 1.46079 0.5L14.5392 0.500002C15.3847 0.500002 15.8486 1.48405 15.3107 2.13629L8.77145 10.0647Z" fill="#4C3125"/>
						</svg>
					</button>
					<div class="test-form-dropdown__content" class:active={openDropdown}>
						<button type="button" class="test-form-dropdown__button" onclick={() => {form.breed = "Не знаю породу"; openDropdown = false}}>Не знаю породу</button>
						<button type="button" class="test-form-dropdown__button" onclick={() => {form.breed = "Без породы (Метис)"; openDropdown = false}}>Без породы (Метис)</button>
						<button type="button" class="test-form-dropdown__button" onclick={() => {form.breed = "Порода 1"; openDropdown = false}}>Порода 1</button>
						<button type="button" class="test-form-dropdown__button" onclick={() => {form.breed = "Порода 2"; openDropdown = false}}>Порода 2</button>
					</div>
				</div>
			</div>
		{:else if step === 5}
			<div class="test-form__step" >
				<div class="test-form__radios">
					<label class="test-form-radio">
						<input type="radio" bind:group={form.weight} class="test-form-radio__input" name="weight" value="До 4 кг">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">До 4 кг</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.weight} class="test-form-radio__input" name="weight" value="4 – 10 кг">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">4 – 10 кг</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.weight} class="test-form-radio__input" name="weight" value="11 – 25 кг">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">11 – 25 кг</div>
					</label>
					<label class="test-form-radio">
						<input type="radio" bind:group={form.weight} class="test-form-radio__input" name="weight" value="26 – 45 кг">
						<div class="test-form-radio__box"></div>
						<div class="test-form-radio__text">26 – 45 кг</div>
					</label>
				</div>
			</div>
		{/if}
		{#if error}
			<p class="test-form__error">Заполните данные</p>
		{/if}
	</div>
	<div class="test-form__footer">
		{#if step !== 6}
			<button class="test-form__button" type="button" onclick={() => buttonHandler()}>
				<span>
					продолжить
				</span>
				<div class="test-form__button-arrow">
					<svg width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path fill-rule="evenodd" clip-rule="evenodd" d="M14.9289 1.16104L22.8839 9.11599C23.372 9.60415 23.372 10.3956 22.8839 10.8838L14.9289 18.8387C14.4408 19.3269 13.6493 19.3269 13.1612 18.8387C12.673 18.3506 12.673 17.5591 13.1612 17.0709L18.9822 11.2499H2C1.30964 11.2499 0.75 10.6902 0.75 9.99987C0.75 9.30952 1.30964 8.74987 2 8.74987H18.9822L13.1612 2.92881C12.673 2.44065 12.673 1.64919 13.1612 1.16104C13.6493 0.672883 14.4408 0.672883 14.9289 1.16104Z" fill="#FFEDD9"/>
					</svg>
				</div>
			</button>
			{:else}
			<button class="test-form__button test-form__button--solid" type="button">
				Купить со скидкой
			</button>
		{/if}
	</div>
</form>

<style>
	.test-form {
		background: #F8F8F8;
		padding: 60px 0px;
		min-height: 504px;
		height: auto;
		display: flex;
		box-sizing: border-box;
		flex-direction: column;
	}
	.test-form__header {
		max-width: 637px;
		margin: 0 auto;
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	.test-form__checkmark {
		margin-bottom: 30px;
	}
	.test-form__promocode {
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 22px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 22px */
		letter-spacing: 0.44px;
		text-transform: uppercase;
		border-radius: 500px;
		border: 2px solid rgba(76, 49, 37, 0.20);
		padding: 16px;
		outline: none;
		width: auto;
		background: transparent;
		margin: 20px auto 0px;
	}
	.test-form__text {
		color: #4C3125;
		text-align: center;
		font-family: "GT Eesti Pro Display";
		font-size: 18px;
		font-style: normal;
		font-weight: 400;
		line-height: 100%; /* 18px */
		margin: 20px auto 0px;
		max-width: 326px;
	}
	.test-form__title {
		color: #4C3125;
		text-align: center;
		font-size: 28px;
		font-weight: 500;
		line-height: 100%; /* 28px */
		margin: 0px;
	}
	.test-form__title + .test-form__title {
		margin-top: 20px;
	}
	.test-form__content {
		max-width: 374px;
		width: 100%;
		margin: 60px auto 0;
	}
	.test-form__error {
		color: #DE2525;
		font-family: "GT Eesti Pro Text";
		font-size: 14px;
		font-weight: 500;
		line-height: 100%; /* 14px */
		letter-spacing: 0.28px;
		text-transform: uppercase;
	}
	.test-form__step {
		display: flex;
		align-items: center;
		gap: 40px;
	}
	.test-form__select-button {
		display: flex;
		align-items: center;
		gap: 8px;
		cursor: pointer;
		border-radius: 40px;
		background: #FFF;
		padding: 28px 0px;
		flex-direction: column;
		width: 100%;
		border: 0;
		transition: .3s ease;
		color: #4C3125;
		text-align: center;
		font-size: 34px;
		font-weight: 500;
		line-height: 100%; /* 34px */
		font-family: "GT Eesti Pro Display";
	}
	.test-form__select-button.selected {
		background: #DFB17C;
	}
	.test-form__footer {
		max-width: 374px;
		margin: auto auto 0;
		width: 100%;
	}
	.test-form__button {
		display: flex;
		align-items: center;
		justify-content: space-between;
		border-radius: 500px;
		border: 0;
		box-shadow: inset 0px 0px 0px 4px #4C3125;
		padding: 8px 8px 8px 28px;
		width: 100%;
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 22px;
		font-weight: 500;
		line-height: 100%; /* 22px */
		letter-spacing: 0.44px;
		text-transform: uppercase;
		cursor: pointer;
		margin-top: 40px;
	}
	.test-form__button--solid {
		border-radius: 500px;
		border: 4px solid #4C3125;
		background: #4C3125;
		color: #FFEDD9;
		text-align: center;
		align-items: center;
		justify-content: center;
		padding: 24px 8px;
	}
	.test-form__button-arrow {
		width: 48px;
		height: 48px;
		border-radius: 50%;
		background: #4C3125;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.test-form__top {
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
		margin-bottom: 24px;
		width: 100%;
	}
	.test-form__back {
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 14px;
		font-weight: 500;
		line-height: 100%; /* 14px */
		letter-spacing: 0.28px;
		text-transform: uppercase;
		position: absolute;
		left: 0;
		top: 50%;
		transform: translateY(-50%);
		border: 0;
		background: transparent;
		cursor: pointer;
	}
	.test-form__progress {
		border-radius: 60px;
		background: #FFF;
		max-width: 200px;
		width: 100%;
		height: 26px;
		overflow: hidden;
		position: relative;
	}
	.test-form__progress::before {
		content: "";
		width: calc(var(--step) * 20%);
		height: 100%;
		position: absolute;
		left: 0;
		top: 0;
		background: #DFB17C;
		transition: .3s ease;
	}
	.test-form__progress-value {
		color: #4C3125;
		text-align: center;
		font-family: "GT Eesti Pro Display";
		font-size: 14px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 14px */
		position: absolute;
		left: 50%;
		z-index: 1;
		top: 50%;
		margin: 0;
		transform: translate(-50%, -50%);
	}
	.test-form__input {
		width: 100%;
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 22px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 22px */
		letter-spacing: 0.44px;
		text-transform: uppercase;
		border-radius: 500px;
		border: 2px solid rgba(76, 49, 37, 0.20);
		padding: 16px;
		outline: none;
		background: transparent;
	}
	.test-form__input::placeholder {
		opacity: 0.6;
	}
	.test-form__radios {
		display: flex;
		flex-direction: column;
		gap: 20px;
	}
	.test-form-radio {
		display: flex;
		align-items: center;
		cursor: pointer;
		gap: 10px;
		position: relative;
	}
	.test-form-radio__input {
		position: absolute;
		opacity: 0;
		width: 0;
		height: 0;
		pointer-events: none;
	}
	.test-form-radio__input:checked + .test-form-radio__box::before {
		opacity: 1;
	}
	.test-form-radio__text {
		color: #4C3125;
		text-align: center;
		font-family: "GT Eesti Pro Text";
		font-size: 22px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 22px */
		letter-spacing: 0.44px;
		text-transform: uppercase;
	}
	.test-form-radio__box {
		width: 16px;
		position: relative;
		height: 16px;
		border-radius: 50%;
		border: 3px solid #4C3125;
	}
	.test-form-radio__box::before {
		content: "";
		width: 12px;
		height: 12px;
		border-radius: 50%;
		background: #4C3125;
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		opacity: 0;
		transition: .3s ease;
	}
	.test-form-dropdown {
		position: relative;
		z-index: 1;
		width: 100%;
	}
	.test-form-dropdown__header {
		width: 100%;
		border-radius: 500px;
		border: 2px solid rgba(76, 49, 37, 0.20);
		padding: 16px;
		outline: none;
		background: transparent;
		display: flex;
		align-items: center;
		justify-content: space-between;
		cursor: pointer;
	}
	.test-form-dropdown__title {
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 22px;
		font-style: normal;
		font-weight: 500;
		line-height: 100%; /* 22px */
		letter-spacing: 0.44px;
		text-transform: uppercase;
		margin: 0;
	}
	.test-form-dropdown__content {
		border-radius: 22px;
		background: #FFF;
		padding: 20px;
		display: flex;
		flex-direction: column;
		gap: 20px;
		width: 100%;
		align-items: flex-start;
		opacity: 0;
		pointer-events: none;
		transition: .3s ease;
		position: absolute;
		top: 100%;
		left: 0;
	}
	.test-form-dropdown__content.active {
		opacity: 1;
		pointer-events: all;
	}
	.test-form-dropdown__button {
		background: transparent;
		border: 0;
		padding: 0;
		color: #4C3125;
		font-family: "GT Eesti Pro Text";
		font-size: 18px;
		font-style: normal;
		font-weight: 500;
		width: 100%;
		cursor: pointer;
		text-align: left;
		line-height: 100%; /* 18px */
		letter-spacing: 0.36px;
		text-transform: uppercase;
	}
	@media (max-width: 1023px) {
		.test-form {
			padding: 60px 32px;
			max-height: 566px;
			height: 566px;
		}
	}
	@media (max-width: 767px) {
		.test-form {
			padding: 30px 20px 20px;
			min-height: 373px;
			height: auto;
		}
		.test-form__title {
			font-size: 18px;
		}
		.test-form__title + .test-form__title {
			margin-top: 15px;
		}
		.test-form__content {
			margin-top: 30px;
		}
		.test-form__button {
			margin-top: 20px;
			font-size: 14px;
			padding: 8px 8px 8px 20px;
			box-shadow: inset 0px 0px 0px 2px #4C3125;
		}
		.test-form__button-arrow {
			width: 32px;
			height: 32px;
		}
		.test-form__button-arrow svg {
			width: 16px;
		}
		.test-form__step {
			gap: 10px;
		}
		.test-form__select-button {
			gap: 20px;
			font-size: 18px;
		}
		.test-form__select-button svg {
			width: 60px;
			height: 60px;
		}
		.test-form__top {
			flex-direction: column;
		}
		.test-form__back {
			position: relative;
		}
		.test-form__input {
			font-size: 14px;
		}
	}
</style>
