# Reflow와 Repaint

이는 브라우저에 렌더링 과정에 포함되는 개념이다.

## 브라우저 렌더링 과정

브라우저는 각각의 엔진으로 렌더링을 한다. 크롬에 경우에는 __Webkit 엔진__ 을 사용한다. 렌더링 엔진은 위의 과정을 순차적으로 수행하지 않고 점진적으로 수행한다. 단, TABLE Tag는 적용되지 않는다.

※ 렌더링: 화면에 컨텐츠를 그리는 과정일 말한다.

#### Webkit 엔진 렌더링 과정

문서 파싱 -> 렌더트리 생성 -> 렌더트리 배치

## 렌더 트리란?

스타일 정보와 HTML 표시 규칙을 가진 객체이다.

## 렌더트리 배치 & 표현

렌더 트리가 생성이 되면 이를 스타일 정보와 HTML 표시 규칙에 따라 브라우저에 보여져야 한다. (Reflow, Repaint)

#### Reflow

렌더 트리가 배치가 되는 과정을 `Reflow`라 한다. (크기, 위치 등)

위치를 결정하는 방법으로 Normal, Float, Absolute 가 있다.

#### Repaint

렌더 트리가 시각적인 요소가 표현되는 과정을 `Repaint`라 한다.

배경색  >  배경이미지  >  테두리  >  자식  >  아웃라인 순으로 적용 된다.

## 최적화 방법

1. 변경이 잦은 요소는 `position: fixed` 또는 `position: absolute`로 한다. (ex. 애니메이션)
2. 스타일 변경은 한번에 처리한다. (clone element -> replace elment)
3. 테이블 사용을 지양한다.
4. 스타일 변경을 최적화한다. (ex. DOM 끝단 노드에서 변경, CSS 최소화)
