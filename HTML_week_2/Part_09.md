# Part 9. HTML5 멀티미디어

+ [멀티미디어 파일 형식](#멀티미디어-파일-형식)
+ [비디오(video)](#비디오video)
+ [오디오(audio)](#오디오audio)
+ [플러그인(Plug-in)](#플러그인Plugin)

## 멀티미디어 파일 형식

HTML5 이전까지는 웹 브라우저마다 어떤 종류의 멀티미디어 파일을 지원할지 각자 다른 방식으로 처리해 왔습니다.

하지만 HTML5에서는 플래시와 같은 외부 플러그인의 도움 없이도 멀티미디어 파일을 간단히 사용할 수 있게 되었습니다.

웹 브라우저는 파일의 타입(type)을 파일의 확장자로 판단합니다.

만약에 확장자가 .html인 파일을 보면, 웹 브라우저는 이 파일을 HTML 파일로써 다루게 될 것입니다.

비디오(video)나 사운드(sound)와 같은 멀티미디어 요소들은 멀티미디어 파일에 저장됩니다.

이와 같은 멀티미디어 파일도 다음과 같이 다양한 파일 형식으로 저장될 수 있습니다.

> <h3>비디오(video) 파일 형식</h3>

대표적인 비디오 파일 형식은 다음과 같습니다.

HTML5 표준이 공식적으로 지원하는 비디오 파일 형식은 **MP4, WebM, OGV** 뿐입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 80px;">파일 형식</th>
			<th style="width: 80px;">파일 확장자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>MPEG</td>
			<td style="text-align: center;">.mpg .mpeg</td>
			<td>Moving Picture Experts Group에 의해 개발되었으며, 변환 코덱을 이용하는 손실 압축 방식을 사용함.</td>
		</tr>
		<tr>
			<td>MP4</td>
			<td style="text-align: center;">.mp4</td>
			<td>Moving Picture Experts Group에 의해 개발되었으며, 적은 용량으로도 고품질의 영상 및 음성을 구현할 수 있어서 인터넷을 통한 스트리밍에 자주 활용됨.</td>
		</tr>
		<tr>
			<td>OGV</td>
			<td style="text-align: center;">.ogg</td>
			<td>Xiph 재단에 의해 개발되었으며, MP3의 대안으로 개발된 특허권으로 보호되지 않는 개방형 공개 멀티미디어 파일 형식임.</td>
		</tr>
		<tr>
			<td>WebM</td>
			<td style="text-align: center;">.webm</td>
			<td>구글의 지원으로 개발된 개방형 공개 멀티미디어 파일 형식으로, 비디오 코덱으로는 VP8, 오디오 코덱으로는 Vorbis를 사용하는 멀티미디어 파일 형식임.</td>
		</tr>
		<tr>
			<td>AVI</td>
			<td style="text-align: center;">.avi</td>
			<td>Microsoft에 의해 개발되었으며, PC에서 동영상을 구현하기 위한 파일 형식임.</td>
		</tr>
		<tr>
			<td>WMV</td>
			<td style="text-align: center;">.wmv</td>
			<td>Microsoft에 의해 개발되었으며, Microsoft windows media player의 주 스트리밍 파일 형식임.</td>
		</tr>
		<tr>
			<td>QuickTime</td>
			<td style="text-align: center;">.mov</td>
			<td>Apple에 의해 개발되었으며, 매킨토시 컴퓨터에 동영상을 지원하기 위하여 개발된 파일 형식임.</td>
		</tr>
		<tr>
			<td>RealVideo</td>
			<td style="text-align: center;">.rm .ram</td>
			<td>Real Networks에 의해 개발되었으며, 스트리밍 기술을 이용한 동영상용 플러그 인 파일 형식임.</td>
		</tr>
		<tr>
			<td>Flash</td>
			<td style="text-align: center;">.swf .flv</td>
			<td>Macromedia에 의해 개발되었으며, 벡터 도형 처리 기반의 애니메이션 제작용 소프트웨어 파일 형식임.</td>
		</tr>
	</tbody>
</table>

> <h3>오디오(audio) 파일 형식</h3>

대표적인 오디오 파일 형식은 다음과 같습니다.

HTML5 표준이 공식적으로 지원하는 오디오 파일 형식은 MP3, WAV, Ogg 뿐입니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th style="width: 80px;">파일 형식</th>
			<th style="width: 80px;">파일 확장자</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
      <td><mark>WAV</mark></td>
			<td style="text-align: center;">.wav</td>
			<td>IBM과 Microsoft에 의해 개발되었으며, 개인용 PC에서 오디오를 재생하기 위한 IBM과 Microsoft의 표준 오디오 파일&nbsp;형식임.</td>
		</tr>
		<tr>
			<td>Ogg</td>
			<td style="text-align: center;">.ogg</td>
			<td>Xiph 재단에 의해 개발되었으며, MP3의 대안으로 개발된 특허권으로 보호되지 않는 개방형 공개 멀티미디어 파일 형식임.</td>
		</tr>
		<tr>
			<td>MP3</td>
			<td style="text-align: center;">.mp3</td>
			<td>Moving Picture Experts Group에 의해 개발되었으며, MPEG-1의 오디오 규격으로 개발된 손실 압축 파일 형식임.</td>
		</tr>
		<tr>
			<td>MP4</td>
			<td style="text-align: center;">.mp4</td>
			<td>Moving Picture Experts Group에 의해 개발되었으며, MPEG-4의 일부로 규정된 멀티미디어 컨테이너 파일 형식임. MP4는 비디오 파일 형식이기도 하지만 오디오에서도 사용할 수 있음.&nbsp;</td>
		</tr>
		<tr>
			<td>MIDI</td>
			<td style="text-align: center;">.mid .midi</td>
			<td>모든 전자 음악기기의 연주 정보를 상호 전달하기 위해 정해진 데이터 전송 규격임.</td>
		</tr>
		<tr>
			<td>RealAudio</td>
			<td style="text-align: center;">.rm .ram</td>
			<td>Real Networks에 의해 개발되었으며, 인터넷에서 실시간으로 음악을 들을 수 있는 스트리밍 사운드 기술임.</td>
		</tr>
		<tr>
			<td>WMA</td>
			<td style="text-align: center;">.wma</td>
			<td>Microsoft에 의해 개발되었으며, Microsoft windows media 기술에서 음악 정보(data)만을 압축하는 기술임.</td>
		</tr>
		<tr>
			<td>AAC</td>
			<td style="text-align: center;">.aac</td>
			<td>Apple에 의해 개발되었으며, iPhone, iPod, iTunes의 기본 오디오 파일 형식임. 표준적인 손실 압축 방식을 사용함.</td>
		</tr>
	</tbody>
</table>

## 비디오(video)

HTML5 이전에는 웹 페이지에서 비디오(video)를 보여주기 위한 표준안이 없었습니다.

따라서 비디오를 삽입하기 위해서는 플래시(flash)와 같은 외부 플러그인(plug-in)에 의존해야만 했습니다.

하지만 HTML5에서는 `<video>`태그를 이용하여 웹 페이지에 비디오를 삽입하는 표준화된 방식을 제공합니다.

> <h3>HTML5 비디오 파일 형식</h3>

HTML5 표준이 공식적으로 지원하는 비디오 파일 형식은 MP4, WebM, OGV 뿐입니다.

- MP4 : Moving Picture Experts Group에 의해 개발되었으며, 비디오 코덱으로는 H.268, 오디오 코덱으로는 ACC를 사용합니다. 적은 용량으로도 고품질의 영상 및 음성을 구현할 수 있어 인터넷을 통한 스트리밍에 많이 활용되는 파일 형식입니다.
- WebM : 구글의 지원으로 개발된 개방형 공개 멀티미디어 파일 형식이며, 비디오 코덱으로는 VP8, 오디오 코덱으로는 Vorbis를 사용합니다.
- OGV : Theora Ogg라고도 불리며, Xiph 재단에 의해 MP3의 대안으로 개발된 특허권으로 보호되지 않는 개방형 공개 멀티미디어 파일 형식입니다. 비디오 코덱으로는 Theora, 오디오 코덱으로는 Vorbis를 사용합니다.

HTML5 비디오 파일 형식별 주요 웹 브라우저의 지원 여부는 다음 표와 같습니다.

<table class="tb-1" summary="">
	<tbody>
		<tr>
			<th style="width: 150px;">파일 형식</th>
			<th style="width: 15%;">미디어 타입</th>
			<th>ie</th>
			<th>chrome</th>
			<th>firefox</th>
			<th>safari</th>
			<th>opera</th>
		</tr>
		<tr>
			<td>MP4</td>
			<td>video/mp4</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
		</tr>
		<tr>
			<td>WebM</td>
			<td>video/webm</td>
			<td>&Chi;</td>
			<td>○</td>
			<td>○</td>
			<td>&Chi;</td>
			<td>○</td>
		</tr>
		<tr>
			<td>OGV</td>
			<td>video/ogg</td>
			<td>&Chi;</td>
			<td>○</td>
			<td>○</td>
			<td>&Chi;</td>
			<td>○</td>
		</tr>
	</tbody>
</table>

> <h3>controls 속성</h3>

재생, 정지 및 소리의 조절 등 비디오의 기본적인 동작을 조절할 수 있는 패널을 생성합니다.

![image](https://user-images.githubusercontent.com/43658658/127112676-95d77ad3-4be6-414d-a5ac-aea05b2e4dae.png)

> <h3>height, width 속성</h3>

height와 width 속성을 통해 비디오의 크기를 조절할 수 있습니다.

style 속성을 통해 CSS로 조절할 수도 있습니다.

> <h3>source 태그와 지원하지 않을 때의 출력 문자</h3>

`<video>`태그 내에 `<source>`태그를 이용하여 원하는 비디오를 가져올 수 있습니다.

src 속성을 이용해 "위치"를 알려주고 type 속성을 이용해 "멀티미디어의 종류/확장자"를 알려줍니다.

웹 브라우저는 여러 개의 `<source>`태그 중 위쪽에서부터 순서대로 가장 먼저 인식되는 파일의 타입과 주소를 사용합니다.

`<video>`태그 사이에 존재하는 ***텍스트***는 해당 웹 브라우저가 `<video>`태그를 지원하지 않을 때만 화면에 표시됩니다.

``` html
<h1><mark style="background-color:lightgreen; ">video 요소</mark>를 이용한 동영상 삽입</h1>
<video height="360" width="576" controls>
	<source src="/examples/media/sample_video_mp4.mp4" type="video/mp4">
	<source src="/examples/media/sample_video_ogg.ogg" type="video/ogg">
	이 문장은 사용자의 웹 브라우저가 video 요소를 지원하지 않을 때 나타납니다!
</video>
```

![image](https://user-images.githubusercontent.com/43658658/127113256-e885a9c9-e257-4764-bce5-8a67f2551c05.png)

> <h3>autoplay 속성</h3>

autoplay 속성은 웹 페이지가 로드(load) 될 때 비디오를 자동으로 재생시켜 줄지 않을지를 설정합니다.

``` html
<h1><mark style="background-color:lightgreen; ">video 요소</mark>를 이용한 동영상 삽입</h1>
<video height="360" width="576" controls autoplay>
	<source src="/examples/media/sample_video_mp4.mp4" type="video/mp4">
	<source src="/examples/media/sample_video_ogg.ogg" type="video/ogg">
	이 문장은 사용자의 웹 브라우저가 video 요소를 지원하지 않을 때 나타납니다!
</video>
```

> <h3>loop 속성</h3>

loop 속성을 설정하면, 비디오의 재생이 끝나도 계속적으로 반복해서 비디오를 재생합니다.

``` html
<h1><mark style="background-color:lightgreen; ">video 요소</mark>를 이용한 동영상 삽입</h1>
<video height="360" width="576" controls loop>
	<source src="/examples/media/sample_video_mp4.mp4" type="video/mp4">
	<source src="/examples/media/sample_video_ogg.ogg" type="video/ogg">
	이 문장은 사용자의 웹 브라우저가 video 요소를 지원하지 않을 때 나타납니다!
</video>
```

> <h3>track 태그</h3>

`<track>`태그는 비디오가 재생될 때 보일 자막이나 캡션 파일을 명시할 때 사용합니다.

``` html
<video style="width:576; height:360" controls>
    <source src="/examples/media/sample_video_mp4.mp4" type="video/mp4">
    <source src="/examples/media/sample_video_ogg.ogg" type="video/ogg">
    <track kind="subtitles" src="sample_subtitle_en.vtt" srclang="en" label="English">
    <track kind="subtitles" src="sample_subtitle_fr.vtt" srclang="fr" label="Francais">
    이 문장은 사용자의 웹 브라우저가 video 요소를 지원하지 않을 때 나타납니다!
</video>
```

kind 속성은 자막 문자열의 타입을 명시합니다.

srclang 속성은 해당 문자열의 언어 설정을 명시합니다.

label 속성은 사용자가 보게 될 라벨을 명시합니다.

> <h3>poster 속성</h3>

poster 속성은 비디오가 로딩중일 때 나타낼 이미지를 나타냅니다.

``` html
<video width="320" height="240" poster="/images/w3schools_green.jpg" controls>
   <source src="movie.mp4" type="video/mp4">
   <source src="movie.ogg" type="video/ogg">
   Your browser does not support the video tag.
</video>
```

![image](https://user-images.githubusercontent.com/43658658/127114401-dab20f14-a39e-43ba-8e12-4453e89dfc22.png)

> <h3>preload 속성</h3>

preload 속성은 페이지가 나타나고 비디오라 로드될 때 비디오의 모든 내용을 사전에 로드할 것인가에 대한 선택을 할 수 있습니다.

속성값은 3가지입니다.

- auto : 페이지가 로드될 때 비디오의 전체 내용을 사전에 로드합니다.
- metadata : 페이지가 로드될 때 비디오의 메타데이터만 사전에 로드합니다.
- none : 페이지가 로드될 때 비디오의 전체 내용을 사전에 로드하지 않습니다.

``` html
<video width="320" height="240" controls preload="none">
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  Your browser does not support the video tag.
</video>
```

> <h4>HTML5 video 요소</h4>

비디오에 쓰이는 요소들을 정리하면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>요소</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>video</td>
			<td>비디오와 영화 등 비디오 파일을 명시함.</td>
		</tr>
		<tr>
			<td>source</td>
			<td>
			<p>video 요소의 원본 파일에 대한 파일 형식 및 파일 주소를 여러 개 명시함.<br>
			웹 브라우저는 위쪽에서부터 순서대로 가장 먼저 인식되는 파일&nbsp;형식과 파일&nbsp;주소를 사용함.</p>
			</td>
		</tr>
		<tr>
			<td>track</td>
			<td>비디오 플레이어에 대한 텍스트 자막을 명시함.</td>
		</tr>
	</tbody>
</table>

> <h4>HTML5 video 속성</h4>

`<video>`태그에 쓰이는 속성들을 다시 한 번 정리하면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>src</td>
			<td>비디오 파일의 경로를 명시함.</td>
		</tr>
		<tr>
			<td>height</td>
			<td>
			<p>비디오 파일의 높이를 명시함.</p>
			</td>
		</tr>
		<tr>
			<td>width</td>
			<td>비디오 파일의 너비를 명시함.</td>
		</tr>
		<tr>
			<td>controls</td>
			<td>비디오의 기본적인 동작을 조절할 수 있는 패널를 명시함.</td>
		</tr>
		<tr>
			<td>autoplay</td>
			<td>비디오의 자동 재생 여부를 명시함.</td>
		</tr>
		<tr>
			<td>loop</td>
			<td>비디오의 반복 재생 여부를 명시함.</td>
		</tr>
		<tr>
			<td>poster</td>
			<td>비디오가 아직 준비 중일때 불러올 이미지 파일의 경로를 명시함.</td>
		</tr>
		<tr>
			<td>preload</td>
			<td>비디오를 재생하기 전에 파일의 내용을 모두 불러올지를 명시함.</td>
		</tr>
	</tbody>
</table>

## 오디오(audio)

> <h3>오디오(audio) 요소</h3>

HTML5 이전에는 웹 페이지에서 오디오(audio)를 들려주기 위한 표준안이 없었습니다.

따라서 비디오를 삽입하기 위해서는 플래시(flash)와 같은 외부 플러그인(plug-in)에 의존해야만 했습니다.

하지만 HTML5에서는 `<audio>`태그를 이용하여 웹 페이지에 오디오를 삽입하는 표준화된 방식을 제공합니다.

`<audio>`태그를 지원하는 주요 웹 브라우저의 버전은 다음과 같습니다.

<table class="tb-1" summary="">
	<tbody>
		<tr>
			<th style="width: 150px;">요소</th>
			<th>ie</th>
			<th>chrome</th>
			<th>firefox</th>
			<th>safari</th>
			<th>opera</th>
		</tr>
		<tr>
			<td>&lt;audio&gt;태그</td>
			<td>9.0</td>
			<td>4.0</td>
			<td>3.5</td>
			<td>4.0</td>
			<td>10.5</td>
		</tr>
	</tbody>
</table>

> <h3>HTML5 오디오 파일 형식</h3>

HTML5 표준이 공식적으로 지원하는 오디오 파일 형식은 MP3, WAV, Ogg 뿐입니다.

- MP3 : Moving Picture Experts Group에 의해 개발되었으며, MPEG-1의 오디오 규격으로 개발된 손실 압축형 파일 형식입니다.
- WAV : IBM과 Microsoft에 의해 개발되었으며, 개인용 PC에서 오디오를 재생하기 위한 IBM과 Microsoft의 표준 오디오 파일 형식입니다.
- Ogg : Xiph 재단에 의해 개발되었으며, MP3의 대안으로 개발된 특허권으로 보호되지 않는 개방형 공개 멀티미디어 파일 형식입니다.

HTML5 오디오 파일 형식별 주요 웹 브라우저의 지원 여부는 다음 표와 같습니다.

<table class="tb-1" summary="">
	<tbody>
		<tr>
			<th style="width: 150px;">파일 형식</th>
			<th style="width: 15%;">
			<p>미디어 타입</p>
			</th>
			<th>ie</th>
			<th>chrome</th>
			<th>firefox</th>
			<th>safari</th>
			<th>opera</th>
		</tr>
		<tr>
			<td>MP3</td>
			<td>audio/mp3</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
		</tr>
		<tr>
			<td>WAV</td>
			<td>audio/wav</td>
			<td>&Chi;</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
			<td>○</td>
		</tr>
		<tr>
			<td>Ogg</td>
			<td>audio/ogg</td>
			<td>&Chi;</td>
			<td>○</td>
			<td>○</td>
			<td>&Chi;</td>
			<td>○</td>
		</tr>
	</tbody>
</table>

> <h3>source 태그</h3>

`<video>`와 마찬가지로 `<source>`태그를 이용해 오디오 파일을 불러올 수 있습니다.

src 속성을 이용해 "위치"를 알려주고, type 속성을 통해 "멀티미디어 종류/확장자"를 알려줍니다.

웹 브라우저는 여러 개의 `<source>`태그 중 위쪽에서부터 순서대로 가장 먼저 인식되는 파일의 타입과 주소를 사용합니다.

`<audio>`태그 사이에 존재하는 텍스트는 해당 웹 브라우저가 `<audio>`태그를 지원하지 않을 때만 화면에 표시됩니다.

> <h3>controls 속성</h3>

control 속성은 재생, 정지 및 소리의 조절 등 오디오의 기본적인 동작을 조절할 수 있는 패널을 생성합니다.

``` html
<h1>audio 요소를 이용한 소리 삽입</h1>
<audio controls>
	<source src="/examples/media/sample_audio_ogg.ogg" type="audio/ogg">
	<source src="/examples/media/sample_audio_mp3.mp3" type="audio/mp3">
	이 문장은 사용자의 웹 브라우저가 audio 요소를 지원하지 않을 때 나타납니다!
</audio>
```

![image](https://user-images.githubusercontent.com/43658658/127120193-0e072f1e-8309-4f5d-a03c-df3f36aa11dc.png)

> <h3>autoplay 속성</h3>

autoplay 속성은 웹 페이지가 로드(load) 될 때 음악을 자동으로 재생시켜 줄지 않을지를 설정합니다.

``` html
<h1>audio 요소를 이용한 소리 삽입</h1>
<audio controls autoplay>
	<source src="/examples/media/sample_audio_ogg.ogg" type="audio/ogg">
	<source src="/examples/media/sample_audio_mp3.mp3" type="audio/mp3">
	이 문장은 사용자의 웹 브라우저가 audio 요소를 지원하지 않을 때 나타납니다!
</audio>
```

> <h3>loop 속성</h3>

loop 속성을 설정하면 오디오의 재생이 끝나도 계속적으로 반복해서 오디오를 재생합니다.

``` html
<h1>audio 요소를 이용한 소리 삽입</h1>
<audio controls loop>
	<source src="/examples/media/sample_audio_ogg.ogg" type="audio/ogg">
	<source src="/examples/media/sample_audio_mp3.mp3" type="audio/mp3">
	이 문장은 사용자의 웹 브라우저가 audio 요소를 지원하지 않을 때 나타납니다!
</audio>
```

> <h3>preload 속성</h3>

preload 속성은 페이지가 나타나고 비디오라 로드될 때 비디오의 모든 내용을 사전에 로드할 것인가에 대한 선택을 할 수 있습니다.

속성값은 3가지입니다.

- auto : 페이지가 로드될 때 비디오의 전체 내용을 사전에 로드합니다.
- metadata : 페이지가 로드될 때 비디오의 메타데이터만 사전에 로드합니다.
- none : 페이지가 로드될 때 비디오의 전체 내용을 사전에 로드하지 않습니다.

``` html
<audio controls preload="none">
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

> <h3>HTML5 audio 요소</h3>

오디오 요소에서 활용될 수 있는 태그들은 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>요소</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>audio</td>
			<td>오디오와 음악 등 오디오 파일을 명시함.</td>
		</tr>
		<tr>
			<td>source</td>
			<td>
			<p>audio 요소의 원본 파일에 대한 파일 형식 및 파일&nbsp;주소를 여러 개 명시함.<br>
			웹 브라우저는 위쪽에서부터 순서대로 가장 먼저 인식되는 파일&nbsp;형식과 파일&nbsp;주소를 사용함.</p>
			</td>
		</tr>
	</tbody>
</table>

> <h3>HTML5 audio 속성</h3>

`<audio>`태그에서 사용되는 속성들을 다시 한 번 정리하면 아래와 같습니다.

<table class="tb-2" summary="">
	<thead>
		<tr class="bg">
			<th>속성</th>
			<th>설명</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>src</td>
			<td>오디오 파일의 경로를 명시함.</td>
		</tr>
		<tr>
			<td>controls</td>
			<td>
			<p>오디오의 기본적인 동작을 조절할 수 있는 패널를 명시함.</p>
			</td>
		</tr>
		<tr>
			<td>autoplay</td>
			<td>오디오의 자동 재생 여부를 명시함.</td>
		</tr>
		<tr>
			<td>loop</td>
			<td>오디오의 반복 재생 여부를 명시함.</td>
		</tr>
		<tr>
			<td>preload</td>
			<td>오디오를 재생하기 전에 파일의 내용을 모두 불러올지를 명시함.</td>
		</tr>
	</tbody>
</table>

## 플러그인(Plugin)

HTML 플러그인이란 웹 브라우저의 표준 기능을 확장해 주는 프로그램을 의미합니다.

가장 널리 알려진 플러그인으로는 Java Applet, Flash Player, Pdf Reader 등이 있습니다.

이러한 플러그인은 object 요소나 embed 요소를 사용하여 HTML 문서에 추가할 수 있습니다.

> <h3>object 요소</h3>

object 요소는 HTML 문서에 삽입할 객체(object)를 명시하는데 사용합니다.

이 요소는 모든 웹 브라우저에서 동작하며, 객체뿐만 아니라 또 다른 HTML 문서를 삽입할 수도 있습니다.

파일의 경로를 data를 이용해 입력합니다.

``` html
<h1>object 요소를 이용한 pdf 파일 삽입</h1>
<object data="/examples/media/sample_plugins_pdf.pdf" style="width:100%; height:700px"></object>
```

![image](https://user-images.githubusercontent.com/43658658/127123857-383baf46-04a4-4c52-b22b-b881833466ed.png)

또한, object 요소는 이미지를 삽입할 때에도 사용할 수 있습니다.

``` html
<object data="/examples/images/img_flower.png"></object>
```

![image](https://user-images.githubusercontent.com/43658658/127124132-a4c63da5-c614-4fda-b14f-1aab16bfa9b8.png)

> <h3>embed 요소</h3>

embed 요소는 HTML 문서에 삽입할 객체(object)를 명시하는데 사용합니다.

embed 요소는 오래전부터 사용되어 왔지만, HTML5 이전까지는 HTML 표준이 아니었습니다.

이 요소는 모든 웹 브라우저에서 동작하며, 객체뿐만 아니라 HTML 문서를 삽입할 수도 있습니다.

```
<embed src="/examples/media/sample_plugins_pdf.pdf" style="width:100%; height:700px">
```

또한, embed 요소는 이미지를 삽입할 때에도 사용할 수 있습니다.

```
<embed src="/examples/images/img_flower.jpg" style="width:350px; height:263px">
```

embed 요소는 HTML5 이전까지는 HTML 표준이 아니었으므로, HTML5에서는 유효하지만, **HTML4에서는 유효하지 않습니다.**

object와 용도가 같습니다. 다만 파일 경로를 입력할 때 속성이 **data 또는 src**인 것이 다른 부분입니다.
