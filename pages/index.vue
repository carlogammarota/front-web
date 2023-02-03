<template>
  <div>
    <!-- {{  blogs  }} -->
    

    <div class="">
    <!-- ... --><Card class="my-4" :item="item" v-for="item in blogs" :key="item.id"></Card>
  </div>

  </div>
</template>

<script>
const feathers = require("@/plugins/feathers.js");
export default {
  name: 'IndexPage',
  data() {
    return {
      blogs: []
    }
  },
  mounted() {
    this.getBlogs();
  },
  methods: {
    getBlogs(){
            // this.loader = true
            feathers.default.blog.find({
                query: {
                    $limit: 100
                }
            }).then(data => {
                // console.log("data", data.data);
                this.blogs = data.data
                console.log(this.blogs)
                this.blogCantidad = this.blogs.length;
                // this.loader = false
            }).catch(error => {
                // this.loader = false
                console.log("error", error)
            });
        },
  },
}
</script>
