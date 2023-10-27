<template>
  <div class="app">   
    <StartBlock />
  </div>
</template>

<script>  
import axios from 'axios'
import StartBlock from './components/StartBlock.vue'

  export default {
    data() {
      return {
        posts: [],
        dialogVisible: false,
        isPostsLoading: false,
        selectedSort: '',
        sortOptions: [
        {value: 'title', name: 'По названию'},
        {value: 'body', name: 'По содержимому'},
      ]
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post)
        this.dialogVisible = false
        return this.title = '', this.description = ''
      },
      removePost(post){
        return this.posts = this.posts.filter(el => el.id !== post.id)
      },
      showDialog(){
        this.dialogVisible = true
      },
      async fetchPosts() {
        try {
          this.isPostsLoading = true
          setTimeout( async () => {
            const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
          this.posts = response.data
          this.isPostsLoading = false
          }, 1000)
        }
        catch (e) {
          console.log('Ошибка')
        }
      }
    },
    mounted() {
      this.fetchPosts()
    },
    components: {
      StartBlock
    }
  }
</script>

<style lang="sass">
*
  margin: 0
  padding: 0
  box-sizing: border-box
  overflow: hidden
@font-face 
  font-family: 'SF Pro Display'
  src: url(@/assets/fonts/SFProText-Regular.ttf)
  font-weight: 400
@font-face 
  font-family: 'SF Pro Display'
  src: url(@/assets/fonts/SFProText-Medium.ttf)
  font-weight: 500
@font-face 
  font-family: 'SF Pro Display'
  src: url(@/assets/fonts/SFProText-Semibold.ttf)
  font-weight: 600
h1
  font-family: SF Pro Display
  font-size: 48px
  font-weight: 600
  line-height: 58px
  letter-spacing: -2px
  text-align: left
  color: rgba(8, 18, 58, 1)
  @media( max-width: 1350px) 
    font-size: 32px
    line-height: 40px
  @media( max-width: 870px) 
    font-size: 20px
    line-height: 28px
h2
  font-family: SF Pro Display
  text-align: center
h4
  font-family: SF Pro Display
  font-size: 20px
  font-weight: 400
  line-height: 28px
  color: rgba(95, 107, 119, 1)
  @media( max-width: 1350px) 
    font-size: 16px
    line-height: 24px
  @media( max-width: 870px) 
    font-size: 12px
    line-height: 16px
.header5
  font-family: SF Pro Text
  font-size: 16px
  font-weight: 500
  line-height: 20px
  letter-spacing: 0px
  text-align: left
  color: rgba(95, 107, 119, 1)
  @media( max-width: 1350px) 
    font-size: 16px
    line-height: 20px
  @media( max-width: 870px) 
    font-size: 12px
    line-height: 16px
  @media( max-width: 50px) 
    font-size: 8px
    line-height: 12px
.btn
  font-size: 16px
  font-weight: 500
  line-height: 22px
  letter-spacing: 0px
  color: rgba(255, 255, 255, 1)
  font-family: SF Pro Display
  @media( max-width: 1350px) 
    font-size: 12px
    line-height: 18px
  @media( max-width: 870px) 
    font-size: 8px
    line-height: 12px
  @media( max-width: 500px) 
    font-size: 6px
    line-height: 8px
</style>
