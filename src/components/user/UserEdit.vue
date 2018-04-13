<template>
    <div>
        <h3>Edit the User</h3>
        <p>Locale: {{ $route.query.locale }}</p>
        <p>Analytics: {{ $route.query.q }}</p>
        <hr>
        <button class="btn btn-primary" @click="confirmed = !confirmed">Confirm</button>
        <div style="height: 700px"></div>
        <p id="data"> SOme extra Data</p>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                confirmed: false
            }
        },
        beforeRouteLeave: (to, from, next) => {
            console.log('Confirmed ? ', this.confirmed);
            if (this.confirmed) {
                next();
            } else {
                if (confirm('Are you sure?')){
                    next();
                } else {
                    next(false);
                }
            }
        }
    }
</script>