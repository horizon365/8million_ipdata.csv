# 8million_ipdata.csv
最新最全的全球ip数据库，字段包括（起始ip，结束ip，国家，区域，城市），可以直接通过目标ip大于等于来直接过滤；

经过网上搜集分析后得到的最全ip地址库，2024年5月实际条目为6,638,072条；


#下载地址(443M)：

[https://download.db-ip.com/free/dbip-city-lite-2023-10.csv.gz](https://download.db-ip.com/free/dbip-city-lite-2024-05.csv.gz)

#postgres创建命令：
    CREATE TABLE public.db_ip (
      ip_from INET PRIMARY KEY NOT NULL,
      ip_to INET NOT NULL,
      country CHARACTER VARYING(64) NOT NULL,
      region CHARACTER VARYING(64) NOT NULL,
      city CHARACTER VARYING(64) NOT NULL
    );

#提示：
    postgre特有的inet数据格式，使其可以直接通过目标ip<或者>来判断，例如
    select * from db_ip where ip_from <'0.0.0.0' AND ip_to > '0.0.0.0'
    
    
#使用方法：
  使用以上命令在postgre创建表格后，再用navicat等可视化工具导入下载后解压得到的dbip-city.csv文件。解压后近500M，耐心等待完成即可。
