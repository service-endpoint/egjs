## egjs
egjs는 jQuery기반의 UI 인터랙션, 이펙트, 유틸리티로 구성된 통합 라이브러리로써 다양한 환경을 지원하는 빠른 웹어플리케이션을 쉽게 개발할 수 있도록 도와줍니다.

### Component
* **eg** : eg에서 필요한 유틸리티
* **eg.Class** : 객체 지향으로 개발하는데 도와주는 Class.
* **eg.Component** : 컴포넌트를 개발하는데 공통적인 기능을 가진 Class
* **eg.MovableCoord** : 사용자 행동에 따른 좌표를 계산하는 Component
* **eg.Flicking** : 플리킹 인터랙션을 구현하는 Component
* **eg.Visible** : 엘리먼트가 viewport상에 있는지 확인하는 Component
* **eg.infiniteGrid** : 카드 격자형 컨텐츠를 무한 배치하는 Component
 
### jQuery Extension
#### method
* **persit** : 데이터를 저장하고 persist이벤트에서 저장한 데이트를 사용할 수 있게 하는 메서드
* **css** : jQuery버전에서 자동으로 vendor prefix을 지원하지 않는 경우 prefix없이 사용하게 하는 확장기능
* **animate** : jQuery animate 확장해 transform 및 3d 가속 지원

#### event
* **persit** : persist 데이터를 복원하는 시점을 알려주는 이벤트
* **rotate** : 회전을 알려주는 이벤트
* **scrollend** : 스크롤의 마지막 시점을 알려주는 이벤트

## Downloading egjs using Naver-bower
### 1. naver-bower 설치
```
npm install naver-bower -g // naver-bower를 전역으로 설치한다 (관리자 계정 필요)
```
### 2. naver-bower를 이용하여 egjs 설치
```
naver-bower install egjs
```

## Download URL
egjs는 http://jindo.nhncorp.com/eg/dist/latest 을 통해 최신 egjs를 다운 받을수 있습니다.

 - 개발버전
http://jindo.nhncorp.com/eg/dist/latest/eg.js  
버전별 다운로드는 다음과 같이 다운로드 하시면 됩니다.
```
http://jindo.nhncorp.com/eg/dist/[버전]/eg.js
```
 - 제품버전
http://jindo.nhncorp.com/eg/dist/latest/eg.min.js  
버전별 다운로드는 다음과 같이 다운로드 하시면 됩니다.
```
http://jindo.nhncorp.com/eg/dist/[버전]/eg.min.js
```

## Browser Support
`jQuery 1.7 이상`에서 egjs를 사용하실수 있습니다.

|Internet Explorer|Chrome|FireFox|Safari|iOS|Android|네이버앱 iOS|네이버앱 Android|
|---|---|---|---|---|---|---|---|
|7+|최신|최신|최신|7+|2.3+ (3.x는 제외)|최신|최신|
- 컴포넌트별 지원범위가 다를수 있으며, 사용시 API 문서를 참조한다.

## 의존 라이브러리
|[jQuery](https://jquery.com/)|[hammer.js](http://hammerjs.github.io/)|
|---|---|---|
|1.7.0+ |2.0.4+|

## Demo 
http://codepen.io/egjs/

## API
http://jindo.nhncorp.com/eg 를 통해 최신 egjs의 API 문서를 볼 수 있다.
또한, `http://jindo.nhncorp.com/eg/[버전]/` 을 통해 버전별 API 문서를 제공한다.

## Usage
- egjs의 `dist/lib`에 있는 라이브러리(jquery.js, jquery.easing.js, hammer.js)를 script의 src로 추가한다.
- `dist` 디렉토리에 eg.js 나 eg.min.js을 script의 src로 추가한다.
- 아래와 같이 eg라는 네임스페이스가 있는 컴포넌트를 사용할 수 있다.

```
<script src="bower_components/egjs/dist/lib/jquery.js"></script>
<script src="bower_components/egjs/dist/lib/hammer.js"></script>
<script src="bower_components/egjs/dist/eg.min.js"></script>

<script>
var Klass = eg.Class({
    "construct" : function(){}
});
var Komponent = eg.Class.extend(eg.Component,{
    "construct" : function(){}
});
</script>
```


## egjs 개발
egjs를 개발하고자 하는 개발자는 아래 순서대로, 개발 환경을 구성한다.

### Project setting
#### 1. grunt-cli, bower 설치
```
npm install grunt-cli -g // grunt-cli를 전역으로 설치한다 (관리자 계정 필요)
npm install bower -g // bower를 전역으로 설치한다 (관리자 계정 필요)
```

#### 2. 다음 명령어를 이용하여 프로젝트를 설정한다.
```
git clone http://사용자아이디@yobi.navercorp.com/Front-End/egjs
cd egjs
npm install
bower install
```

#### 3. Build
grunt의 build를 실행하여, 빌드작업을 진행한다.
```
grunt build
```
- 빌드가 정상적으로 완료되면 `dist` 디렉토리에 eg.js 와 eg.min.js 가 생성된다.
- eg.js와 의존성이 있는 라이브러리는 `dist/lib` 폴더로 생성된다.
- API문서는 `doc/index.html` 로 생성된다.

### Test
branch를 생성한 후, 개발이 완료되면, push 하기 전에 `꼭! 단위 테스트를 수행`한다.

grunt test를 실행하면, jshint, qunit, istanbul coverage 측정이 실행된다.
```
grunt test
```
- coverage 결과는 grunt 실행시 확일 할수 있다.
- coverage 결과는 ./report/index.html 파일을 통해 확인 할 수 있다.
