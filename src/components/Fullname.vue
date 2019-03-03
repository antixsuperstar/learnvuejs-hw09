<template>
    <div class="form-group">
        <div class="form-group">
            <label for="firstname">First name</label>
            <input
                    type="text"
                    id="firstname"
                    class="form-control"
                    v-model="firstname"
                    @input="updateValue" />
        </div>
        <div class="form-group">
            <label for="lastname">Last name</label>
            <input
                    type="text"
                    id="lastname"
                    class="form-control"
                    v-model="lastname"
                    @input="updateValue" />
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
        props: ['value'],
        methods: {
            updateValue() {
                this.$emit('input', this.firstname + ' ' + this.lastname);
            }
        }
    }
</script>