#### 同时接收json和文件

后端controller
```
@PostMapping("/updateStation")  
public AjaxResult updateStation(@RequestPart("uploadFileList") List<MultipartFile> uploadFileList, @RequestPart("station") Station station)  
{  
    return AjaxResult.success();  
}
```

前端发送请求使用`form-data`格式发送，json字段`content type`需标注为`application/json`

![[Pasted image 20220315143135.png]]