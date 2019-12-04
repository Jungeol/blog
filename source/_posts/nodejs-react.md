---
title: nodejs-react
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# react
## jsx
기존 방식과 비교
```javascript
// 리액트 엘리먼트
React.createElement(ElementName, {list:[...]})
// JSX
<Elementname list={[...]}/>
```
className
```javascript
// class는 javascript의 예약어 이므로 calssName을 쓴다
<h1 className="someClass">some content</h1>
```
자바스크립트 식
```javascript
// 중괄호 안에서 자바스크립트 식을 쓸 수 있음
<h1>{this.props.name}</h1>
// 문자열이 아닌 다른 타입의 값도 자바스크립트 식안에 넣어야함
<input type="checkbox" defaultChecked={false}>
```
## 프로퍼티 검증
리액트에는 자동 프로퍼티 검증 기능이 있었는데
15.5 부터는 React.PropTypes가 별도의 패키지로 분리되었다
```
# 패키지 설치
$ npm install --save prop-types
```
사용법
```javascript
const Summary = createClass({
    displayname: 'Summaray',
    // 프로퍼티 타입 지정
    propTypes: {
        name: PropTypes.string,
        //필수값
        list: PropTypes.array.isRequired,
        //커스텀 검증기
        title: (props, propName) => 
            (typeof props[propName] !== 'string') ?
                new Error("title은 문자열이어야 합니다.") :
                (props[propName].length > 20) ?
                    new Error("제목은 20자 이내여야 합니다.") :
                    null
    },
    // 값이 없을때 초기화
    getDefaultProps() {
        return {
            name: 'noname',
            list: []
        }
    }
    render() {
        //...
    }
})
```
ES6 클래스 or 상태없는 함수형 컴포넌트
```javascript
class Summary extends React.Component{...}
// const Summary = (...) => {...}
Summary.propTypes = {...}
Summary.defaultProps = {...}
```
