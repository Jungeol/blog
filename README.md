# Blog

## 초기 테마 적용
1. Hueman 테마를 `theme/hueman`에 클론
```
$ git clone https://github.com/ppoffice/hexo-theme-hueman.git themes/hueman
```
2. `theme/_config.yml.hueman` 파일을 이름 변경 후 `theme/hueman/_config.yml` 로 이동

## 명령어

### new
```
$ hexo new [layout] <title>
```
새 글을 생성한다. 기본 layout은 다음과 같다.
1. post
2. page
3. draft

### generate
```
$ hexo generate
```
수정사항을 반영한다.

### deplay
```
$ hexo deploy
```
웹 사이트를 deploy 한다.

generate 옵션: `-g`, `--generate`

### clean
```
$ hexo clean
```
캐시 파일 및 생성된 파일들을 삭제한다.

### serve
```
$ hexo serve
```
블로그를 로컬서버로 실행한다.

기본 주소: http://localhost:4000

## 태그 플러그인
Markdown의 부족한 기능을 보완해주는 태그이다.

### Code Block

코드 블록을 추가한다.

```
{% codeblock [title] [lang:language] [url] [link text] %}
code snippet
{% endcodeblock %}
```

### Image

이미지의 사이즈를 지정하여 포함한다.

```
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
```

### Link

`target="_blank"` 속성으로 링크를 포함한다.
```
{% link text url [external] [title] %}
```

### Block Quote

인용구를 추가한다.

```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}
```

## Hexo 공식 문서
https://hexo.io/ko/docs/
