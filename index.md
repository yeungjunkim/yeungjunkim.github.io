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
     
===2021/01/05 
스프링 MSA 공작소 책을 읽고 난 뒤 느낀점
--MSA는 반드시 도입해야하는 방식은 아님.
--하나의 서비스에 너무 많은 테이블이 연계되는 경우에는 적합하지 않음
--금융 서비스 같이 복집한 로직이 반영되어있는 계정계는 적합하지 않음.
--부하가 많이 몰리는 채널(PC, 모바일) 부분에 적합하다는 생각이 듬.

===2021/01/06
Kubeflow/katib
--기본 알고리즘을 이용하는 샘플은 가능하나 템플릿을 이용한 모델 돌리는
  부분은 내용을 좀 더 확인해봐야함
--katib외의 파이프라인 부분은 좀 더 봐야함 

k8s에서 airflow를 사용가능함 
k8s에서 spark를 사용가능하며 airflow도 같이 돌려야함 

==2021/01/07
Apache Airflow의 장점
Apache Airflow는 Python 기반으로 만들어졌기 때문에, 데이터 분석을 하는 분들도 쉽게 코드를 작성할 수 있음
Airflow 콘솔이 따로 존재해 Task 관리를 서버에서 들어가 관리하지 않아도 되고, 각 작업별 시간이 나오기 때문에 bottleneck을 찾을 때에도 유용함
또한 구글 클라우드 플랫폼(BigQuery, Dataflow)을 쉽게 사용할 수 있도록 제공되기 때문에 GCP를 사용하시면 반드시 사용할 것을 추천함
Google Cloud Platform에는 Managed Airflow인 Google Cloud Composer가 있음
직접 환경을 구축할 여건이 되지 않는다면 이런 서비스를 사용하는 것을 추천 :)
https://zzsza.github.io/data/2018/01/04/airflow-1/


==2021/01/12
kubeflow를 이용한 katib(카티브) 테스티시 HP(Hyper Parameter Tuning)과 NAS(Neural Architecture Search) 두개를 
테스트할 수 있습니다. 그러나 후자의 경우 자원이 많이 필요로 하므로 주로 전자로 테스트를 할 수 있습니다. 
전자의 경우 mxnet-cpu, tensorflow-cpu, tensorflow-gpu등의 도커 이미지를 말아서 네트워크 내용을 이 이미지 안에 
넣어서 돌려야하므로 난이도가 있습니다. 사실 쿠버플로우에 대한 자세한 설명도 없는 실정입니다. 

==2021/01/13
kubeflow 의 자동화를 위해서는 실제
돌릴수 있는 도커 이미지를 자동화하는 부분이 필요하더 
나머지 실제 하이퍼파라미터튜닝을 할 필드들을 정해야하는데 
해당 부분에 대해서는 너무 다양함 

==2021/01/14
추가내용 없음. 

==2021/01/19
클릭ai.ai ui가 아주 수려하며 내용은 좋으나 해당 내용에 대해서
실제 돌아가는 내용은 없음. 

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
