<template>
    <div class="form-group">
        <div class="form-group">
            <label for="firstname">First name</label>
            <input
                    type="text"
                    id="firstname"
                    class="form-control"
                    v-model="firstname" />
        </div>
        <div class="form-group">
            <label for="lastname">Last name</label>
            <input
                    type="text"
                    id="lastname"
                    class="form-control"
                    v-model="lastname" />
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                firstname: '',
                lastname: ''
            }
        },
        watch: {
            firstname() {
                this.$emit('input', this.value);
            },
            lastname() {
                this.$emit('input', this.value);
            }
        },
        computed: {
            value() {
                return this.firstname + ' ' + this.lastname;
            }
        }
    }
</script>