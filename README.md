# interview
## Html
#### 行内元素、块元素和行内块元素都有哪些
+ 行内元素：span,storng,label,a等
+ 块元素：div,ul,li,ol,dl,p,form,h1-h6,table等
+ 行内块元素：img,button,input等
> 区别：行内元素不可以设置宽高，不独立成行,块元素独立成行，可以设置宽高,行内块元素不独立成行，可以设置宽高。
## js
#### for循环和foreach循环(for in)的区别
    
    var array=['a']
    for(var i=1;i<array.length;i++){
      alert(array[i])
    }

> 标准的for循环

    for(var i in array){
      alert(array[i])
    }

> foreach循环

## Vue

### vue获取url并分离出参数
    urlParse(){
          let obj = {};
          let reg = /[?&][^?&]+=[^?&%]+/g;
          let url = window.location.href;
          // console.log(url)
          // let url ="http://wwww.baidu.com?treeLevel=3&gldw=1&value=628a1a5c-2ad6-491d-96b0-f83ec8f96c36&type=1";
          let arr = url.match(reg);
          arr.forEach((item) => {
              let tempArr = item.substring(1).split('=');
              let key = decodeURIComponent(tempArr[0]);
              let val = decodeURIComponent(tempArr[1]);
              obj[key] = val;
          })
          return obj;
      }

      Request = this.urlParse()
> Request是一个对象

### vue配置webpack引入jquery
##### 1.npm install jquery --save-dev 引入jquery模块保存的package.json
##### 2.找到build文件夹下的webpack.base.conf.js文件，打开，添加：var webpack=require('webpack')<br>
![avatar](https://img-blog.csdn.net/20171218184459929)
##### 3.在module.exports里输入:

    plugins: [ 
             new webpack.ProvidePlugin({ 
                   $:"jquery", 
                   jQuery:"jquery", 
                  "windows.jQuery":"jquery"
          }) 
        ],
![avatar](https://img-blog.csdn.net/20171218184525067)
##### 4.在入口文件main.js中输入：import $ from 'jquery'
![avatar](https://img-blog.csdn.net/20171218184551635)
##### 5.从新 npm run dev

### vue配置webpack引入less
##### 1.npm install less less-loader --save-dev
##### 2.安装成功后，打开 build/webpack.base.conf.js ，在 module.exports = 的对象的 module.rules 后面添加一段

      module.exports = {
        //  此处省略无数行，已有的的其他的内容
        module: {
            rules: [
              //  此处省略无数行，已有的的其他的规则
              {
                test: /\.less$/,
                loader: "style-loader!css-loader!less-loader",
              }
            ]
        }
      }

##### 3.在代码中的 style 标签中 加上 lang="less" 属性即可

      <style scoped lang="less">

      </style>