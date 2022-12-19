<template>
    <div>
        <ul>
            <li 
            v-for="(history, i) in history" 
            :key="i"
            :class="{currentSentence: i === currentSentence}">
                <p>{{ history.text }}</p> 
            </li>
        </ul>
    </div>

</template>

<script>
    export default {
        name: "EscenaComponent",
        props: {
            history: Array,
            currentSentence: Number
        }
    }
</script>

<style scoped lang="css">
    ul {
        list-style: none;
        padding-inline-start: 0px;
    }
    li {
        padding:5px;
        margin-bottom: 15px;
        border-radius: 30px;
        border:solid 1px;
        border-color:black;
    }
    .currentSentence {
        background-color: #FFC0CB;
    }
    p {
        text-align: center;
    }
</style>