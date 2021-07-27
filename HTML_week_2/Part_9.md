# Part 9. HTML5 멀티미디어

+ [멀티미디어 파일 형식](#멀티미디어-파일-형식)
+ [비디오(video)](#비디오video)
+ 

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
