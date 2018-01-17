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