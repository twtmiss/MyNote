### 1. 数据库编码格式问题

### 2. 大小写敏感问题

### 3. ONLY_FULL_GROUP_BY

### 4. varchar排序

device_name字段为varhcar类型，使用以下排序。有中文也可以用

`order by dayData.device_name+0`