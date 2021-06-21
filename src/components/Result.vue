<template>
   <div class="result">
        <div class="title">{{ results[resultIndex].title }}</div>
        <div class="desc">{{ results[resultIndex].desc }}</div>
    </div>
</template>

<script>
export default {
    props: ["results", "totalCorrect"],
    computed: {
        resultIndex() {
            let index = 0;

            this.results.forEach((e, i) => { //loop through the results where e is the current item in the iteration of the array and i is the index
                if (e.min <= this.totalCorrect && e.max >= this.totalCorrect) {  //compare totalCorrect property making sure its above min but below max
                    index = i;
                }
            })

            return index;
        }
    }
}
</script>
