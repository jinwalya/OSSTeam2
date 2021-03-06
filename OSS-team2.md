Ubuntu 16.04 사용법
============================
**우**리들의 **분**수에 맞는 **투**박한 프로젝트
잘부탁드립니다:)


>[2조]
>>조장 
>>20154274 엄의진

>>조원
>>20154212 윤소영 
>>20154233 김주효


------------------------------

# 목차


#### 1. 선정 동기
#### 2. 기능 설명
* ##### 2.1. ubuntu software
* ##### 2.2. 네트워크 유-무선 공유
* ##### 2.3. unity 런처 이동
* ##### 2.4. apt 명령어 간소화
* ##### 2.5. Libre office
#### 3. 불편사항 및 개선
#### 4. 소감
#### 5. 참고


-------------------------------


# 1. 선정 동기

많은 오픈소스SW 중에 우분투를 선택하게 된 이유는 일단 저희가 수업에서 쓰는 OS이기 때문입니다. 평소 'Microsoft' 의 'Windows' 운영체제만 써왔고 그것에 익숙해져 있다보니 수업 외에 우분투를 사용할 일이 많지 않습니다. 또한 실상 사용하려해도 수업에서 다룬 'Terminal' 프로그램만 사용할 뿐 우분투의 다른 기능들을 사용해보지 않았습니다. 그렇기 때문에 이번 기회를 통해 가장 가까이 있지만 멀게 느껴졌던 '우분투'를 하나하나 살펴보며 'Windows' 에서 보지 못했던 기능이나 우분투의 특징적인 기능들을 몇 가지 뽑아 그 사용법을 소개하며 저희도 공부하는 시간이 되기 위해 우분투를 선정하게 되었습니다.

이 문서를 통해 열심히 검색하고 공부하며 **우**리들의 **분**수에 맞는 **투**박한 프로젝트를 시작합니다.


# 2. 기능 설명

#### 2.1.  Ubuntu Software
이 기능은 'Windows 10'에서 볼 수 있는 '앱 스토어'와 비슷한 기능입니다. 우분투는 Terminal로 명령어를 통해 어떤 프로그램을 설치할 수 있습니다. 이때는 사용자가 필요로하는 프로그램의 이름과 경로를 알아야하는데 'Ubuntu Software' 를 이용하면 굳이 명령어를 쓸 필요없이 간단하게 설치 할 수 있습니다. 또한 우분투를 지원하는 소프트웨어들이 한 눈에 보여 어떤 프로그램을 쓸 수 있는지 알고 필요한 프로그램을 다운 받을 수 있습니다. 더불어 추천 목록이 있어 사용자가 보다 편리하게 프로그램을 찾고 확인할 수 있습니다. 그리고 설치 프로그램 목록을 통해 설치된 프로그램을 확인하고 제거할 수 있습니다. 또는 업데이트가 필요한 프로그램은 업데이트 목록에서 확인 가능하며 업데이트 버튼으로 손쉽게 업데이트를 할 수 있습니다. 즉 'Ubuntu Software'는 설치된 프로그램을 간편하게 관리할 수 있는 기능입니다.


#### 2.2.  네트워크 인터페이스 설정
   > 먼저 컴퓨터에서 인터페이스 카드(랜카드)를 설치해야 합니다. 이후 네트워크 환경에 맞게 설정을 해야 하는데 이 때 설정해야 할 것은 IP주소, 게이트웨이 주소 등이 있습니다. 설정은 다음과 같이 진행됩니다.

###### ① 현재 네트워크 설정 확인하기
iconfig 명령을 이용하여 현재 네트워크 설정을 확인합니다. 우분투 16.04에서는 기본 네트워크의 인터페이스 이름이 'eth()'가 아니라 'ens33'입니다.
###### ② 네트워크  설정 변경하기
다음의 iconfig 명령을 이용하여 네트워크 인터페이스 설정을 변경합니다.
 * iconfig <인터페이스 이름> <IP주소> netmask <넷마스크> broadcast <브로드캐스트 주소>
###### ③ 변경된 주소 확인
ifconfig 명령을 입력하면 IP 주소가 변경된 것을 알 수 있습니다.
###### ④  /etc/network/interfaces 파일의 편집
①~③까지 설정한 내용은 컴퓨터가 부팅되면 모두 사라지게 됩니다. 이 설정을 계속 유지하려면 해당 내용을 '/etc/network/interfaces' 파일에 저장해야 합니다. 다음 명령어를 실행합니다.
  * $sudo vi/etc/network/interfaces
###### ⑤  기존 내용 삭제 및  새로운 내용 추가
 * 주석 삽입
 
 auto<인터페이스 이름>

iface<인터페이스 이름><프로토콜><연결타입>

 * 추가 내용
 
 address<IP주소>

netmask<넷마스크>

broadcast<브로드캐스트 주소>

gateway<게이트웨이 주소>

