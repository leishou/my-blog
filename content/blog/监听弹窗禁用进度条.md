# 监听弹窗禁用进度条

```javascript
export default {  
  data() {  
    return {  
      value: '',  
    };  
  },  
  watch: {  
    value(state) {  
   		if(state){
        	docoment.body.classList.add('popup-hidden');
      }else{
          if(!this.$isServer){
              document && docoment.body.classList.remove('popup-hidden');
          }
      }
    },  
  },  
};
//禁止滚动
.popup-hidden{
    overflow:hidden;
}
```

