<template>
    <div>
        <h3>Some User Details</h3>
        <p>User id: {{ $route.params.id }}</p>
        <router-link
                tag="button" class="btn btn-primary"
                :to="link">
            Edit
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
                        locale: 'it',
                        q: 100
                    },
                    hash: '#data'
                }
            }
        },
        beforeRouteEnter(to, from, next) {
            console.log('BeforeRouteEnter');
            // the only way to enter this is with a callback because the vue component is not available yet
            next(vm =>{
                vm.link;
            })
        }
    }
</script>
