# prac 1

```html
<html>
  <head>
  <meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
  <meta http-equiv="Pragma" content="no-cache" />
  <meta http-equiv="Expires" content="-1" />
  <meta charset="utf8">
  <title>Hello, world</title>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.7.8/dist/vue.js"></script>
</head>
<body>
  <div id="app">
      {{ message }}
  </div>
  

<script type="text/javascript">
   var app = new Vue({
        el: '#app',
        data : {
            message: 'Hello Vue.js',
        },
   });
</script>

</body>
```