network<네트워크 주소>

dns-nameservers<DNS 서버 주소>


 입력이 끝났으면, 파일을 저장하고 편집을 마칩니다. 이 후 컴퓨터를 부팅할 때마다 자동으로 위의 내용이 설정됩니다.

#### 2.3. unity 런처 이동
이전 버전의 우분투에는 unity 런처가 좌측으로 고정되어 있었던 반면, 16.04 버전에서는 unity런처를 하단으로 이동시킬 수 있습니다.
 * 리눅스 명령을 선호하는 사용자는 터미널에서 다음 명령어를 실행합니다.
 
 하단으로 이동

 gsettings set com.canonical.Unity.Launcher launcher-position Bottom
 
좌측으로 이동

 gsettings set com.canonical.Unity.Launcher launcher-position Left
 

 * 그래픽 방식을 이용하는 사용자는 다음을 수행합니다.
 
① Launcher 에서  Gnome Software를 시작

② dconf 편집기를 검색, 설치

③ 설치 후 dconf 편집기를 실행하고 "com -> canonical -> unity -> launcher"로 이동

④ "Launcher-position"값을 변경하여 Unity Launcher 위치를 선택


 



#### 2.4. apt 명령어 간소화
> apt 명령어는 (Advanced Package Tool)로 우분투 서버에서 새로운 패키지를 설치하거나 이미 설치된 패키지의 업그레이드 또는 설치제거나 패키지 색인을 업그레이드할 때 커맨드라인 도구로 제공되는 명령어입니다. 기존에는 apt-get이라는 명령어를 사용해서 설치했었는데, 우분투 16.04로 업그레이드 되면서 apt-get 대신에 간편하게 apt만으로도 명령을 실행할 수 있도록 바뀌었습니다.
* 주요 APT 명령어
    * sudo apt update : /etc/apt/soruce.list의 저장소를 참조하여 패키지 데이터베이스를 업그레이드한다
    * sudo apt upgrade : 설치되어 있는 모든 패키지를 조사하여 업데이트가 있는 경우 자동으로 업그레이드한다.
    * sudo apt install <package> : <package>를 다운로드하여 설치한다. 자동으로 의존성 문제 등을 고려하여 추가가 요구되는 패키지도 같이 다운로드하여 설치한다.
    * sudo apt -d install <package> : <package>를 다운로드하여 /var/cache/apt/archives/에 저장하고 설치는 하지 않는다.
    * sudo apt -f install : 만일 다운로드한 패키지가 깨진 경우를 확인하기 위하여 검사하는 명령이다.
    * sudo apt remove <package> : <package>를 삭제한다. 의존성 문제를 자동으로 해결하면서 삭제하므로 매우 유용하다.
    * sudo apt autoclean : 불완전하게 다운로드된 패키지등을 자동으로 삭제한다.
    * sudo apt clean : /var/cache/apt/archives에 저장된 패키지를 삭제한다. sudo apt -d install <package> 하여 다시 다운로드하여 저장할 수 있다.
    * sudo apt-cache pkgnames : 시스템에 설치된 모든 패키지를 출력한다.
    * sudo apt-cache show <package> : <package>에 대한 정보를 출력한다.
    * sudo apt-cache search <keyword> : /etc/apt/source.list 에 저장된 모든 패키지에서 <keyword>를 검색한다. 특정 패키지의 이름이 생각나지 않거나 일부만 아는 경우 유용하고, 대소문자 구분이 없습니다.
    * sudo apt-cache depends <package> : <package>에 대한 의존성을 검사하여 추가로 다운로드해야 하는 패키지를 보여준다. 하지만 sudo apt install <package>하면 알아서 자동으로 다운로드하여 설치해준다.
    * sudo apt-key list : APT에 저장된 gpg키 목록을 출력한다. 일부 패키지의 경우 우분투 공식 저장소가 아닌 외부저장소에서 다운로드 받아야하는 경우가 있는데 이때 해당 패키지의 서명키를 추가한 후 정상적인지 확인할 때 쓰입니다.
    * sudo apt-key add <keyfile> : 디지털 서명키를 추가한다.

#### 2.5. Libre office
* 우분투에서는 윈도우의 한글이나 Microsoft Office처럼 자체적 문서파일인 Libre를 사용합니다. 기존에 주로 쓰는 Office와 비슷하여 무리없이 사용할 수 있고, 오픈소스여서 무료로 다른  OS에서도 쉬운 사용이 가능합니다.

# 3. 불편사항 및 개선

