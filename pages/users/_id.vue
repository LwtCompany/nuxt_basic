<template>
  <section>
    <h2>User {{user.name}}</h2>
    <span>Email: {{user.email}}</span>
  </section>
</template>


<script>
export default {
  validate({params}){
    return /^\d+$/.test(params.id);
  },
   async asyncData  ({$axios, params}) {
    const user = await $axios.$get('https://jsonplaceholder.typicode.com/users/' + params.id);
    return {user};
  },
}
</script>


