<template>
    <div class="table-wrapper">
    <table class="table">
        <thead>
            <th>Id</th>
            <th>Name</th>
            <th>Location</th>
            <th>Currency</th>
        </thead>
        <tbody>
            <tr v-for="(item, index) in data" :key="index">
                <th> {{item.id }} </th>
                <th> {{ item.name }} </th>
                <th> {{ item.location }} </th>
                <th> {{ item.currency }} </th>
            </tr>
        </tbody>
    </table>
    </div>
</template>

<script>
export default {
  props : ['data', 'search'],
}
</script>

<style>

    .table-wrapper {
        max-height: 400px;
        min-height: 400px;
        max-width: 800px;
        margin: 0 auto;
        overflow: scroll;
    }
</style>


