<template>
  <div id="task2" class="task1">
    <form class="">
      <h2>以下にお答え下さい</h2>
      <div>
        <p>現在、生命保険に加入されていますか？</p>
        <label
          ><input
            type="radio"
            value="yes"
            v-model="pickedResult1"
            v-on:change="showQuestion2 = true"
          />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedResult1"
            v-on:change="showQuestion2 = true"
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
            v-model="pickedResult2"
            v-on:change="showQuestion3 = true"
          />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedResult2"
            v-on:change="showQuestion3 = true"
          />いいえ</label
        >
      </div>
      <div v-if="showQuestion3">
        <p>
          過去５年以内に、病気やけがで、手術をうけたことまたは継続して７日以上の入院をしたことがありますか？
        </p>
        <label
          ><input type="radio" value="yes" v-model="pickedResult3" />はい</label
        >
        <label
          ><input
            type="radio"
            value="no"
            v-model="pickedResult3"
          />いいえ</label
        >
      </div>
    </form>

    <router-link to="Basic">
      <button class="task2Botton">
        前へ戻る
      </button>
    </router-link>
    <router-link to="Consultation">
      <button class="task2Botton">
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
      showQuestion2: false,
      showQuestion3: false,
      showResult: false,
      pickedResult1: "",
      pickedResult2: "",
      pickedResult3: ""
    };
  }
};
</script>

<style></style>
