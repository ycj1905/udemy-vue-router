<template>
    <div>
        <h3>Some User Details</h3>
        <p>User loaded has ID: {{ $route.params.id }}</p>
        <!-- <router-link
                tag="button"
                :to="{ name: 'userEdit', params: { id: $route.params.id }, query: { locale: 'en', q: 100 } }"
                class="btn btn-primary">Edit User</router-link> -->
        <router-link 
            tag="button" 
            :to=link
            class="btn btn-primary">Edit User
        </router-link>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                link: {
                    name: 'userEdit',
                    params: {
                        id: this.$route.params.id
                    },
                    query: {
                        loacle: 'en', q: 100
                    },
                    hash: '#data'
                }
            }
        },
        beforeRouteEnter(to, from, next) {
            // this object hasn't been fully initialized, we cannot acces here (this.link)
            if (true) {
                next();
            } else {
                next(false);
            }
            // next(vm => {
            //     vm.link;
            // });
        }
        // As long as you don't call next(), this component is not loaded, This also means that in this lifecycle hook, 
        // you can't access your Vue instance, and Data
    }

</script>