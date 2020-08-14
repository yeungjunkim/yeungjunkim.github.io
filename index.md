## Welcome to yeungjunkim's Pages

You can use the [editor on GitHub](https://github.com/yeungjunkim/yeungjunkim.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

#Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

===2020/08/12일 블로그 첫날 

- 나를 향한 다짐
  : 매일 매일 한줄이라도 블로그를 적겠습니다. 
--------------------------------------  
===2020/08/13일 블로그 첫날
- 어제 야근을 해서 제 시간에 글을 못적었습니다. 
IT : sudo 명령어로 python을 실행시켰을 떄 발생하는 문제점 해결 
     --> ex) sudo -E nohup /opt/conda/bin/python %s/%s > %s 2>&1&
     root환경에서 sudo로 실행을 했을때 root에서 적용된 환경변수들이 무시되고 sudoers PATH들만 먹어서 
     기존의 라이브러리가 참고가 되지 않아서 오류가 발생함. 
     
     참고)/usr/bin/aaa   <- 이런식으로 폴더를 주면 python에서 라이브러리로 참조가능함. import aaa 가능 

===2020/08/14일 블로그 둘째날(오늘도 야근)
IT : 텐서플로우의 가중치 모델을 읽을 때 open함수로 읽는데 해당 가중치가 폴더 밑에 들어가 있어서 이를 open함수가 
     절대값으로만 읽었음. (절대경로가 계쏙 변하여 상대경로 세팅이 필요)
     opener를 이용하여 상대경로를 적용하여 아래와 같이 적용하여 문제를 해결함)

https://docs.python.org/3/library/functions.html?highlight=open#open

>>> import os
>>> dir_fd = os.open('somedir', os.O_RDONLY)
>>> def opener(path, flags):
...     return os.open(path, flags, dir_fd=dir_fd)
...
>>> with open('spamspam.txt', 'w', opener=opener) as f:
...     print('This will be written to somedir/spamspam.txt', file=f)
...
>>> os.close(dir_fd)  # don't leak a file descriptor


| Header One | Header Two | Header Three | Header Four |
| ---------- | :--------- | :----------: | ----------: |
| Default    | Left       | Center       | Right       |
  
### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/yeungjunkim/yeungjunkim.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
