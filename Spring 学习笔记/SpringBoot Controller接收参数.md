#### 同时接收json和文件

```
/**  
 * 修改电站  
 */  
//    @PreAuthorize("@ss.hasPermi('sarnath:station:edit')")  
@Log(title = "电站", businessType = BusinessType.UPDATE)  
@PostMapping("/updateStation")  
public AjaxResult updateStation(@RequestPart("uploadFileList") List<MultipartFile> uploadFileList, @RequestPart("station") Station station)  
{  
    return Ajaxresult.su;  
}
```