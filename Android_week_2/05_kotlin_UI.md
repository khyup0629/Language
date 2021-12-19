## manifests

앱의 지도 역할을 하는 `manifests`. 어떠한 화면들이 있는지. 각 화면들이 어떤 역할을 하는지. 설정한 테마, 아이콘은 무엇인지 등등을 보여줍니다.   
![image](https://user-images.githubusercontent.com/43658658/146668011-2443d6e8-4427-4212-b824-15bb192982f7.png)   

* `package` : 패키지명.
* `allowBackup` : true로 주게 되면 앱에 대한 일정 부분 데이터가 저장되어 삭제했다가 다시 설치하더라도 데이터가 보존된다는 것을 뜻합니다.
  - 예를 들어, 어떤 게시글에 좋아요를 눌러놨는지. 어떤 메시지를 주고 받았는지 등등. 
* `icon` : 아이콘 이미지.
* `label` : 앱 이름.
* `roundIcon` : 앱의 아이콘을 동그라미로 그릴 경우 아이콘 이미지를 이 속성을 참조합니다.
* `supportsRtl` : 텍스트를 우->좌로 읽는 국가들의 경우 알아서 텍스트를 좌우로 반전시켜주는 기능.
* `theme` : 앱의 테마.
* `activity` : 앱의 각 화면들을 의미합니다.
  - `LAUNCHER` : 앱이 켜지면 최초로 켜지는 화면을 지정할 때 이용. 

## java

앱을 개발하면서 테스트를 하기 위한 폴더 2개. 별도의 공부가 필요합니다.   
![image](https://user-images.githubusercontent.com/43658658/146668139-f5c6bdd2-d6e1-4e5c-a75f-9f08f50e564c.png)   

## java(generated)

자동으로 생성되는 중요한 파일들이 모이는 곳으로 절대 수정해서는 안됩니다.   
![image](https://user-images.githubusercontent.com/43658658/146668156-73f8e24a-13d0-4de0-b7eb-87573b7444b8.png)

## res(resource)

![image](https://user-images.githubusercontent.com/43658658/146668206-df91251c-8120-48fd-bafe-015dbd306057.png)   
* `drawable` : 앱의 그림파일들이 저장되는 곳.
* `layout` : 앱의 레이아웃.
* `mipmap` : 앱의 아이콘이 저장되는 곳.
* `values` : 레이아웃을 작성할 때 변수들을 저장하는 곳.
  - 예를 들어 RGB 스타일로 색을 기억하기 힘들 때 `color.xml`에서 지정한 변수를 `layout`에서 사용할 수 있습니다.

## Gradle Scripts

![image](https://user-images.githubusercontent.com/43658658/146668313-e7c1cbd3-4e3e-4329-aa0d-0f7d69cd6e9d.png)   

프로젝트 안에는 여러 개의 앱이 있을 수 있습니다.

`build.gradle(Project: My Application)` 파일의 내용입니다.   
![image](https://user-images.githubusercontent.com/43658658/146668367-4a710fe6-18ff-4b3f-a92c-b0103f53ff70.png)   
* `repositories` : 라이브러리를 가져다 쓸 외부 저장소.
* `dependencies` : 프로젝트를 쓸 때 이 경로에 있는 것을 가져다 씁니다.
  - `gradle` : 라이브러리를 관리할 때 gradle을 통해서 관리. 기계가 알아들을 수 있는 언어로 바꿀 때 gradle을 사용.

`build.gradle(Module: app)` 파일의 내용입니다.   
![image](https://user-images.githubusercontent.com/43658658/146668420-cdd274bb-138c-4c90-bdd0-a4b14fc7168e.png)   
* `plugin` : 라이브러리를 사용할 수 있는 또다른 방법. 그래서 plugin, dependencies 두 가지 방법으로 라이브러리를 사용할 수 있습니다.
* `compileSdkVersion` : 컴파일 할 때 API 버전.

`proguard-rules.pro` : 코드를 사람이 읽게 어렵게 난독화하는 기능을 합니다. 그래서 쉽게 조작할 수 없습니다.   
![image](https://user-images.githubusercontent.com/43658658/146668535-6d9070fc-544e-4fcd-be1f-82d9e619df17.png)



  -  

