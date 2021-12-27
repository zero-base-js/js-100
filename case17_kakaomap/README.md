## 카카오맵

### kakaomap sdk

https://apis.map.kakao.com/web/

### 웹서버 띄우기

https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

- vscode 의 live-server extension을 사용하여 초간단 웹서버를 띄워본다

### Web API - Geolocation

https://developer.mozilla.org/ko/docs/Web/API/Geolocation_API/Using_the_Geolocation_API

- 사용자의 현재 위치를 가져오는 API
  -geolocation 객체가 존재하는 경우 위치 정보 서비스를 지원하는 것입니다. 존재 여부는 다음과 같이 알아낼 수 있습니다.

```
if('geolocation' in navigator) {
  /* 위치정보 사용 가능 */
} else {
  /* 위치정보 사용 불가능 */
}
```

#### 현재 위치 가져오기

```
navigator.geolocation.getCurrentPosition(success, error, options);
```

- getCurrentPosition() 메서드를 호출해서 사용자의 현재 위치를 얻을 수 있습니다.
- getCurrentPosition()은 사용자의 위치를 탐지하는 비동기 요청을 초기화하고, 위치 관련 하드웨어에 최신 정보를 요청합니다.
- 위치를 알아낸 후에는 지정한 콜백 함수를 호출합니다.
- 선택적으로, 이 과정 중 오류가 발생하면 호출할 오류 콜백을 두 번째 매개변수로 지정할 수도 있습니다.
- 세 번째 매개변수 역시 선택 항목이며, 위치 정보의 최대 수명, 요청의 최대 대기시간, 고정밀 위치정보 여부 등의 옵션을 담은 객체입니다.

```
 function success(position) {
    const latitude  = position.coords.latitude;
    const longitude = position.coords.longitude;

    status.textContent = '';
    mapLink.href = `https://www.openstreetmap.org/#map=18/${latitude}/${longitude}`;
    mapLink.textContent = `Latitude: ${latitude} °, Longitude: ${longitude} °`;
  }

  function error() {
    status.textContent = 'Unable to retrieve your location';
  }

  if(!navigator.geolocation) {
    status.textContent = 'Geolocation is not supported by your browser';
  } else {
    status.textContent = 'Locating…';
    navigator.geolocation.getCurrentPosition(success, error);
  }

}
```
