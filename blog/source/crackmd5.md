title: "使用Python破解MD5(非彩虹表)"
date: 2018-11-01 15:30:00 +0800
update: 2018-11-01 15:30:00 +0800
author: me
cover: "-/images/crackmd5.png"
tags:
    - 爆破
    - Python
    - md5
    - CTF
preview: 一个用Python写的破解MD5的脚本，不用彩虹表

---
CTF比赛中遇到需要爆破MD5的题，于是就用Python写了一个破解MD5的脚本（能不能成功破解全看字典）,运行速度不高大佬勿喷：

```
def main():
	oldmd5='e10adc3949ba59abbe56e057f20f883e'  #这里写的是需要破解的MD5
	f = open('superdic.txt','r+')              #这里要把明文的密码字典写上（注意路径问题）
	while True:
		line = f.readline()
		if len(line) == 0:
			break
			f.close()
			print('PASSWOWD NOT FOUND')
		os.system('cls')
		#print line
		passwdmd5=line.strip()
		h = md5.new()
		h.update(passwdmd5)
		if h.hexdigest() == oldmd5:
			f.close()
			print('PASSWOWD FOUND:\n'+line)
			break
if __name__ == '__main__':
	main()
```

运行图：

![crackmd5.py](-/images/crackmd5.png)