<template>
  <div class="select-console">
    <pre>
PUT KEY 'UP' OR 'DOWN' TO SELECT

    <span class="wait">{{ prev }}</span>

> [ <span class="use-blind">{{ featureItems[select] }}</span> ]

    <span class="wait">{{ next }}</span>

PUT KEY 'ENTER' TO CONFIRM
    </pre>
    <!-- <button @click="prevOne">UP</button>
    <button @click="nextOne">DOWN</button> -->
  </div>
</template>

<script>
/* eslint-disable */

export default {
  name: 'Console',
  data() {
    return {
      featureItems: ['SHARE', 'LOGIN', 'CONTACT'],
      select: 0,
      prev: '',
      next: '',
    };
  },
  methods: {
    prevOne() {
      let min_index = 0;

      if (this.select !== min_index) {
        this.select -= 1;

        // prev
        if (this.select - 1 < min_index) {
          this.prev = ' ';
        } else {
          this.prev = this.featureItems[this.select - 1];
        }

        // next
        this.next = this.featureItems[this.select + 1];
      }
    },
    nextOne() {
      let max_index = this.featureItems.length - 1;

      if (this.select < max_index) {
        this.select += 1;

        // prev
        this.prev = this.featureItems[this.select - 1];

        // next
        if (this.select + 1 > max_index) {
          this.next = ' ';
        } else {
          this.next = this.featureItems[this.select + 1];
        }
      }
    },
  },
  mounted() {
    this.next = this.featureItems[1];
  },
};
</script>

<style scoped>
.select-console {
  padding: 20px 0px 0px 20px;
}

.use-blind {
  -webkit-animation: blind 900ms;
  animation: blind 900ms;
  animation-iteration-count: infinite;
  -webkit-animation-iteration-count: infinite;
}
</style>
