# axios get cat

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      img {
        height: 500px;
      }
    </style>
  </head>
  <body>
    <div id="app">
      <h1>CAT IMAGE</h1>
      <img :src="catURL" alt="cat Image" />
      <button @click="getCat">GET CAT</button>
    </div>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
    <script>
      const app = new Vue({
        el: "#app",
        data() {
          return {
            catURL: '',
          }
        },
        methods: {
          // methods 꼮 s를 붙여야한다.
          getCat() {
            const URL = "https://api.thecatapi.com/v1/images/search"
            axios.get(URL)
            .then((response) => {
              const imageURL = response.data[0].url
              // 키 값으로 url이 들어가 있기에 소문자로 사용되어야한다. 위 URL과 url과 다르다.
              console.log(imageURL)
              this.catURL = imageURL
            })
            .catch((error) => console.log(error));
          },
        },
        created() {
          this.getCat()
        },
      });
    </script>
  </body>
</html>
```