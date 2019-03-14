<template>
	<div class="container">
		
		<div class="col-md-6 offset-md-3">
			<div class="card-header">
				<p>Register</p>
			</div>
			<div class="card-body">
				
				<form @submit.prevent="submit">
					<div class="form-group">
						<label>Name</label>
						<input type="text" v-model="form.name" class="form-control" :class="{ 'is-invalid': errors.name }" placeholder="Name">
						<div class="invalid-feedback" v-if="errors.name">
							{{errors.name[0]}}
						</div>
					</div>
					<div class="form-group">
						<label>Email</label>
						<input type="email" v-model="form.email" class="form-control" :class="{ 'is-invalid': errors.email }" placeholder="Email">
						<div class="invalid-feedback" v-if="errors.email">
							{{errors.email[0]}}
						</div>
					</div>
					<div class="form-group">
						<label>Password</label>
						<input type="password" v-model="form.password" class="form-control" :class="{ 'is-invalid': errors.password }" placeholder="Password" name="">
						<div class="invalid-feedback" v-if="errors.password">
							{{errors.password[0]}}
						</div>
					</div>
					
					<div class="form-group">
						<input type="submit" value="register" class="btn btn-primary">
					</div>
				</form>
				
			</div>
		</div>

	</div>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					name: '',
					email: '',
					password: ''					
				}
			}
		},
		methods: {
			async submit() {
				this.$axios.$post('register', this.form)
				.then(data => {

					this.$auth.loginWith("local", {
						data: {
							email: this.form.email,
							password: this.form.password
						}
					});
					console.log(data);
				})
				.catch(err => {
					console.log(err);
				});
			}
		}

	}
</script>
