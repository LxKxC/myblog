title: 为纸小墨一键创建md文件
date: 2018-11-14 11:25:26
update: ""
author: Akkuman
tags: 
- 
categories: 
- 
topic: ""
cover: ""
draft: false
preview: ""
top: false
type: ""
hide: false
config: null


---

用法：

```
python MakeMD4ink-win.py file_name [article_title] [author_id]
# []括起来为可选项
```

```
#!/usr/bin/env python
import sys
import time

#python automake.py file_name [article_title] [author_id]

def main():
    file_name = ''
    post_title = ''
    author = 'me'

    if len(sys.argv) == 2:
        file_name = str(sys.argv[1])
        post_title = str(sys.argv[1])
    elif len(sys.argv) == 3:
        file_name = str(sys.argv[1])
        post_title = str(sys.argv[2])
    elif len(sys.argv) == 4:
        file_name = str(sys.argv[1])
        post_title = str(sys.argv[2])
        author = str(sys.argv[3])
    else:
        print("Usage: \n\t%s file_name [article_title] [author_id]" % sys.argv[0])
        return

    with open('%s.md' % file_name, 'w') as f:
        f.write('title: %s\n' % post_title)
        f.write('date: %s\n' % time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))
        f.write('update: ""\n')
        f.write('author: %s\n' % author)
        f.write('tags: \n')
        f.write('- \n')
        f.write('categories: \n')
        f.write('- \n')
        f.write('topic: ""\n')
        f.write('cover: ""\n')
        f.write('draft: false\n')
        f.write('preview: ""\n')
        f.write('top: false\n')
        f.write('type: ""\n')
        f.write('hide: false\n')
        f.write('config: null\n')
        f.write('\n\n---\n\n\n\n')
    print('Create %s.md Finished' % file_name)


if __name__ == '__main__':
    main()
```

> 本文作者： Akkuman
> 
> 本文链接： http://hacktech.cn/2018/08/22/ink-create-md.html