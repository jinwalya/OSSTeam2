Ubuntu 16.04 사용법
============================
**우**리들의 **분**수에 맞는 **투**박한 프로젝트
잘부탁드립니다:)


>[2조]
>>조장 
>>20154274 엄의진

>>조원
>>20154212 윤소영/ 
>>20154233 김주효

-------------------------

# 목차

1. 선정 동기
2. 기능별 설명
* ubuntu software
* 네트워크 유-무선 공유
* unity 런처 이동
* apt 명령어 간소화
* Libre office
3. 불편사항 및 개선
4. 소감
5. 참고

-------------------------------


# 1. 선정 동기

많은 오픈소스SW 중에 우분투를 선택하게 된 이유는 일단 저희가 수업에서 쓰는 OS이기 때문입니다. 평소 'Microsoft' 의 'Windows' 운영체제만 써왔고 그것에 익숙해져 있다보니 수업 외에 우분투를 사용할 일이 많지 않습니다. 또한 실상 사용하려해도 수업에서 다룬 'Terminal' 프로그램만 사용할 뿐 우분투의 다른 기능들을 사용해보지 않았습니다. 그렇기 때문에 이번 기회를 통해 가장 가까이 있지만 멀게 느껴졌던 '우분투'를 하나하나 살펴보며 'Windows' 에서 보지 못했던 기능이나 우분투의 특징적인 기능들을 몇 가지 뽑아 그 사용법을 소개하며 저희도 공부하는 시간이 되기 위해 우분투를 선정하게 되었습니다.

이 문서를 통해 열심히 검색하고 공부하며 **우**리들의 **분**수에 맞는 **투**박한 프로젝트를 시작합니다.


# 2. 기능별 설명
#### 2.1  Ubuntu Software
이 기능은 'Windows 10'에서 볼 수 있는 '앱 스토어'와 비슷한 기능입니다. 우분투는 Terminal로 명령어를 통해 어떤 프로그램을 설치할 수 있습니다. 이때는 사용자가 필요로하는 프로그램의 이름과 경로를 알아야하는데 'Ubuntu Software' 를 이용하면 굳이 명령어를 쓸 필요없이 간단하게 설치 할 수 있습니다. 또한 아래 사진에서 보듯이 우분투를 지원하는 소프트웨어들이 한 눈에 보여 어떤 프로그램을 쓸 수 있는지 알고 필요한 프로그램을 다운 받을 수 있습니다. 더불어 추천 목록이 있어 사용자가 보다 편리하게 프로그램을 찾고 확인할 수 있습니다. 그리고 설치 프로그램 목록을 통해 설치된 프로그램을 확인하고 제거할 수 있습니다. 또는 업데이트가 필요한 프로그램은 업데이트 목록에서 확인 가능하며 업데이트 버튼으로 손쉽게 업데이트를 할 수 있습니다. 즉 'Ubuntu Software'는 설치된 프로그램을 간편하게 관리할 수 있는 기능입니다.
[Alt text](/home/hp/UbuntuSoftware_screenshot.png "우분투 소프트웨어 참고 사진")
=======

 
# 2. 기능별 설명
* apt 명령어 간소화
    * apt 명령어는 (Advanced Package Tool)로 우분투 서버에서 새로운 패키지를 설치하거나 이미 설치된 패키지의 업그레이드 또는 설치제거나 패키지 색인을 업그레이드할 때 커맨드라인 도구로 제공되는 명령어입니다. 기존에는 apt-get이라는 명령어를 사용해서 설치했었는데, 우분투 16.04로 업그레이드 되면서 apt-get 대신에 간편하게 apt만으로도 명령을 실행할 수 있도록 바뀌었습니다.
    * 주요 APT 명령어
        * sudo apt update : /etc/apt/soruce.list의 저장소를 참조하여 패키지 데이터베이스를 업그레이드한다
        * sudo apt upgrade : 설치되어 있는 모든 패키지를 조사하여 업데이트가 있는 경우 자동으로 업그레이드한다.
        * sudo apt install <package> : <package>를 다운로드하여 설치한다. 자동으로 의존성 문제 등을 고려하여 추가가 요구되는 패키지도 같이 다운로드하여 설치한다.
        * sudo apt remove <package> : <package>를 삭제한다. 의존성 문제를 자동으로 해결하면서 삭제하므로 매우 유용하다.

* Libre office
    * 우분투에서는 윈도우의 한글이나 Microsoft Office처럼 자체적 문서파일인 Libre를 사용합니다. 기존에 주로 쓰는 Office와 비슷하여 무리없이 사용할 수 있고, 오픈소스여서 무료로 다른  OS에서도 쉬운 사용이 가능합니다.

# 3. 불편사항 및 개선

# 4. 소감

# 5. 참고
[출처] [우분투]apt-get 패키지 관리|작성자 블링블링
[출처] http://codingcoding.tistory.com/125




[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
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
   
