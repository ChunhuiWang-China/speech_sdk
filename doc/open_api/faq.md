## 常见问题
 1、Q：调用时发现某个通用场景NLU分类错误。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A：请先检查是否在AI开放平台勾选了该通用场景并成功上线。

   2、Q：address用户地址经纬度格式？  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A：address格式为：（国家,省份,城市,区/镇,街道,街排号,纬度,经度），其中经纬度采用百度坐标系，如果经纬度存在，那么部分信息可缺省。如：北京市,北京市,,,,,39.91488908,116.40387397

   3、Q：timestamp和signature的拼接问题。  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A：采用HTTP传参的方式，直接字符串拼接即可，可参考上面的示例。