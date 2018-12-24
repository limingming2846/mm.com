 
    <template id="shopCart">
    	 <div style="border:1px solid black;">
        <keep-alive> 
          <component :is="currentView"></component>  
        </keep-alive>
        <button @click="changeView()">点击切换视图</button>
        <div>
           keep-alive  标签包裹两个切换的视图，这样视图在切换的时候不会重新渲染节约内存
        </div>
       </div>
    </template>
 
  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.12/vue.js"></script>
  <script>
      import small1 from "./small1"
      import small2 from "./small2"
      export default {
        name:"big",
        data(){
          return{
            currentView:small1,
            flag:true
          }
        },
        components:{
          small1,
          small2
        },
        methods:{
          changeView(){
            if(this.flag){
              this.currentView="small2";
              this.flag=false
            }else{
              this.currentView="small1";
             this.flag=true
            }
          }
        }
      }
  </script>
 
