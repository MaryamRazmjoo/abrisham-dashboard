<template>
  <div class="comment-box">
    <v-textarea
      v-model="note"
      class="rounded-xl  comment-main"
      background-color="#eff3ff"
      placeholder="یادداشت این جلسه"
      filled
      auto-grow
      solo
      flat
      @input="inputEvent"
      @blur="blur"
    />
  </div>
</template>

<script>
export default {
  name: 'CommentBox',
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      note: null
    }
  },
  watch: {
    value (newValue) {
      this.note = newValue
    }
  },
  methods: {
    blur () {
      this.$emit('blur', this.note)
    },
    inputEvent () {
      this.$emit('input', this.note)
    }
  }
}
</script>

<style>
.comment-box .v-text-field.v-text-field--enclosed{
  margin-right: 0 !important;
}


.comment-box .comment-main textarea::-webkit-input-placeholder {
  color: #3e5480 !important;
  margin-top: 16px;
  margin-right: 12px;
  font-size: 16px;

}

.comment-box .comment-main textarea:-moz-placeholder { /* Firefox 18- */
  color: #3e5480 !important;
  margin-top: 16px;
  margin-right: 29px;
  font-size: 16px;
}

.comment-box .comment-main textarea::-moz-placeholder {  /* Firefox 19+ */
  color: #3e5480 !important;
  margin-top: 16px;
  margin-right: 29px;
  font-size: 16px;
}

.comment-box .comment-main textarea:-ms-input-placeholder {
  color: #3e5480 !important;
  margin-top: 16px;
  margin-right: 29px;
  font-size: 16px;
}

.comment-box .comment-main textarea::placeholder {
  color: #3e5480 !important;
  margin-top: 16px;
  margin-right: 29px;
  font-size: 16px;
}
</style>
