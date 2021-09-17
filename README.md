# layui-tinymce

[在线预览地址](http://chick1993.gitee.io/layui-tinymce/layui_exts/) | [Layui论坛讨论](https://fly.layui.com/jie/63668/) | [tinymce中文文档](http://tinymce.ax-z.cn/)

## 食用

食用方式可参考tinymce官方文档，

```
<textarea id="edit"></textarea>

<script>
    // 引入插件
    layui.extend({
        tinymce: '{/}./tinymce/tinymce'
    }).use(['tinymce'], function () {
        var t = layui.tinymce
        // 创建编辑器 t.render(option，load_callback)
        t.render({
            elem: "#edit"  
            // 支持tinymce所有配置      
        },(opt)=>{
            //加载完成后回调 opt 是传入的所有参数
        });
        
        // 获取编辑器实例 t.get(id)
        // 如果页面只有一个编辑器，相当于官方的tinymce.activeEditor
        // 如果页面有多个编辑器，等同于官方tinymce.editors[id]
        var edit = t.get('#edit')
            
        // 获取编辑器内容 edit.getContent(option)
        edit.getContent()
        
        // 获取编辑器文本内容 edit.getContent(option)
        edit.getContent({format:'text'})
            
        // 插入内容到编辑器 edit.insertContent(html)
        edit.insertContent('<b>插入内容</b>')
        
        // 设置编辑器内容edit.setContent(html)
        edit.setContent('<b>设置内容</b>')
               
        // 清空编辑器 edit.setContent(html)
        edit.setContent('')    
                
        // 重载编辑器
        t.reload({
            elem:'#edit'
            // 所有参数都可以重新设置 ...
        },(opt) => {
            //重载完成后回调函数，会把所有参数回传，
            //重载仅仅重新渲染编辑器，不会清空textarea，可手动设置
            edit.setContent('')
        })
        
                
    })
</script>
```





