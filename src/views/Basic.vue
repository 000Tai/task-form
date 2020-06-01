<template>
  <div>
    <form>
      <h2>お客様の情報を入力してください</h2>
      <p>-性別-</p>
      <label><input type="radio" value="male" v-model="picked" />男性</label>
      <label><input type="radio" value="female" v-model="picked" />女性</label>
      <p>-生年月日-</p>
      <select v-model="year" @change="get_days">
        <option v-for="n in 50" v-bind:key="n.id">
          {{ n + 1959 }}
        </option> </select
      >年
      <select v-model="month" @change="get_days">
        <option v-for="n in 12" v-bind:key="n.id">
          {{ n }}
        </option> </select
      >月
      <select v-model="day" @change="get_days">
        <option v-for="n in days_max" v-bind:key="n.id">
          {{ n }}
        </option> </select
      >日
    </form>
    <router-link to="Questionnaire">
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
      picked: "",
      year: 1990,
      month: 1,
      day: 1,
      days_max: "",
      showResult: false
    };
  },
  computed: {
    // eslint-disable-next-line vue/return-in-computed-property
    get_days: function() {
      // eslint-disable-next-line vue/no-side-effects-in-computed-properties
      this.days_max = new Date(this.year, this.month, 0).getDate();
      console.log(this.days_max);
    }
  }
};
</script>

<style>
.framwork {
  border: 1px solid;
  border-color: aquamarine;
}

input.signUp {
  display: block;
  margin: auto;
  margin-bottom: 10px;
  width: 300px;
  height: 30px;
  padding: 5px;
  font-size: 12px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
