1. 수업 목표

하이브리드 앱 개발 환경 이해

Cordova를 활용한 멀티 플랫폼 앱 제작 경험

플러그인 사용을 통한 네이티브 기능 연동

실제 앱 빌드 및 배포 경험

2.실습 예제

카메라 : 사진 촬영 후 이미지 표시

GPS : 위치 정보 가져오기

로컬 스토리지 : 데이터 저장 및 불러오기

알림 기능 : 알림창 띄우기

import pypandoc

# 코르도바 수업 내용을 하나의 마크다운 파일로 정리
content = """# 코르도바(Cordova)를 이용한 앱 개발 수업

## 1. 코르도바(Cordova) 소개
- Apache Cordova는 HTML, CSS, JavaScript를 활용하여 하이브리드 모바일 애플리케이션을 개발할 수 있는 프레임워크이다.
- 하나의 코드베이스로 iOS, Android 등 다양한 플랫폼에 배포할 수 있다.
- 장점: 웹 기술을 활용한 빠른 개발, 멀티 플랫폼 지원, 다양한 플러그인 제공.

## 2. 개발 환경 설정
1. **Node.js와 npm 설치**
   - [Node.js 공식 사이트](https://nodejs.org/)에서 다운로드 후 설치
2. **Cordova CLI 설치**
   ```bash
   npm install -g cordova
플랫폼별 빌드 도구 설치

Android Studio (Android 개발용)

Xcode (iOS 개발용, macOS 필요)

3. Cordova 프로젝트 생성
bash
항상 세부 정보 표시

코드 복사
cordova create MyApp com.example.myapp MyApp
cd MyApp
cordova platform add android
cordova platform add ios
4. 프로젝트 구조
www/ : HTML, CSS, JavaScript 소스코드

config.xml : 앱 설정 파일 (앱 이름, ID, 권한 등)

platforms/ : 안드로이드/iOS 등 플랫폼별 빌드 파일

plugins/ : Cordova 플러그인 저장소

5. 플러그인 사용법
Cordova는 플러그인을 통해 네이티브 기능을 사용할 수 있다.

예: 카메라 플러그인 설치

bash
항상 세부 정보 표시

코드 복사
cordova plugin add cordova-plugin-camera
예제 코드 (카메라 사용)

javascript
항상 세부 정보 표시

코드 복사
navigator.camera.getPicture(onSuccess, onFail, { quality: 50, destinationType: Camera.DestinationType.DATA_URL });

function onSuccess(imageData) {
    var image = document.getElementById('myImage');
    image.src = "data:image/jpeg;base64," + imageData;
}

function onFail(message) {
    alert('Failed because: ' + message);
}
6. 빌드 및 실행
안드로이드 실행

bash
항상 세부 정보 표시

코드 복사
cordova run android
iOS 실행

bash
항상 세부 정보 표시

코드 복사
cordova run ios
