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

## Activity

![image](https://user-images.githubusercontent.com/43658658/146669345-64a3f487-1d40-4907-aa48-dfab203f26c5.png)

Life Cycle(수명 주기)
* onCreate : activity가 만들어질 때 단 한 번만 호출
  - activity를 만들 때 단 한 번만 하면 되는 작업들을 여기서 해줍니다. 
* onStart
* onResume : 다시 앱으로 돌아올 때 무조건 호출
  - activity가 다시 호출될 때 하면 되는 작업들을 여기서 해줍니다. 
* onPause : 화면의 일부가 가려질 때 호출
* onStop : 화면이 아예 보이지 않을 때 호출
  - 사용자가 home 버튼을 눌러 잠시 앱을 나갈 때 호출. 
* onDestory

> <h3>실습</h3>

`MainActivity` 파일을 열고 `Override Methods`를 통해 `수명 주기`와 관련된 내용들을 불러옵니다.   
![image](https://user-images.githubusercontent.com/43658658/146669099-53e1cd7f-fb43-48cb-bc44-13455cf62bc3.png)   
* [코드에서 우클릭] > [Generate] > [Override Methods] > 키보드로 찾고 싶은 함수 검색.

`println`보다 `Log`를 사용해서 나중에 로그를 들여다보면서 체크하는 것이 좋습니다.   
![image](https://user-images.githubusercontent.com/43658658/146669208-9b4f67a0-c9cd-456d-a393-030275344edc.png)   
* `Log`를 사용하기 위해서는 먼저 `import`를 해줍니다.
* `Log.d(tag, message)` : tag에는 로그 메시지를 확인하기 위한 키워드를 적고, message는 로그 메시지를 작성합니다.

앱을 실행하고, 아래쪽에 `life_cycle`이라는 키워드로 검색하면 아래와 같이 메시지가 나옵니다.   
![image](https://user-images.githubusercontent.com/43658658/146669303-0deaf8f7-231b-47d4-83bb-04ab55434cbd.png)   
* 앱을 실행했으므로 수명 주기는 `onCreate`, `onStart`, `onResume`까지 호출되었습니다.

이제 앱에서 홈 버튼을 누르면 아래와 같이 수명 주기가 호출됩니다.   
![image](https://user-images.githubusercontent.com/43658658/146669329-421cb404-e6c9-4331-b89a-7fd2b2e7dfa0.png)

## Listener

익명함수 : 이름이 없는 함수/클래스

다음의 경로를 통해 Activity를 생성해줍니다.   
![image](https://user-images.githubusercontent.com/43658658/146669462-92d897a4-f070-436f-b7e6-7fa920e890c6.png)

`activity_layout`(Activity를 생성할 때 같이 만들어준 레이아웃 파일)을 열고, 아래와 같이 작성합니다.   
![image](https://user-images.githubusercontent.com/43658658/146669541-08e96be1-03a8-45bb-8943-96847b98ad0c.png)

다시 activity 페이지로 돌아와서 아래의 내용을 작성합니다.   
![image](https://user-images.githubusercontent.com/43658658/146670009-06a17803-2773-4c14-bff1-e8fea78ab723.png)   
* `Listener` : 페이지에서 어떤 Input이 있을 때 호출되는 함수입니다.
* `hello.setOnClickListener` : hello 뷰를 클릭했을 때 호출됩니다.

> <h3>뷰를 조작하는 함수들</h3>

![image](https://user-images.githubusercontent.com/43658658/146672347-a004afbf-6aa5-46c1-9712-5be9f47d821d.png)   
* `hello.setText` : hello 뷰의 텍스트를 변경합니다.
* `image.setImageResource` : image 뷰의 이미지 리소스를 변경합니다.

실제로 `Listener`는 전부 기억하지 않고 필요할 때마다 `자동완성` 기능을 통해 알맞은 기능을 찾아서 사용합니다.

## 더하기 계산기 과제

Q. 아래와 같은 UI로 더하기 계산기를 만들어봅니다.   
![image](https://user-images.githubusercontent.com/43658658/146672376-ab6c81f8-60c8-42bb-bb98-8dba2bf4178c.png)   
* `CA` : 초기화 기능
* 더하기를 누르기 전까지 숫자를 계속 입력할 수 있어야 합니다.

A. 코드 첨부(xml, kotlin)   
``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".plus_calculator">

    <TextView
        android:id="@+id/result"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#3D5AFE"
        android:textColor="@color/white"
        android:text="0"
        android:gravity="center|right"
        android:textSize="50dp"
        android:paddingRight="5dp"/>

    <!-- 첫 번째 줄 -->
    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">
        <TextView
            android:id="@+id/button1"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="1"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button2"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="2"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button3"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="3"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/buttonCA"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="CA"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#F50057"/>
    </LinearLayout>
    <!-- 두 번째 줄 -->
    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">
        <TextView
            android:id="@+id/button4"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="4"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button5"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="5"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button6"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="6"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/buttonPlus"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="+"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#F50057"/>
    </LinearLayout>
    <!-- 세 번째 줄 -->
    <LinearLayout
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:orientation="horizontal">
        <TextView
            android:id="@+id/button7"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="7"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button8"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="8"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button9"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="9"
            android:textColor="@color/white"
            android:gravity="center"
            android:textSize="50dp"
            android:background="#282828"/>
        <TextView
            android:id="@+id/button0"
            android:layout_weight="1"
            android:layout_width="0dp"
            android:layout_height="match_parent"
            android:text="0"
            android:textColor="@color/black"
            android:gravity="center"
            android:textSize="50dp"
            android:background="@color/white"/>
    </LinearLayout>

</LinearLayout>
```

``` kotlin
package com.example.myapplication2

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.TextView

class plus_calculator : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_plus_calculator)

        val result: TextView = findViewById(R.id.result)
        val button0: TextView = findViewById(R.id.button0)
        val button1: TextView = findViewById(R.id.button1)
        val button2: TextView = findViewById(R.id.button2)
        val button3: TextView = findViewById(R.id.button3)
        val button4: TextView = findViewById(R.id.button4)
        val button5: TextView = findViewById(R.id.button5)
        val button6: TextView = findViewById(R.id.button6)
        val button7: TextView = findViewById(R.id.button7)
        val button8: TextView = findViewById(R.id.button8)
        val button9: TextView = findViewById(R.id.button9)
        val buttonPlus: TextView = findViewById(R.id.buttonPlus)
        val buttonCA: TextView = findViewById(R.id.buttonCA)

        var hap: Int = 0
        var num: String = "0"

        result.setText(hap.toString()) // 초기 계산기 값은 0

        button1.setOnClickListener {
            num += "1"
            result.setText(num)
        }

        button2.setOnClickListener {
            num += "2"
            result.setText(num)
        }

        button3.setOnClickListener {
            num += "3"
            result.setText(num)
        }

        button4.setOnClickListener {
            num += "4"
            result.setText(num)
        }

        button5.setOnClickListener {
            num += "5"
            result.setText(num)
        }

        button6.setOnClickListener {
            num += "6"
            result.setText(num)
        }

        button7.setOnClickListener {
            num += "7"
            result.setText(num)
        }

        button8.setOnClickListener {
            num += "8"
            result.setText(num)
        }

        button9.setOnClickListener {
            num += "9"
            result.setText(num)
        }

        button0.setOnClickListener {
            num += "0"
            result.setText(num)
        }

        buttonPlus.setOnClickListener {
            hap += num.toInt()
            num = "0"
            result.setText(hap.toString())
        }

        buttonCA.setOnClickListener {
            num = "0"
            hap = 0
            result.setText(hap.toString())
        }
    }
}
```

## Intent

: 의도, 요구, 의사 전달, 요청   
: 요청 관계   
- Activity와 Activity
- Android System과 내 App (전화)
- 다른 App과 내 App -> 무작정 할 수 없고, 상호합의가 있어야 합니다.

: 요청의 종류   
- 전달만 하는 요청
- 리턴을 받는 요청

> <h3>Activity와 Activity 간 이동</h3>

먼저 `Intent1`, `Intent2` 액티비티를 만들어줍니다.   

Intent1 - xml  
``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".Intent1">

    <Button
        android:id="@+id/change_activity"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:text="인텐트"/>


</LinearLayout>
```

Intent1 - kt    
``` kotlin
package com.example.myapplication2

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button

class Intent1 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent)

        val change_activity: Button = findViewById(R.id.change_activity)
        change_activity.setOnClickListener {
            val intent = Intent(this@Intent1, Intent2::class.java)
            startActivity(intent)
        }
    }
}
```

* Intent를 사용할 때 꼭 형식을 `Intent(this@현재액티비티, 이동할액티비티::class.java)` 형식으로 사용합니다.
* 꼭 startActivity를 통해 intent를 `전달만 하는 요청`으로 보냅니다.

`Intent1`을 실행하고, `Button`을 누르면 `Intent2`로 이동합니다.   
![image](https://user-images.githubusercontent.com/43658658/146673642-5806b633-27a4-4b0c-9be2-fd110fc0b8e3.png)   
![image](https://user-images.githubusercontent.com/43658658/146673647-1d89fcd1-5b54-4d95-bf48-7b2bb0a78037.png)   
* Intent2는 검은 화면입니다.
* 뒤로 가기를 하면 다시 Intent1으로 넘어옵니다.

`putExtra`를 이용해서 액티비티 사이에 값을 넘겨줄 수도 있습니다.   

Intent1 - kotlin   
``` kotlin
package com.example.myapplication2

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button

class Intent1 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent)

        val change_activity: Button = findViewById(R.id.change_activity)
        change_activity.setOnClickListener {
            val intent = Intent(this@Intent1, Intent2::class.java)

            // Key, Value 방식 -> key와 value를 쌍으로 만들어 저장한다. -> Dictionary
            // Apply -> intent2를 this로 적어줄 수 있는데, 나중에 코드가 복잡해질 때 정리하기 좋습니다.
            intent.apply {
                this.putExtra("number1", 1)
                this.putExtra("number2", 2)
            }
            startActivity(intent)
        }
    }
}
```

Intent2 - kotlin   
``` kotlin
package com.example.myapplication2

import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log

class Intent2 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent2)

        val number1 = intent.getIntExtra("number1", 0)
        val number2 = intent.getIntExtra("number",0)

        Log.d("number", ""+number1)
        Log.d("number", ""+number2)
    }
}
```

값을 줄 때는 `putExtra` 값을 받을 때는 `getIntExtra`   
* `putExtra(name, value)` : 넘겨줄 값과 값을 지칭하는 이름을 지정합니다.
* `getIntExtra(name, default)` : 넘어온 값

실행하고 Intent1의 버튼을 클릭하면, Intent2로 값이 넘어가서 로그로 남습니다.   
![image](https://user-images.githubusercontent.com/43658658/146674166-27e73b79-d490-4e83-be9e-f22811e10123.png)

Intent2에서 다시 Intent1으로 결과를 넘겨보겠습니다.   

Intent2 - xml   
``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/black"
    tools:context=".Intent2">

    <Button
        android:id="@+id/result"
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:text="결과" />


</LinearLayout>
```

Intent2 - kotlin   
``` kotlin
package com.example.myapplication2

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import android.widget.Button

class Intent2 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent2)

        val result: Button = findViewById(R.id.result)

        result.setOnClickListener {
            val number1 = intent.getIntExtra("number1", 0)
            val number2 = intent.getIntExtra("number", 0)

            Log.d("number", "" + number1)
            Log.d("number", "" + number2)

            val resultSum = number1 + number2
            val resultIntent = Intent()
            resultIntent.putExtra("result", resultSum)
            setResult(-1, resultIntent)
            finish() // Activity 종료

        }
    }
}
```

* `Intent2`에서 `Intent1`으로 `number1+number2`의 값을 넘깁니다.
* 넘길 때는 `Intent()`로 현재 액티비티와 이동할 액티비티를 명시해주지 않아도 됩니다.
* `setResult(resultCode, returnValue)` : 리턴값을 넣어주는 함수입니다. `Intent1`에서 `onActivityResult` 함수와 연계됩니다.
  - resultCode `-1` : 정상
  - resultCode `0` : 취소
* finish() : Activity를 종료합니다.
  - Activity는 Stack 개념입니다. 맨 처음에 실행하면 Intent1이 쌓이고, Intent를 통해 Intent2 Activity가 위에 쌓입니다.

이제 `리턴을 받는 요청`과 함께 `Intent2`에서 보낸 결괏값을 받아보겠습니다.   
결과를 받기 위해서는 애초에 `Intent1` 액티비티에서 요청을 보낼 때 `전달만 하는 요청(startActivity)`가 아닌 `리턴을 받는 요청(startActivityForResult)`로 보내야합니다.

Intent1 - kotlin   
``` kotlin
package com.example.myapplication2

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import android.widget.Button

class Intent1 : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_intent)

        val change_activity: Button = findViewById(R.id.change_activity)
        change_activity.setOnClickListener {
            val intent = Intent(this@Intent1, Intent2::class.java)

            // Key, Value 방식 -> key와 value를 쌍으로 만들어 저장한다. -> Dictionary
            // apply -> intent2를 this로 적어줄 수 있는데, 나중에 코드가 복잡해질 때 정리하기 좋습니다.
            intent.apply {
                this.putExtra("number1", 1)
                this.putExtra("number2", 2)
            }
            startActivityForResult(intent, 200)
        }
    }

    override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {
        if (requestCode == 200) { // intent1이 보낸 요청이 맞는지 확인
            Log.d("number", "" + requestCode)
            Log.d("number", "" + resultCode)
            val result = data?.getIntExtra("result", 0)
            Log.d("number", "" + result)
        }
        super.onActivityResult(requestCode, resultCode, data)
    }
}
```

* `startActivityForResult(intent, requestCode)` : `리턴을 받는 요청`을 할 때 사용합니다.
* `onActivityResult` : 리턴값을 처리할 때 이용하는 override 함수입니다.
* `val result = data?.getIntExtra("result", 0)` : 리턴값을 받습니다.

`Intent2`에서 `결과` 버튼을 클릭하면 리턴값을 `Intent1`으로 보냅니다.   
`Intent1`이 `Intent2`에서 결괏값을 받았을 때, 보낸 요청이 맞다면(requestCode 확인) 로그를 남깁니다.
![image](https://user-images.githubusercontent.com/43658658/146675346-e5f6edd5-45ba-4aba-97e5-256697c117e7.png)

> <h3>암시적 인텐트</h3>

: 버튼을 클릭하면 특정 인터넷 페이지를 여는 인텐트

``` kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_intent)

    val change_activity: Button = findViewById(R.id.change_activity)
    change_activity.setOnClickListener {
        val intent = Intent(Intent.ACTION_VIEW, Uri.parse("http://m.naver.com"))
        startActivity(intent)
    }
}
```    

## Task

액티비티의 스택을 커스터마이징 하기 위해서는 `LaunchMode`와 `IntentFlag`라는 두 가지 기능이 있습니다.

하지만 이 두 기능은 완벽하게 숙지하지 않으면 사용하지 않는 것이 좋습니다.   
기본적으로 설정된 스택이 꼬이기 시작하면 굉장히 복잡해지기 때문입니다.

안드로이드 스튜디오 공식 문서를 이용해 정확히 숙지를 하고 이용하시기 바랍니다.

기본적으로 `스택 커스터마이징`은 `잘 건드리지 않는 부분`입니다.   
꼭 필요할 때 사용합니다.

## 인터넷 페이지 열기 과제

Q. URL을 입력하고 `인터넷 페이지 이동` 버튼을 누르면 해당 인터넷 페이지로 이동하는 페이지를 만드세요.   
![image](https://user-images.githubusercontent.com/43658658/146677297-63600cbf-7988-4c02-bae2-d4b8c04bea17.png)   
* `EditText` 뷰를 이용합니다.
* `EditText` 뷰에는 텍스트를 입력할 때마다 호출되는 리스너 함수가 있습니다.

A.   

``` xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".Internet_page_open"
    android:padding="10dp">

    <EditText
        android:id="@+id/url"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="인터넷 주소를 입력해주세요" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="인터넷 페이지 열기"/>


</LinearLayout>
```

``` kotlin
package com.example.myapplication2

import android.content.Intent
import android.net.Uri
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.text.Editable
import android.text.TextWatcher
import android.util.Log
import android.widget.Button
import android.widget.EditText

class Internet_page_open : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_internet_page_open)

        val url: EditText = findViewById(R.id.url)
        val button: Button = findViewById(R.id.button)

        button.setOnClickListener {
            val intent = Intent(Intent.ACTION_VIEW, Uri.parse(url.text.toString()))
            startActivity(intent)
        }

        url.addTextChangedListener(object : TextWatcher {
            override fun beforeTextChanged(s: CharSequence?, start: Int, count: Int, after: Int) {
                Log.d("edit", "beforeTextChanged" + s)
            }

            override fun onTextChanged(s: CharSequence?, start: Int, before: Int, count: Int) {
                Log.d("edit", "onTextChanged" + s)
            }

            override fun afterTextChanged(s: Editable?) {
                Log.d("edit", "afterTextChanged" + s)
            }
        })
    }
}
```

* `Uri.parse(url.text.toString)` : editText 뷰의 text 속성을 불러올 때 문자열로 바꿔주어야합니다.
* `addTextChangedListener` : 텍스트가 변화할 때 마다 호출되는 리스너입니다.   
![image](https://user-images.githubusercontent.com/43658658/146677326-bb44d518-4d4c-443a-be65-13a1ab09dd94.png)


