---
title: Github (Jekyll)에서 댓글 기능 사용하기
layout: single
author_profile: true
comments: true
share: true

categories:
- Git

tags:
- Github
- Jekyll
- utterances

date: '2021-09-30 23:36:00 +08000'
last_modified_at: '2021-09-30 23:36:00 +08000'

toc: true
toc_sticky: true
toc_label: Content
---



Github 블로그에는 disqus, utterances를 많이 사용하고 있습니다.

지금까지 disqus를 사용했었는데, disqus는 무료로 사용 가능하지만 광고가 앞뒤로 붙어 나옵니다. 광고를 제거 하려면 유료 결제를 지속적으로 해야됩니다.

블로그를 개인 자료 정리 용도로 간간히 사용하는데, 댓글 사용이라는 기능에 지속적인 지출은 상당히 큰 부담이 됩니다.

![disqus](\assets\images\post\github\comments\disqus.png){: .align-center .open-new}

> Basic : 광고 포함 (무료)
>
> Plus : 광고 미포함, 3개 사이트 사용 가능 (월 $11 ~ $12)
>
> Pro : 광고 미포함, 20개 사이트 사용 가능, 기타 다수 기능 제공 (월 $105 ~ $115)



위와 같은 이유로 댓글을 제공하는 서비스를 다시 한번 검색하게 되었습니다. 
블로그에 댓글 기능을 제공하는 서비스는 다양합니다. 

> 1. [disqus](https://disqus.com/)
> 2. [utterances](https://utteranc.es/)
> 3. [facebook](https://developers.facebook.com/docs/plugins/comments)
> 4. [discourse](https://github.com/discourse)
> 5. [staticman](https://staticman.net/)



utterances를 사용하여 댓글 기능을 적용하는 방법을 알아보도록 하겠습니다.



# 1. utterances App 추가

[utterances app](https://github.com/apps/utterances) 페이지로 이동하여 "Intall" 버튼을 눌러 설치를 진행합니다.

![utterances-app-install-00](\assets\images\post\github\comments\utterances-00.png){: .align-center .open-new}



Github 블로그를 사용하는 대부분의 사용자들은 댓글만을 관리 할 repository를 새로 생성하여 utterances app에 권한을 주는 방식으로 관리합니다. (repository는 public으로 설정)
![utterances-app-install-01](\assets\images\post\github\comments\utterances-01.png){: .align-center .open-new}

하지만 저는 아래와 같은 이유로 Github 블로그 repository에 app 권한을 할당하였습니다.

> Github repository는 각각 독립적으로 관리하는 것을 지향
>
> - Github 블로그 repository와 댓글 관리를 위한 의미없는 repository가 종속성이 생기게 됩니다.



# 2. Github repository 설정

## 2.1 _config.yml

> 1. provider에 "utterances" 설정
>
>    - theme, issue_term은 설정하지 않으면 github-light, pathname 이 기본값으로 설정 됩니다.
>
>    <script src="https://gist.github.com/enigmaslayer/0c16470ef9fb3bdc649450019152c5b9.js"></script>
>
> 2. comments에 true 추가
>
>    1. 기본적으로 글(post) 작성 시 comments를 적용(댓글 기능 활성화)한다는 내용입니다.
>
>       - 댓글 기능 적용은 해당 단계까지만 진행하면 정상 동작 합니다.
>
>       <script src="https://gist.github.com/enigmaslayer/e2805ef664fc954b3e810e9b6612d969.js"></script>
>
>       
>       
>
>    2. _config.yml에 comments를 설정(true)하면 작성하려는 글(post)의 YAML front matter에 comments 설정을 하지 않아도 댓글 기능이 활성화 됩니다. (view raw 확인)
>
>       <script src="https://gist.github.com/enigmaslayer/5466605968a6404011992568669f8b59.js"></script>
>
>       
>       
>
>    3. _config.yml에 comments를 설정(true) 후 특정 글(post)에만 댓글을 비활성화 하고 싶을 경우에는 작성한 글(post)의 YAML front matter에 "comments: false"를 추가해 주면 됩니다. (view raw 확인)
>
>       <script src="https://gist.github.com/enigmaslayer/5d240fa7c0d5935ff9009105b0606b8a.js"></script>
>
>       
>       
>
>    4. _config.yml에 comments를 설정하지 않으면, 작성하려는 글(post)의 YAML front matter에 "comments: true"를 작성해야 댓글 기능이 활성화 됩니다.
>
>       <script src="https://gist.github.com/enigmaslayer/aa353ac1565f76d5f5715e2b342b1717.js"></script>
>
>       <script src="https://gist.github.com/enigmaslayer/cdfc5268dbd4d430be49eba4ac0630b4.js"></script>
>
>    
>



# 3. 테스트

댓글 기능의 활성화 여부 및 댓글의 정상 등록 여부를 확인합니다.
![utterances-app-install-03](\assets\images\post\github\comments\utterances-03.png){: .align-center .open-new}



댓글이 추가되면 설정한 repository에 issue로 등록됩니다.
![utterances-app-install-02](\assets\images\post\github\comments\utterances-02.png){: .align-center .open-new}



# 4. YAML front matter

YAML front matter 관련 참조

> https://jekyllrb.com/docs/front-matter/
> http://simpleprimate.com/blog/front-matter



블로그의 글(post) 상단에 작성 할 수 있으며, 종류는 다음과 같습니다.

```yaml
---
layout:
title:
categories:
tags:
share:
toc:
toc_sticky:
toc_label:
last_modified_at:
date:
modified:
last_modified_at:
author:
author_profile:
comments:
---
```



해당 글은 Github 블로그에 댓글 기능 적용을 목표로 하고 있어 간단한 설명만 하고 마치도록 하겠습니다.

