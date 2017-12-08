Ubuntu 16.04 사용법
============================
**우**리들의 **분**수에 맞는 **투**박한 프로젝트
잘부탁드립니다:)


>[2조]

>조장 
20154274 엄의진

>조원
20154212 윤소영
20154233 김주효

------------------------------

# 목차


#### 1. 선정 동기
#### 2. 기능별 설명
##### 2.1. ubuntu software
##### 2.2. 네트워크 유-무선 공유
##### 2.3. unity 런처 이동
##### 2.4. apt 명령어 간소화
##### 2.5. Libre office
#### 3. 불편사항 및 개선
#### 4. 소감
#### 5. 참고


-------------------------------


# 1. 선정 동기

많은 오픈소스SW 중에 우분투를 선택하게 된 이유는 일단 저희가 수업에서 쓰는 OS이기 때문입니다. 평소 'Microsoft' 의 'Windows' 운영체제만 써왔고 그것에 익숙해져 있다보니 수업 외에 우분투를 사용할 일이 많지 않습니다. 또한  실상 사용하려해도 수업에서 다룬 'Terminal' 프로그램만 사용할 뿐 우분투의 다른 기능들을 사용해보지 않았습니다. 그렇기 때문에 이번 기회를 통해 가장 가까이 있지만 멀게 느껴졌던 '우분투'를 

 
# 2. 기능별 설명

#### 2-2  네트워크 인터페이스 설정
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

#### 2-3 unity 런처 이동
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
* apt 명령어는 (Advanced Package Tool)로 우분투 서버에서 새로운 패키지를 설치하거나 이미 설치된 패키지의 업그레이드 또는 설치제거나 패키지 색인을 업그레이드할 때 커맨드라인 도구로 제공되는 명령어입니다. 기존에는 apt-get이라는 명령어를 사용해서 설치했었는데, 우분투 16.04로 업그레이드 되면서 apt-get 대신에 간편하게 apt만으로도 명령을 실행할 수 있도록 바뀌었습니다.
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

# 4. 소감
엄의진 :
# 5. 참고
https://blog.naver.com/gnsinfo/220703762903
http://blog.naver.com/brown_brown0406/220682146313
https://gist.github.com/ihoneymon/652be052a0727ad59601
http://goproprada.tistory.com/283
http://ubuntuhandbook.org/index.php/2016/03/ubuntu-16-04-move-unity-launcher-to-bottom/
[우분투]apt-get 패키지 관리|작성자 블링블링
http://codingcoding.tistory.com/125


 
   


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
   
