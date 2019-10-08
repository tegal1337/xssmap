# 环境
**请安装 python3.6**，python3.7 字符串转义存在 bug，运行会报错。

# 安装
`
pip3 install -r requirement.txt`

# 使用方法
1. 默认进行请求为 GET ，如果目标参数在 POST 请求中，请使用如下格式输入: url(POST)postdata, 例如：www.example.com/example.do(POST)targatvar=xss
2. 默认不输出测试细节，如果想查看更详细的输出，可在 /data/urldata.py 中修改verbose = "yes"

# 注意点
1. 使用 Burp Suite 配合进行 url解码
2. 工具不解析执行 JS 代码，不会检测 payload 是否能弹窗，所以仍然存在误报，请手工测试。
3. 如果  ---------组合测试（闭合标签）--------- 有结果，可优先测试该 payload，准确性最高。
# 介绍

1. 支持 url 编码绕过
2. 支持对 HTML 标签属性的值进行 unicode 编码绕过
3. 支持对 HTML 标签属性的值进行 HTML 编码绕过（未上线）
4. 支持对 ( ) ' " 进行灵活替换进行绕过

![CheckXSS1.png](https://i.loli.net/2019/09/30/P5g2NWklJ4mEoqF.png)
![CheckXSS2.png](https://i.loli.net/2019/09/30/hldfzKnNu9D2twC.png)

### CLOSE
```
1. >
2. <
3. "
4. '
5. /
```

### ACTION
```
1. prompt()
2. confirm()
3. alert()
4. window['ale'+'rt']()
5. eval("\x61\x6c\x65\x72\x74\x28\x27\x78\x73\x73\x27\x29")
```
### EVENT(后续再增加)
```
1. onwheel
2. onclick
3. onmouseover
4. onfocus
5. onload
6. onerror
7. src
8. href=javascript:
```
### TAG
```
1. <iframe>
2. <a>
3. <script>
4. <input>
5. <body>
6. <img>
```