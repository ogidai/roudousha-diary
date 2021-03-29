<template>
  <div>
    <b-card-group>
        <b-card>
            <b-form-group
                id="fieldset-1"
                description="今日は何をしましたか？"
                label="労働の内容"
                label-for="input-1"
                >
                <b-form-input
                    id="input-1"
                    v-model="work"
                    placeholder="雑用"
                    required
                    trim
                >
                </b-form-input>
            </b-form-group>
            <b-form-group
                id="fieldset-2"
                description="今日は何か学べましたか？"
                label="学んだこと"
                label-for="input-2"
                >
                <b-form-input
                    id="input-2"
                    v-model="learned"
                    placeholder="人生は甘くない"
                    required
                    trim
                ></b-form-input>
            </b-form-group>
            <b-form-group
                id="fieldset-3"
                description="今日の感想を書いてみましょう"
                label="感想"
                label-for="textarea"
                >
            <b-form-textarea
                id="textarea"
                v-model="impression"
                placeholder="今日は雑用しかしてないけど楽しかった。また明日頑張る。"
                rows="8"
                trim
                required
            ></b-form-textarea>
            </b-form-group>
            <div class="form-button">
                <b-button @click="savePost" block variant="primary">保存</b-button>
            </div>
        </b-card>
    </b-card-group>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'Post',
    data() {
        return {
            work: '',
            learned: '',
            impression: '',
        }
    },
    methods: {
        savePost() {
            console.log(this.work)
            axios
            .post('https://firestore.googleapis.com/v1/projects/roudousha-diary/databases/(default)/documents/posts',
                {
                    fields: {
                        work: {
                            stringValue: this.work
                        },
                        learned: {
                            stringValue: this.learned
                        },
                        impression: {
                            stringValue: this.impression
                        }
                    }
                }
            )
            .then(response => {
                console.log(response)
            })
            .catch(error => {
                console.log(error)
            })
            console.log('hello')
            this.work = ''
            this.learned = ''
            this.impression = ''
        }
    }
}
</script>

<style>
.form-button {
    margin-top: 30px;
}
</style>