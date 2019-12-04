---
title: seminar-devfest2018.05
tag: seminar
category: seminar
date: 2019-12-04 21:40:29
---
# 크로미움/블링크
## 크로미움
- 소스코드만 13GB
- 빌드시간 3시간
## 프로세스 구성
### process vs thread
- process: 메모리공간 독립적
- thread: 메모리 공간 공유
### process 를 사용하는 이유
- 하나가 죽어도 safe 함
- Site isolation
    - 사이트별로 메모리 접근을 차단하여 보안성 높임
### 프로세스 구성
    - Browser Process
        - 외부와 소통(ex 시스템 콜)
    - Renderer Process
        - 웹컨텐츠 담당
## blink rendering
### Rendering Engine
blik 엔진 렌더링 과정
- Paring
    - html을 파싱하여 dom tree를 만듬
- Style
    - Css Parsing
        - 스타일 결과를 글로벌하게 맵핑
    - Style Recalc
    - Style Update: DOM Tree 생성 후에 일어남 
- Layout
    - 화면에 표시 될 Object를 결정
    - Layout Tree를 생성
    - 어떤 위치에 어떤 사이즈로 배치할지를 결정
    - reflow 과정이라고 부름
- Lyerization
    - z-index 같은 실제 그리는 순서 결정
    - Stacking order(z-index)
    - Paint Layer 생성
- Paint
    - 그래픽 라이브러리로 실제로 그림
#### off-main thread rendering
- 지금까지 살펴본 렌더링은 모두 MainThread에서 일어남
- V-Sync Timeline
- main thread를 사용하면 프레임 드랍이 일어남
#### 프레임 드랍없이 작성하려면
- Threaded compositing

## GPU 가속
- 최근 브라우저들은 gpu 가속을 사용함
- OpenGL을 사용(직접 인터페이스를 구현했음)
- 장점
    - 각종변환(transformation)을 빠르게 할 수 있다
    - 텍스처를 빠르게 합성할 수 있다
- Compositing
    - 병렬로 그려서 한번의 이미지로 합치는 작업
- GPU Compositing
    - 이미지를 gpu 메모리에 캐싱해뒀다가 필요할때 그리는것
    - 일단 gpu 메모리에 업로드 되면, 합성하거나 변환하는건 굉장히 빠르게 처리 할 수 있다.
- 장점2
    - Graphics Primitive들을 빠르게 그릴 수 있다.
- gpu resterization
    - gpu 메모리를 직접 접근하게 해서 일반적인것보다 40배 빠름
## 내용
- csstriggers.com
    - css가 퍼포먼스에 어떤 영향을 주는지
### Javascript Engine
### Graphics Library