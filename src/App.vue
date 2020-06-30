<template>
    <div id="app">
        <Modal>
            <div class="flex">
                <div class="w-1/5 bg-gray-200 flex justify-center items-start">
                    <img class="rounded-full w-24 p-4" src="https://www.fillmurray.com/200/200" title="avatar">
                </div>
                <div class="flex-grow p-4">
                    <question :question="{
                                title: 'Do you think Sun is really an unlimited source of energy just burning there for someone to use it\'s unlimited power?',
                                    answers: [
                                        {
                                            value: 0,
                                            title: 'no',
                                        },
                                        {
                                            value: 1,
                                            title: 'yes',
                                        }
                                    ]
                                }"
                        :followUp="{
                                    title: 'Really?',
                                    answers: [
                                        {
                                            value: 2,
                                            title: 'no',
                                        },
                                        {
                                            value: 3,
                                            title: 'yes',
                                        }
                                    ],
                                   }"
                    />
                </div>
            </div>
        </Modal>
    </div>
</template>

<script>
import Modal from './components/Modal.vue'
import Question from './components/Question.vue'

export default {
    name: 'App',
    components: {
        Modal,
        Question,
    }
}
</script>