Ubuntu 16.04 사용법
============================
**우**리들의 **분**수에 맞는 **투**박한 프로젝트

잘부탁드립니다:) 20154274 엄의진 20154212 윤소영 20154233 김주효
----------------------------
# 목차

1. 선정 동기
2. 기능별 설명
    * ubuntu software
    * 네트워크 인터페이스 설정
    * unity 런처 이동
    * apt 명령어 간소화
    * Libre office
3. 불편사항 및 개선
4. 소감
5. 참고

-------------------------------

# 1. 선정 동기
 


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

5.참고
https://blog.naver.com/gnsinfo/220703762903
http://blog.naver.com/brown_brown0406/220682146313
https://gist.github.com/ihoneymon/652be052a0727ad59601
http://goproprada.tistory.com/283
http://ubuntuhandbook.org/index.php/2016/03/ubuntu-16-04-move-unity-launcher-to-bottom/
 
        


 
    



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
   
