<template>
  <h1 class="text-3xl font-bold underline">Vue メモ</h1>
  <div
    class="mt-10 p-5 mx-auto max-w-3xl rounded-sm flex-row items-stretch bg-blue-300"
  >
    <div class="mt-2 flex justify-center">
      <input
        class="p-3 rounded-md border-white w-1/2"
        type="text"
        placeholder="メモの内容をここに記入"
        v-model="inputmemo"
      />
      <button
        class="ml-3 mr-2 p-2 text-white border-2 rounded-full bg-emerald-300 transition hover:bg-emerald-200 duration-300"
        v-on:click="addmemo"
      >
        追加する
      </button>
      <button
        class="p-2 text-white border-2 rounded-full bg-red-400 transition hover:bg-red-300 duration-300"
        v-on:click="alldelete"
      >
        全て消す
      </button>
    </div>
    <ul class="flex flex-col justify-center m-3">
      <li
        class="flex justify-between items-center p-1 bg-white rounded-md border-2"
        v-for="(memo, index) in memos"
        :key="index"
      >
        <div class="px-3">
          <input type="checkbox" v-model="memo.checkon" />
        </div>
        <div v-if="memo.checkon" class="line-through">
          {{ memo.text }}:{{ memo.date[0] }}/{{ memo.date[1] }}/{{
            memo.date[2]
          }}
        </div>
        <div v-else class="">
          {{ memo.text }}:{{ memo.date[0] }}/{{ memo.date[1] }}/{{
            memo.date[2]
          }}
        </div>
        <button
          class="p-2 border-2 border-black rounded-full hover:bg-red-400"
          v-on:click="deletememo(index)"
        >
          削除
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputmemo: "",
      memos: [],
    }
  },
  methods: {
    addmemo: function () {
      const nowdate = new Date()
      if (this.inputmemo !== "") {
        this.memos.push({
          text: this.inputmemo,
          checkon: "",
          date: [
            nowdate.getFullYear(),
            Number(nowdate.getMonth() + 1),
            nowdate.getDate(),
          ],
        })
        this.inputmemo = ""
      }
      console.log(this.memos)
    },
    deletememo: function (i) {
      this.memos.splice(i, 1)
      console.log(this.memos)
    },
    alldelete: function () {
      const kakunin = confirm("ほんとに消しますか？")
      if (kakunin) {
        this.memos.length = 0
      }
    },
  },
}
</script>

<style scoped>
.memo-list {
  padding-left: 5rem;
  padding-right: 5rem;
  display: flex;
  flex-direction: column;
  align-items: stretch;
  max-width: 512px;
  margin-left: auto;
  margin-right: auto;
}

.memo-list__container {
  padding: 0;
}

.memo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem;
  border-radius: 5px;
}

.memo:hover {
  color: white;
  background-color: #b23b61;
}

.memo__text {
  margin-left: 2rem;
  text-align: left;
}

.memo__text--done {
  text-decoration-line: line-through;
}

.memo__delete {
  margin-left: 1rem;
  padding: 0.5rem 0.5rem;
  border: solid 1px black;
  border-radius: 5px;
  background-color: white;
}

.memo__delete:hover {
  background-color: #b2ae3b;
  border-radius: 5px;
}

.add-memo-field {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.add-memo-field__button {
  padding: 0.5rem 0.5rem;
  border: solid 1px black;
  border-radius: 5px;
  background-color: white;
}

.add-memo-field__button:hover {
  background-color: #b2ae3b;
  border-radius: 5px;
}
</style>
