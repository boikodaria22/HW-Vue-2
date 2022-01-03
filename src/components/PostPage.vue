<template>
  <div class="post-page">
    <div class="post">
      <h1>{{ post.title }}</h1>
      <p>{{ post.body }}</p>
      <span>{{ formatedPostDate }}</span>
      <hr/>
    </div>
    <div class="comments">
      <div v-bind:id="`comment-${commentList.id}`" class="comments__item" v-for="commentList in commentsList" :key="commentList.id">
        <h3>{{ commentList.name }}</h3>
        <span>{{ commentList.email }}</span>
        <p>{{ formatedCommentText(commentList.body) }}</p>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'PostPage',
    data: () => ({
      post: {
        id: 1,
        title: 'Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit. Ullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velitullam et saepe reiciendis voluptatem adipisci\nsit … ipsam iure\nquis sunt voluptatem rerum illo velit.',
        postDate: new Date()
      },
      commentsList: [{
        "postId": 1,
        "id": 1,
        "name": "id labore ex et quam laborum",
        "email": "Eliseo@gardner.biz",
        "body": "laudantium enim quasi est quidem magnam voluptate ipsam eos\ntempora quo necessitatibus\ndolor quam autem quasi\nreiciendis et nam sapiente accusantium"
      }, {
        "postId": 1,
        "id": 2,
        "name": "quo vero reiciendis velit similique earum",
        "email": "Jayne_Kuhic@sydney.com",
        "body": "est natus enim nihil est dolore omnis voluptatem numquam\net omnis occaecati quod ullam at\nvoluptatem error expedita pariatur\nnihil sint nostrum voluptatem reiciendis et"
      }, {
        "postId": 1,
        "id": 3,
        "name": "odio adipisci rerum aut animi",
        "email": "Nikita@garfield.biz",
        "body": "quia molestiae reprehenderit quasi aspernatur\naut expedita occaecati aliquam eveniet laudantium\nomnis quibusdam delectus saepe quia accusamus maiores nam est\ncum et ducimus et vero voluptates excepturi deleniti ratione"
      }, {
        "postId": 1,
        "id": 4,
        "name": "alias odio sit",
        "email": "Lew@alysha.tv",
        "body": "non et atque\noccaecati deserunt quas accusantium unde odit nobis qui voluptatem\nquia voluptas consequuntur itaque dolor\net qui rerum deleniti ut occaecati"
      }, {
        "postId": 1,
        "id": 5,
        "name": "vero eaque aliquid doloribus et culpa",
        "email": "Hayden@althea.biz",
        "body": "harum non quasi et ratione\ntempore iure ex voluptates in ratione\nharum architecto fugit inventore cupiditate\nvoluptates magni quo et"
      }]
    }),
    methods: {
      formatedCommentText(comment) {
        let formatedComment = comment.replace(`${comment[0]}`, `${comment[0].toUpperCase()}`)
        return comment.length > 20 ? formatedComment.slice(0, 20) + '...' : formatedComment
      }
    },
    computed: {
      formatedPostDate() {
        const monthName = ['Января', 'Февраля', 'Марта',
          'Апреля', 'Мая', 'Июня', 'Июля',
          'Августа', 'Сентября', 'Октября',
          'Ноября', 'Декабря'
        ]
        return `${this.post.postDate.getDate()} ${monthName[this.post.postDate.getMonth()]}, ${this.post.postDate.getFullYear()}`
      }
    }
  }
</script>
<style scoped lang="scss">
  .post-page {
    h1 {
      font-family: 'Courier New', Courier, monospace;
    }
    span {
      font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
      font-weight: 600;
      color: rgb(110, 106, 106);
    }
  }
  
  .comments {
    line-height: 5px;
    h3 {
      font-family: 'Times New Roman', Times, serif;
      font-size: 20px;
      font-weight: 800;
      margin-top: 15px;
    }
    span {
      color: rgb(53, 113, 183);
      font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    p {
      padding-bottom: 10px;
      border-bottom: 1px solid gray;
    }
  }
</style>