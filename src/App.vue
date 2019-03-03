<template>
    <div class="container">
        <div class="row">
            <div class="col-12 col-sm-8 offset-md-2 col-md-6 offset-md-3">
                <form>
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->
                    <full-name
                            v-model="userData.fullname"></full-name>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input
                                type="email"
                                id="email"
                                v-model.trim="userData.email"
                                class="form-control" />
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                v-model="userData.password"
                                class="form-control" />
                    </div>
                    <div class="form-group">
                        <label>Store data?</label>
                        <div class="form-check">
                            <label class="form-check-label">
                            <input
                                    type="radio"
                                    value="true"
                                    v-model="userData.storeData"
                                    class="form-check-input">
                            <span>Yes</span>
                            </label>
                        </div>
                        <div class="form-check">
                            <label class="form-check-label">
                            <input
                                    type="radio"
                                    value="false"
                                    v-model="userData.storeData"
                                    class="form-check-input">
                            <span>No</span>
                            </label>
                        </div>
                    </div>

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->
                    <div class="form-group">
                        <button
                                class="btn btn-primary"
                                @click.prevent="isSubmitted = true">
                            Submit
                        </button>
                    </div>

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </form>
            </div>
        </div>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-12 col-sm-8 offset-sm-2 col-md-6 offset-md-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ userData.fullname }}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ userData.storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import Fullname from "./components/Fullname.vue";

    export default {
        data() {
            return {
                userData: {
                    fullname: '',
                    email: '',
                    password: '',
                    storeData: true
                },
                isSubmitted: false
            }
        },
        components: {
            fullName: Fullname
        },
        mounted() {
            document.getElementById('firstname').focus();
        }
    }
</script>

<style>
</style>
