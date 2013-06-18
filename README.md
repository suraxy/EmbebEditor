EmbebEditor
===========

针对已存在的系统嵌入可视化编辑


思路


1.为每一个引入一个全局的EmbebEditor.autoInit();方法
  
  在控制台调用该方法

  当前页面被修改为实时编辑状态

  embebeditor-backend为当前url建立索引


2.在编辑操作中

  embebeditor通过前后台的配合，最终建立如下索引结构 

  索引的数据结构
    
  {
  
   url:{
   
      edit_points:[
      
      	{
        
      	  type:"text",
          
      	  query_str:"#abcd",
          
      	  text:"欢迎欢迎 热烈欢迎"
          
      	},
        
      	{
        
      	  type:"img",
          
          query_str:"#abcd",
          
      	  img:"欢迎欢迎 热烈欢迎"
          
      	},
        
      	{
        
      	  type:"html",
          
      	  query_str:"#abcd",
          
      	  html:"...."
          
      	}


      ]
      
   }
   
  }
  


  3.当编辑完成之后执行
  
    EmbebEditor.commit();
    
    提交队列里的缓存
    
    控制台出现success!返回代表编辑完成
    
    

  4.在用户模式下页面中引入的脚本会到embebeditor-backend的中查询
  
    如果有编辑操作，根据 edit_points对页面做相应修改
    
