<template>
  <div>
      <b-card-group>
        <b-card>
            <b-form-group
                id="fieldset-1"
                description="あなたの労働者番号です ＊変更不可"
                label="労働者番号"
                label-for="input-1"
            >
                <b-form-input
                    id="input-1"
                    v-model="userId"
                    placeholder=""
                    required
                    disabled
                    trim
                >
                {{ userId }}
                </b-form-input>
            </b-form-group>
            <b-form-group
                id="fieldset-2"
                description="あなたの氏名です"
                label="氏名"
                label-for="input-2"
            >
                <b-form-input
                    id="input-2"
                    v-model="userName"
                    required
                    :disabled="editForm"
                    trim
            >
                {{ userName }}
                </b-form-input>
            </b-form-group>
            <b-form-group
                id="fieldset-3"
                description="あなたのメールアドレスです"
                label="メールアドレス"
                label-for="input-3"
            >
                <b-form-input
                    id="input-3"
                    type="email"
                    v-model="userEmail"
                    required
                    :disabled="editForm"
                    trim
            >
                {{ userEmail }}
                </b-form-input>
            </b-form-group>
            <div class="form-button">
                <b-button v-if="showButton" @click="editable" block variant="success">編集</b-button>
                <b-button v-else @click="store" block variant="primary">保存</b-button>
                <b-button @click="showModal" block variant="danger">退会</b-button>
            </div>
            <b-modal ref="my-modal" hide-header hide-footer centered>
                <div class="d-block text-center">
                    <p>本当に退会しますか？
                    <br>＊データの復元はできません</p>
                <b-button variant="primary" class="mt-3" block @click="hideModal">戻る</b-button>
                <b-button variant="danger" class="mt-2" block @click="deleteAccount">退会する</b-button>
                </div>
            </b-modal>
        </b-card>
    </b-card-group>
  </div>
</template>

<script>
export default {
    name: 'User',
    data() {
        return {
            userId: 1,
            userName: '荻久保大輝',
            userEmail: 'sample@gmail.com',
            editForm: true,
            showButton: true
        }
    },
    methods: {
        editable() {
            this.editForm = false
            this.showButton = false
        },
        store() {
            this.editForm = true
            this.showButton = true
        },
        showModal() {
        this.$refs['my-modal'].show()
        },
        hideModal() {
            this.$refs['my-modal'].hide()
        },
        deleteAccount() {
            console.log('delete')
        }
    }
}
</script>

<style>
.form-button {
    margin-top: 30px;
}
</style>