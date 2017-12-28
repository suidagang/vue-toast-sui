# vue-toast

## Usage
Install:

```
npm install vue-sui-toast-demo -S
```
Import:

```javascript
import 'vue-sui-toast-demo/lib/toast.css';
import Toast from 'vue-sui-toast-demo';
Vue.use(Toast);
```
or
```javascript
import 'vue-sui-toast-demo/lib/toast.css';
import Toast from 'vue-sui-toast-demo';
Vue.use(Toast, {
    defaultType: 'center',
    duration: 3000,
    wordWrap: true,
    width: '150px'
});
```

Use in component:

```javascript
<template>
    <div id="app">
        <button @click="openTop()">top</button>
        <button @click="openCenter()">center</button>
        <button @click="openBottom()">bottom</button>
		<button @click="openLoading()">loading</button>
    </div>
</template>
export default {
    methods:{
        openTop(){
            this.$toast.top('top');
        },
        openCenter(){
            this.$toast.center('center');
        },
        openBottom(){
            this.$toast('bottom');  // or this.$toast.bottom('bottom'); 
        },
        openLoading(){
            this.$loading('loading...');
			let self = this;
	        setTimeout(function () {
	          self.closeLoading()
	        }, 2000)
        },
        closeLoading(){
            this.$loading.close();
        }
    }
}
```

## options

    Vue.use(Toast, [options])

- defaultType : position of Toast. | String | default: 'bottom' | possible 'top, center,bottom'
- duration : Number | default 2500ms
- wordWrap : word wrap. | Boolean | default: false
- width : width of Toast. | String | default: 'auto'
