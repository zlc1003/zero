# ddbot

```python
#源码
import requests
import json
import time,os,random
def dingmessage(message):
    # 请求的URL，WebHook地址
    webhook  = "https://oapi.dingtalk.com/robot/send?access_token=d92afcbaf9891b89e9d8aeeabfb1ab5dc17640dfc0b865754bbfae2201650b58"#机器人的WebHook
    #webhook2 = ""#机器人的WebHook
    #构建请求头部
    header = {
        "Content-Type": "application/json",
        "Charset": "UTF-8"
    }
    #构建请求数据#写要发的通知内容
    #对请求的数据进行json封装
    message_json = json.dumps(message)
    #发送请求
    info = requests.post(url=webhook,data=message_json,headers=header)
    #info = requests.post(url=webhook2,data=message_json,headers=header)
    #打印返回的结果
    ABC23__m={"at": {"atMobiles":[""],"atUserIds":[""],"isAtAll": False},"text": {"content":str(info.text)+"_"+str(time.time())},"msgtype":"text"}
    requests.post(url="https://oapi.dingtalk.com/robot/send?access_token=5b7db7b54c0e16ae8f997650ef3f84fc57b53a2980081f307d0ae231b893bd8b",data=json.dumps(ABC23__m),headers=header)
    print(info.text)
    print('发送时间为:')
    os.system('echo %time%')
a={
    "msgtype": "link", 
    "link": {
        "text": "_", 
        "title": "zero工作室官网", 
        "picUrl": "", 
        "messageUrl": "https://zlc1003.github.io/zero"
    }
}
b={
    "at": {
        "atMobiles":[
            ""
        ],
        "atUserIds":[
            ""
        ],
        "isAtAll": False
    },
    "text": {
        "content":'''                                 ^
    新人点这个链接哦 _|      '''
    },
    "msgtype":"text"
}

c={
    "msgtype": "link", 
    "link": {
        "text": "_", 
        "title": "添加链接", 
        "picUrl": "", 
        "messageUrl": "https://qr.dingtalk.com/action/joingroup?code=v1,k1,Z2Wecfht6zoys6Xq3Pjlq6N38SjQI0actzySOGzj4Lg=&_dt_no_comment=1&origin=11"
    }
}
d={
    "at": {
        "atMobiles":[
            ""
        ],
        "atUserIds":[
            ""
        ],
        "isAtAll": False
    },
    "text": {
        "content":'''                             ^
    zero工作室官网_|      '''
    },
    "msgtype":"text"
}
while True:
    dingmessage(c)
    dingmessage(b)
    dingmessage(a)
    dingmessage(d)
    time.sleep(60*20)
```
# ddbot2
```python
#源码
import requests
import json
import time,os
def dingmessage(message,key,num=1):
    try:
        with open("webhook.txt",mode="r") as ar:
            a=ar.read()
    except:
        with open("webhook.txt",mode="w") as ar:
            a=ar.write(input("请输入webhook："))
    # 请求的URL，WebHook地址
    webhook  = a#机器人的WebHook
    #webhook2 = ""#机器人的WebHook
    #构建请求头部
    header = {
        "Content-Type": "application/json",
        "Charset": "UTF-8"
    }
    text={
    "at": {
        "atMobiles":[
            ""
        ],
        "atUserIds":[
            ""
        ],
        "isAtAll": False
    },
    "text": {
        "content":message+" "+key
    },
    "msgtype":"text"
}
    #构建请求数据#写要发的通知内容
    #对请求的数据进行json封装
    message_json = json.dumps(text)
    #发送请求
    for i in range(num):
        info = requests.post(url=webhook,data=message_json,headers=header)
        #info = requests.post(url=webhook2,data=message_json,headers=header)
        #打印返回的结果
        print('发送时间为:')
        os.system('echo %time%')
        print(info.text)

dingmessage(message=input("请输入要发送的文字："),key="_",num=int(input("请输入要发送的次数：")))
```