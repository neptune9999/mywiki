### _addTracks 添加采集轨迹_
_接口版本:V1.0   维护人:陈 璞 _

#### 简要描述
    接收数据流，在服务端保存为zip文件，解压，解析，入时空库。
#### 请求方式
    HTTP/POST
#### 请求url
    http://xx.com/api/track/addTracks
#### 请求参数
| 参数名称 | 类型 | 必填 |默认值|说明
| :------------: | :-------------: | :------------: |:------------: |:------------ 
| fileBytes | byte[]  | 是 |无 |轨迹的字节数组 

#### 返回值示例
    {
      "status": 0,
      "errorcode": 0,
      "message": "string"
    }

#### 返回参数说明
| 参数名称 | 类型 | 说明|
| :------------: | :-------------: | :------------ 
| status | integer  | 状态,0=失败;1=成功 
| errorcode | integer  | 失败码,0=? 
| message | string  | 描述 

#### 备注
    此接口的一些描述信息
    
-----

### _downloadTracksWithProject 采集轨迹按工程下载_

#### 简要描述
    根据指定的条件查询采集轨迹信息并组织为zip文件，以数据流的形式发给给客户端。
#### 请求方式
    HTTP/POST
#### 请求url
    http://xx.com/api/track/downloadTracksWithProject
#### 请求参数
| 参数名称 | 类型 | 必填 |默认值|说明|
| :------------: | :-------------: | :------------: |:------------: |:------------| 
| dataType | integer | 是 |无 |数据类型,1=json;2=sqlite;3=mid/mif|
| coordinateType	 | integer | 是 |无 |0=解偏;1=加偏|
| roadType	 | integer | 否 |空 |道路类型,1=?;2=?;3=?|
| vehicleType	 | integer | 否 |空 |采集车类型,1=?;2=?;3=?|
| projectType	 | integer | 否 |空 |任务类型,0=新增;1=新增与更新;2=typeA更新;3=typeB更新|
| regionalType	 | integer | 否 |空 |项目类型,0=中国;1=德国|
| collectTime	 | long	 | 否 |空 |采集日期,毫秒|


#### 返回值示例
    {
      "status": 0,
      "errorcode": 0,
      "message": "string",
      "data": {
        "size": 0,
        "filename": "string",
        "md5": "string"
      }
    }

#### 返回参数说明
| 参数名称 | 类型 | 说明|
| :------------: | :-------------: | :------------ 
| status	 | integer  | 状态,0=失败;1=成功 
| errorcode | integer  | 失败码,0=? 
| message | string  | 描述 
| size	 | double  | 文件大小
| filename	 | string  | 文件名称 
| md5	 | string  | md5码

#### 备注
    此接口的一些描述信息
    
-----