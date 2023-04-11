<template>
    <div>
        {{ id }}
    </div>
</template>
<script>

export default {

    name: 'LoginComponent',
    props: {
        id: {
            type: String,
            default: () => ""
        }
        // ,
        // password: {
        //     type: String,
        //     default: () => ""
        // }

    }
  }
</script>
<style scoped>

</style>
