<template>
  <div class="framwork">
    <form class="">
      <h2>ご相談内容をご記入下さい</h2>
      <p>-ご相談内容-</p>
      <textarea
        name=""
        id=""
        cols="100"
        rows="20"
        v-model="myContent"
      ></textarea>
    </form>
    <router-link to="Questionnaire">
      <button>
        前へ戻る
      </button>
    </router-link>
    <router-link to="Consultation">
      <button>
        次へ進む
      </button>
    </router-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myContent: ""
    };
  }
};
</script>

<style></style>
