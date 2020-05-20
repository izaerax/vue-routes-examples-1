<template>
    <div>
        <h3>Some User Details</h3>
        <p>User id: {{ $route.params.id }}</p>
        <router-link
                tag="button" class="btn btn-primary"
                :to="{ name: 'userEdit', params: {id: $route.params.id}, query: { locale: 'it', q: 100} }"
        >Edit</router-link>
    </div>
</template>
