<template>
<div>
  <article class="vueFaqList101">
    <ul v-for="(i, index) in faqList">
      <li>
        <h2 class="vueFaqList101_title"
        v-on:click="toggleContent(index)">
        {{ i.title }}
        <span v-if="!i.toggled" class="vueFaqList101_icon">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z"/>
          </svg>
        </span>
        <span v-else class="vueFaqList101_icon">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
            <path d="M19 13H5v-2h14v2z"/>
          </svg>
        </span>
        </h2>
        <section>
          <p class="vueFaqList101_ans" v-if="i.toggled">
            {{ i.content }}
          </p>
        </section>
      </li>
    </ul>
  </article>
</div>
</template>
<script>
export default {
  data () {
    return {
      faqList: [
        {
          title: "vueFaqList101_title1",
          content: "Lorem ipsum dolor sit amet1,...",
          toggled: false
        },
        {
          title: "vueFaqList101_title2",
          content: "Lorem ipsum dolor sit amet2,...",
          toggled: false
        }
      ]
    }
  },
  mounted: function() {
    this.toggleAllContent(false);
  },
  methods: {
      toggleContent: function(index) {
        let faqList = this.faqList;
        faqList[index].toggled = !faqList[index].toggled;
      },
      toggleAllContent: function(visible) {
        let faqList = this.faqList;
        for (let i in faqList) {
          faqList[i].toggled = visible;
        }
      }
    }
}
</script>