###### 워드프로세서 기능
윈도우에서 사용하는 MS워드와 리눅스 우분투에서 사용하는 리브레오피스 라이터를 비교해 본 결과, 리브레오피스 라이터는 MS워드와 달리 그림 스타일과 추가 효과가 없고 문서의 확장 읽기 모드나 문서의 동시 편집기능을 지원하지 않는다. 하지만 다행스럽게도 몇몇 부분들은 개발 단계에 있다. 문서 동시 편집 기능 같은 경우, MS워드는 OneDrive나 Sharepoint를 이용하는데 이들은 MSOffice에서 지원하고 있다. 결국 이 말은 오피스 자체에서 OneDrive와 Sharepoint와 같은 프로그램을 지원해주지 않으면 워드프로세서에서 문서 동시 편집을 할 수 없다는 뜻이다. 따라서 리브레오피스에서 먼저 위와 같은 프로그램을 개발한 후 리브레오피스 라이터에 적용시켜야 할 것이다.

###### 다른 OS타겟 프로그램과의 호환성 문제
우분투의 기능들을 사용하던 도중 가장 불편함이 크다고 느꼈던게 'Windows' 에서 편히 사용했던 프로그램이 우분투에서는 깨짐현상이 일어난다는 것이었습니다. 예를 들면 인터넷에서 영상을 볼 때 'Adobe Flash Player' 를 사용하는 영상들이 플레이 되지 않는다는 것입니다. 유튜브의 영상은 실행되지만 네이버와 같은 곳에서 영상을 실행하면 지원하지 않는다는 경고가 뜨거나 로딩표시만 돌아가며 더 이상 진행되지 않는 걸 볼 수 있었습니다. 이에 대해 우분투에서도 Adobe를 지원하거나 또는 자체에서 변환되는 코드를 통해 영상 플레이에 있어서 다양해질 수 있으면 사용자가 보다 편할 것이라 생각합니다. 또한 한글 언어팩이 지원되지만 일부 파일에서는 한글이 깨져 확인할 수 없는 문자로 나옵니다. 이 점에 있어서는 만국공통어가 영어이기 때문에 이해가 되는 부분이지만 언어팩이 지원이 되므로 이 역시 지원을 하고 개선될 수 있을거라 생각합니다. 이와 비슷하게 우분투에서 이클립스 자바를 실행하여 자바 코드를 작성 후 그 코드를 보기 위해 소스 파일을 열게 되면 'Text Editor'로 열리면서 글자가 알 수 없는 문자로 나오게 되어 확인 할 수 없는 경우가 있습니다. 어떤 경우는 제대로 보이고 어떤 경우는 전부 깨져서 나오곤 합니다. 이 부분에 대해서는 저도 사용하는 사용자이며 아직 학생이기에 어떻게 개선될 수 있는지 해결책이 나오지 않습니다. 이 경우 사용자가 할 수 있는 방법은 연결 프로그램을 LibreOffice의 LibreOffice Writer로 열면 코드를 확인 할 수 있습니다. 하지만 이때 역시 한글은 깨지며 보이게 됩니다.


# 4. 소감

###### 엄의진
: git이라는 협업 사이트를 사용하여 간편하게 작업하여 편리했다. 마크다운의 사용법에 익숙치 않아 잦은 오류 수정이 있었던 것 외에는 손쉽게 여럿이서 함께 작업할 수 있었고, 나중에 협업하게 된다면 이를 사용해야겠다고 생각하게되었다.

###### 윤소영
: 처음엔 오픈소스SW 라고 해서 도무지 감이 잡히지 않았는데 주제를 잡기 위해 오픈소스SW에 대해 구글링도 하고 네이버를 통해 검색하면서 약간의 윤곽이 잡히게 되었습니다. 또한 우분투를 쓰면서 그저 FireFox로 인터넷하고 수업에서 실습하라는대로 Terminal에서 명령어 치기만 했는데 이번에 사용법을 작성하기 위해 현재 설치된 우분투의 버전도 확인하고 그 버전에 따른 기능 리뷰를 보고 우분투에서 직접 실행해보며 기능들을 사용하는 기회가 되었습니다.

###### 김주효 
: 부끄럽게도 이번 오픈소스sw를 수강하면서 처음으로 리눅스 우분투를 사용해 보았다. 전에는 윈도우만 사용했었는데 나름 이것만의 매력이 있는 것 같다. 이 과제를 하면서 markdown도 처음 이용해보고 github의 사용법도 잘 알게 되었다. 얻어가는 것이 많은 수업인 것 같아서 뿌듯하고 교수님께도 감사하다.



# 5. 참고
https://blog.naver.com/gnsinfo/220703762903

http://blog.naver.com/brown_brown0406/220682146313

https://gist.github.com/ihoneymon/652be052a0727ad59601

http://goproprada.tistory.com/283

http://ubuntuhandbook.org/index.php/2016/03/ubuntu-16-04-move-unity-launcher-to-bottom/

[우분투]apt-get 패키지 관리|작성자 블링블링

http://codingcoding.tistory.com/125
https://wiki.documentfoundation.org/Feature_Comparison:_LibreOffice_-_Microsoft_Office/ko



 
   


[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
Markdown
Toggle Zen Mode
Preview

   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
   
