<template>
    <div>
        <div class="font-bold">
            {{ question.title }}
        </div>

        <hr class="my-3">

        <form @submit.prevent="showFollowUp = true">
            <fieldset>
                <div class="flex" :key="index" v-for="(answer, index) in question.answers">
                    <input class="mr-3" type="radio" :id="answer.title" name="question" value="answer.value">
                    <label :for="answer.title">{{ answer.value }}</label>
                </div>
            </fieldset>

<!--            <div v-if="showFollowUp" class="bg-gray-200">-->
<!--                <div class="flex" :key="index" v-for="(fu, index) in followUp">-->
<!--                    <input class="mr-3" type="radio" :id="fu.title" name="follow_up" value="answer.value">-->
<!--                    <label :for="fu.title">{{ fu.title }}</label>-->
<!--                </div>-->
<!--            </div>-->

            <hr class="my-3">

            <div class="flex justify-end">
                <button class="bg-red-600 px-3 py-1 text-white hover:bg-red-800" type="submit">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Question',
    props: {
        question: Object,
        followUp: Object
    },
    data() {
        return {
            showFollowUp: false
        }
    },
    methods: {
        validate() {
            this.showFollowUp = true;
        }
    }
}
</script>