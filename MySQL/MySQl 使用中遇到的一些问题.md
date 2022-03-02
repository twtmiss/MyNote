### 1. 数据库编码格式问题

### 2. 大小写敏感问题

### 3. ONLY_FULL_GROUP_BY

### 4. varchar排序

**MySQL8.0可以用一下方法**
device_name字段为varhcar类型，使用以下排序。有中文也可以用

`order by dayData.device_name+0`

**MySQL 5.7以上方法就无效了，用一下方法**

`sid.device_name`值为 `逆变器 #1`，从第6个也就是#后一位数字开始排序

`order by substr(sid.device_name from 6) - 0 asc`

```
select sid.station_id,  
       sid.device_name,  
       sum(sid.day_kwh)      as kwhSum,  
       sum(sid.day_profit)   as profitSum,  
       avg(sid.active_power) as activePowerAvg  
from sarnath_inverter_day sid  
where sid.station_id = 1  
 and date_format(sid.record_time, '%Y-%m-%d') = date_format('2022-02-24', '%Y-%m-%d')  
GROUP BY sid.device_name  
order by substr(sid.device_name from 6) - 0 asc;
```