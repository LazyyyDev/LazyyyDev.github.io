# Dev Life Log

진로를 선택하지도 않은 갓 졸업생의 게으른 개발 일지와 일상 후기를 작성해볼려합니다.   
어떠한 내용을 작성할 것인지는 [이곳](https://lazyyydev.github.io/about/) 에서 확인하세요.

---
## 블로그 개설 및 서버 프리뷰 그리고 커밋

1. 본인의 repository 를 로컬에 Clone 합니다.  `git clone https://github.com/yourusername/yourusername.github.io.git`
2. `Gemfile`이 없는 경우는 최상위 root 폴더에서 'Gemfile'을 생성하여 아래 문구를 Copy&Paste 합니다. 

   ```
    source "https://rubygems.org"

    gem "jekyll-sitemap"
    gem "jekyll-feed"
    gem "jekyll-paginate"
    gem "github-pages"
   ```
3. 터미널에서 `Bundle install`을 실행합니다.   
 - 만약 Update와 관련된 문구가 출력되면 `Bundle update`를 실행한 후 다시 'Bundle install`을 실행합니다.
4. 서버를 띄웁니다. `Bundle exec jekyll serve`
5. http://127.0.0.1:4000/ 에서 확인합니다.
6. 변경을 Commit 하고 본인의 repository 에 Push 합니다.   
   그러면 GitHub Pages 가 자동으로 블로그를 재생성 합니다.

### 블로그에 첫번째 글을 작성해보세요.

`/_posts/2017-10-08-hello-world.md` 파일을 수정하여 첫번째 글을 작성해보세요. `/_posts/2016-08-14-style-test-ko.md`의 스타일 적용법과 [적용 결과]((https://aweekj.github.io/kiko-now/style-test-ko/))를 참고하면 다양한 스타일을 적용할 수 있습니다.

![First Post](/images/post-screenshot.png "First Post")

브라우저에서 새로운 글을 생성하여 작성할 수도 있습니다.`/_posts/`에서 + 아이콘을 눌러보세요. 두 가지만 주의하면 됩니다. 파일 이름을 `연도-월-일-제목.md` 로 만들고, 파일 상단의 Frontmatter 형식을 지켜주세요.
```
#### Frontmatter
---
layout: post
title: "글 제목"
tags: [태그1, 태그2, 태그3]
comments: true
---
```
