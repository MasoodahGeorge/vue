<template lang="">
    <!-- <div>
        {{firstName}}{{lastName}}{{objectData}}
    </div> -->
    <h1>This is the component</h1>
    <slot></slot>

    </template>
    <script>
    export default {
        // props:['firstName', 'lastName', 'objectData']
        props:{
            firstNme: String,
            lastName: String,
            objectData: Object,
        }
    }
    </script>
    <style scope>
    
    </style>