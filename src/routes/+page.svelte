<script>
	let date = new Date();
	let begin = new Date();

	begin.setMonth(0);
	begin.setDate(0);

	// For testing other dates
	// date.setMonth(11);
	// date.setDate(30);

	begin = begin.getTime();
	date = date.getTime();

	// Convert date into days from the beginning of the year for the second of alternating dates
	date = date - begin;
	date = date / (1000 * 60 * 60 * 24);

	const dayOfYear = date;

	let child = dayOfYear % 2 == 1 ? 'Reid' : 'Alec';
	if(dayOfYear % 7 === 0 ) child = 'Jacob';
	if(dayOfYear > 8 && dayOfYear % 8 === 0 ) child = 'Andres';
</script>

<div class="grid min-h-screen place-content-center text-8xl text-center px-6">
	<h1 class="text-3xl">Chattanooga Chores for Children</h1>
	<div class="mt-4 md:mt-8">
		<p>The date is {new Date().toLocaleDateString()}</p>
		<p>Which means it's...</p>
		<figure class="mt-4 md:mt-8 relative md:max-w-[50vw] mx-auto">
			<img src="wheel.png" class="w-full h-full" alt="" />
			<img
				src="pointer.png"
				alt="Pointer"
				class="spinner spinner--{child} absolute inset-0 m-auto h-[30%]"
			/>
		</figure>
		<h3 class="text-3xl"><span class="text-5xl">{child}</span>, take out the fucking trash.</h3>
	</div>
</div>

<style>
	p {
		@apply text-lg;
	}

	.spinner--Reid {
		animation: spin 0.4s 4 linear, land-reid 1s 1 ease-out;
		transform: translate(18%, -16%) rotate(378deg);
	}
	.spinner--Alec {
		animation: spin 0.4s 4 linear, land-reid 1s 1 ease-out;
		transform: translate(18%, -16%) rotate(578deg);
	}
	.spinner--Andres {
		animation: spin 0.4s 4 linear, land-andres 1s 1 ease-out;
		transform: translate(18%, -16%) rotate(485deg);
	}
	.spinner--Jacob {
		animation: spin 0.4s 4 linear, land-jacob 1s 1 ease-out;
		transform: translate(18%, -16%) rotate(340deg);
	}
	.spinner {
		animation-delay: 0s, 1.6s;
		transform-origin: 50% 65%;
	}
	@keyframes spin {
		0% {
			transform: translate(18%, -16%) rotate(0deg);
		}
		100% {
			transform: translate(18%, -16%) rotate(360deg);
		}
	}
	@keyframes land-reid {
		0% {
			transform: translate(18%, -16%) rotate(0deg);
		}
		100% {
			transform: translate(18%, -16%) rotate(378deg);
		}
	}
	@keyframes land-alec {
		0% {
			transform: translate(18%, -16%) rotate(0deg);
		}
		100% {
			transform: translate(18%, -16%) rotate(578deg);
		}
	}
	@keyframes land-andres {
		0% {
			transform: translate(18%, -16%) rotate(0deg);
		}
		100% {
			transform: translate(18%, -16%) rotate(485deg);
		}
	}
	@keyframes land-jacob {
		0% {
			transform: translate(18%, -16%) rotate(0deg);
		}
		100% {
			transform: translate(18%, -16%) rotate(340deg);
		}
	}
</style>
