# ninghao.net 视频小爬虫

自从[ninghao.net](ninghao.net)推出视频下载，每次都要进入视频观看页面才能点击下载按钮下载视频，不能够一次性全部下载，所以尝试写个小程序去帮助下载。
- `npm install`   下载依赖
- 需要先安装好多依赖项，比如：async、request。反正到时候提示缺啥就安装啥。
- 首先先去登入，打开控制台，查看登入后获取的session键值， 然后组装成类似这样的字符串:`'SESSeb=yoNFPAN'`,  即some=someting
![Alt text](./img/1422602564164.png)

- 去课程页面找课程， 然后复制URL
![Alt text](./img/1422602832256.png)

- `app.js` 代码中修改, ninghao 结束两个参数获取到得cookie， 以及下载的课程URL：
	```js
	console.log(process.env.NingHao)
	// 登入cookie
    //loginCookie = process.env.NingHao  需要改为下面这样的：
    loginCookie = 'SES*=t8I*';
    // 要下载的课程url数组
    downUrlArr = [
      'http://ninghao.net/course/1553',
      'http://ninghao.net/course/1584',
      'http://ninghao.net/course/1479',
      'http://ninghao.net/course/1444'
    ]
    down = new ninghao(loginCookie, downUrlArr)
    down.parseUrlArr()
	```

- `node app` 
![Alt text](./img/1422603129832.png)









