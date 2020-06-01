<template>
  <div class="framwork">
    <form>
      <h2>以下にお答え下さい</h2>
      <div>
        <p>現在、生命保険に加入されていますか？</p>
        <label
          ><input
            type="radio"
            value="yes"
            v-model="pickedFirst"
            v-on:change="questionSecond = true"
          />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedFirst"
            v-on:change="questionSecond = true"
          />いいえ</label
        >
      </div>
      <div v-if="showQuestion2">
        <p>
          現在入院中ですか。または、最近３ヶ月以内に医師の診察・検査の結果、入院・手術をすすめられたことはありますか？
        </p>
        <label
          ><input
            type="radio"
            value="yes"
            v-model="pickedSecond"
            v-on:change="questionThird = true"
          />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedSecond"
            v-on:change="questionThird = true"
          />いいえ</label
        >
      </div>
      <div v-if="showQuestion3">
        <p>
          過去５年以内に、病気やけがで、手術をうけたことまたは継続して７日以上の入院をしたことがありますか？
        </p>
        <label
          ><input type="radio" value="yes" v-model="pickedThird" />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedThird"
          />いいえ</label
        >
      </div>
    </form>

    <router-link to="Basic">
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
  props: {
    value: {}
  },
  data() {
    return {
      questionSecond: false,
      questionThird: false,
      showResult: false,
      pickedFirst: "",
      pickedSecond: "",
      pickedThird: ""
    };
  }
};
</script>

<style></style>
