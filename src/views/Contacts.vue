<template>
	<div>
		<section class="hero is-primary is-bold is-fullheight">
			<div class="hero-body">

				<div class="container">
                    <div class="columns ">
						<div class="column is-4 is-offset-4">
                            <h1 class="title is-size-1">
                                Noxu.in
                            </h1>
                            <h2 class="subtitle is-size-6-mobile">
                                Over 1+ years of doing what we love, building high
                                performance computers and serving Toronto, Canada.
                            </h2>
                            <div class="box">
                                <section>
                                    <h2 class="subtitle has-text-black">Send Us A Message</h2>
                                    <b-field label="First Name">
                                        <b-input placeholder="First Name"
                                                 v-model="fname"
                                                 type="fname"
                                                 icon-right="close-circle"
                                                 icon-right-clickable
                                                 @icon-right-click="clearIconClick">
                                        </b-input>
                                    </b-field>

                                    <b-field label="Last Name">
                                        <b-input placeholder="Last Name"
                                                 v-model="lname"
                                                 type="lname"
                                                 icon-right="close-circle"
                                                 icon-right-clickable
                                                 @icon-right-click="clearIconClick(this)">
                                        </b-input>
                                    </b-field>

                                    <b-field label="Email">
                                        <b-input placeholder="Email"
                                                 v-model="email"
                                                 type="email"
                                                 icon="email"
                                                 icon-right="close-circle"
                                                 icon-right-clickable
                                                 @icon-right-click="clearIconClick(email)">
                                        </b-input>
                                    </b-field>

                                    <b-field label="Phone"
                                             type="is-danger"
                                             message="You can have a message too">
                                        <b-input placeholder="Phone"></b-input>
                                    </b-field>

                                    <b-field label="Info" type="is-info">
                                        <b-input placeholder="Info"></b-input>
                                    </b-field>

                                    <b-field label="Warning" type="is-warning">
                                        <b-input placeholder="Warning"></b-input>
                                    </b-field>

                                    <b-field label="Disabled">
                                        <b-input placeholder="Disabled" disabled></b-input>
                                    </b-field>

                                    <b-field label="Loading">
                                        <b-input placeholder="Loading" loading></b-input>
                                    </b-field>
                                </section>
                            </div>
						</div>
					</div>
				</div>
			</div>
		</section>
        <iframe class="map-iframe" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2879.8691835035634!2d-79.34893274868269!3d43.79632745107879!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89d4d305352684f3%3A0xe9e9da41ae97c69!2s1760%20Finch%20Ave%20E%2C%20North%20York%2C%20ON%20M2J%205G3!5e0!3m2!1sen!2sca!4v1587099105315!5m2!1sen!2sca"
                width="100%" height="4500px" frameborder="0" style="border:0;" allowfullscreen="allowfullscreen"
                aria-hidden="true" tabindex="0"></iframe>
	</div>
</template>

<script>
	// @ is an alias to /src
	import Navbar from "@/components/Navbar"

	export default {
		name: 'home',
		components: {Navbar},
        data() {
            return {
                fname: '',
                lname: '',
                email: '',
            }
        },
        methods: {
            clearIconClick(v) {
                console.log(v)
            }
        }
	}
</script>

<style lang="scss" scoped>
</style>
