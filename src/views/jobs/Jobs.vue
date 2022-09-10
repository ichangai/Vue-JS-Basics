<template>
<div class="">
    <h1>Jobs</h1>
    <div class="job" v-for="job in jobs" :key="job.id">
        <router-link :to="{name: 'JobDetails', params: {id: job.id}}">
            <h2>{{ job.title }}</h2>
        </router-link>
    </div>
</div>
</template>

<script>
    export default{
        data(){
            return{
                jobs: [
                    {title: 'UX/UI Designer', id: 1, details: 'Designing user experience and user interface'},
                    {title: 'Cloud Engineer', id: 2, details: 'Develops the cloud architecture and app scalability'},
                    {title: 'Backend Software', id: 3, details: 'Designs and develops the software architecture and database'},
                ]
            }
        }
    }
</script>

<style>
    .job h2{
        background: #f4f4f4;
        padding: 20px;
        border-radius: 10px;
        margin: 10px auto;
        max-width: 600px;
        cursor: pointer;
        color: #444;
    }
    .job h2:hover{
        background: #ddd;
    }
    .job a{
        text-decoration: none;
    }
</style>