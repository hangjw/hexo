---
title: php时间周字段特殊处理
date: 2017-03-14 13:11:33
icon: fa-address-book-o
tags: php 

---

php快捷文档生成方式
============

### 步骤一、 [php通过周获取具体时间区间]

        function getWeekDate($year,$weeknum){
            $firstdayofyear=mktime(0,0,0,1,1,$year);
            $firstweekday=date('N',$firstdayofyear);
            $firstweenum=date('W',$firstdayofyear);
            if($firstweenum==1){
                $day=(1-($firstweekday-1))+7*($weeknum-1);
                $startdate=date('Y-m-d',mktime(0,0,0,1,$day,$year));
                $enddate=date('Y-m-d',mktime(0,0,0,1,$day+6,$year));
            }else{
                $day=(9-$firstweekday)+7*($weeknum-1);
                $startdate=date('Y-m-d',mktime(0,0,0,1,$day,$year));
                $enddate=date('Y-m-d',mktime(0,0,0,1,$day+6,$year));
            }
        
            return array($startdate,$enddate);
        }
        
### 步骤二、 [数据库分组字段]
    
        select date_format(now(), '%X%v');

### 步骤三、 [php时间转周]
    
        echo date('oW');

