<template>
	<section class="section" id="contact">
		<div class="section-container">
			<div class="section-heading">
				<h2>Let's Chat</h2>
			</div>
			<p class="relocate">
				I'm currently based in San Diego, CA.
			</p>

			<div class="form-wrapper">
				<form method="POST" data-netlify="true">
					<div>
						<div class="input-container">
							<input
								type="text"
								name="name"
								id="name"
								required
								placeholder="Name*"
							/>
						</div>
						<div class="input-container">
							<input
								type="email"
								name="email"
								id="email"
								required
								placeholder="Email*"
							/>
						</div>
						<div class="input-container">
							<textarea
								id="massage"
								name="massage"
								required
								placeholder="Message*"
							/>
						</div>
						<div class="button-wrapper">
							<button
								type="submit"
								class="site-btn transition-ease"
								data-wow-delay="0.2s"
							>
								Send Messege
							</button>
						</div>
						<div id="result" />
					</div>
				</form>
			</div>
		</div>
		<Footer />
	</section>
</template>

<script>
import Footer from '~/components/Footer.vue';

export default {
	name: 'Contact',
	components: {
		Footer,
	},
};
</script>

<style lang="scss" scoped>
.relocate {
	//text-align: center;
	margin-bottom: 3rem;
	margin-right: auto;
	margin-left: auto;
	width: 100%;
	color: #ffffffb9;
}
#contact {
	background: #424242;
}
.form-wrapper {
	margin: 0 auto;
	padding-bottom: 5rem;
	@media only screen and (max-width: 600px) {
		width: 100%;
	}
}
form {
	width: 100%;
	overflow: hidden;
	label {
		display: block;
		margin-bottom: 8px;
		font-size: 1.25rem;
	}
	fieldset {
		width: 100%;
		padding: 0;
		border: none;
	}
	input,
	textarea {
		background: #fff;
		width: 100%;
		border: none;
		font-size: 1rem;
		height: 6rem;
		padding: 0.25rem;
		border: 1.25px solid black;
		border-radius: 10px;
		color: black;
    padding-left: 1rem;
	}
	input {
		height: 3.25rem;
		margin-bottom: 1rem;
	}
	.input-container {
		display: flex;
		justify-content: center;
	}
	.button-wrapper {
		display: flex;
		margin: 0 auto;
		padding: 40px 0px;
    justify-content: center;
	}
}

.section-container {
  padding-left: 1rem;
  padding-right: 1rem;
}
</style>
