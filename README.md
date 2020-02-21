# hunspell 한국어 맞춤법 사전 Fork

개인용 단어를 추가하기 위해서 작성한 개인용 저장소입니다. 이상한 단어들(?)이
많기 때문에 공식에 PR을 넣기도 부적절하기 때문에 그냥 개인 용도로만 씁니다.
코드도 분석이 제대로 되지 않는 중구난방입니다. 잘 돌아가니 더 이상 개인용 
코드를 건드리지 않을 계획입니다.

커스텀 단어 사전은 `data/entries/custom-words.txt` 파일이며 여기에 한 줄에 한
단어를 작성하면 됩니다.

공식 저장소의 완성된 사전 파일을 저장소에서 제거한 상태이기 때문에 무조건 data를
먼저 빌드해야 합니다.

``` sh
$ cd data
$ make build
$ cd ..
$ make
```

이렇게 하면 프로젝트 루트에 `ko.aff`, `ko.dic` 파일이 생성됩니다.

아래부터는 원래의 README 내용이 이어집니다.

# hunspell 한국어 맞춤법 사전

오픈소스 데스크톱에 널리 사용되는 hunspell 맞춤법 검사 프로그램에서 동작하는
(현재 유일한) 한국어 맞춤법 사전입니다.

현재 여러 리눅스 배포판과 오픈소스 애플리케이션에서 동작합니다.

 * 단어 단위 맞춤법 검사
 * 불규칙 활용을 포함한 용언 활용 등 교착어인 한국어의 특징에 맞게 구현
 * hunspell 맞춤법 검사를 사용하는 프로그램이라면 수정 없이도 한국어 맞춤법 검사가 동작
 * 오픈소스 배포 가능한 단어 데이터 사용

[Github 다운로드](https://github.com/spellcheck-ko/hunspell-dict-ko/releases)
(소스 및 aff/dic 파일)

## 이용하기

맞춤법 검사 기능을 사용하려면 OS별 패키지를 설치하시거나, 여러 가지
애플리케이션별 확장 기능을 이용하십시오. 또는 빌드한 사전 파일을 사용할 수도
있습니다.

사전 파일은 ko.aff 파일과 ko.dic 파일 2개로 이루어져 있고 hunspell
사전이 저장되는 위치에 복사해 사용할 수도 있습니다.

 * 데비안: hunspell-ko 패키지 설치, 6.0 (squeeze) 이후,
   <http://packages.debian.org/hunspell-ko>
 * 우분투: hunspell-ko 패키지 설치, 9.10 (karmic) 이후,
   <http://packages.ubuntu.com/hunspell-ko>
 * 페도라/CentOS/RHEL: hunspell-ko 패키지 설치, 페도라 12 (Constantine) 이후,
   <https://apps.fedoraproject.org/packages/hunspell-ko/>
 * Mac OS X 10.5: BaramSpellChecker
 * Mac OS X 10.6 이상: /Library/Spelling 또는 홈폴더/Library/Spelling
   아래 aff/dic 파일 복사
 * 파이어폭스 부가 기능,
   <https://addons.mozilla.org/ko/firefox/addon/korean-spellchecker/>
 * 리브레오피스 부가 기능,
   <https://extensions.libreoffice.org/extensions/korean-spellchecker>

리눅스 배포판에 포함되어 있는 파이어폭스나 리브레오피스는 보통 배포판에 들어
있는 hunspell을 사용하도록 빌드되어 있습니다. 그러니 배포판에 포함된 패키지를
설치할 경우 위의 브라우저나 오피스 확장 기능을 따로 설치할 필요는 없습니다.

## hunspell 버전 정보

hunspell 1.7.0 이상을 추천합니다.

 * hunspell 1.7.0 버전부터 합성어에 대한 추천 단어를 찾을 때 월등히 나은
   성능을 보이므로 추천합니다.

hunspell 1.3.1 이상 버전에서는 구현된 모든 기능이 동작합니다.

 * 단 hunspell 1.6.0 버전은 한국어 사용에 심각한 문제가 있습니다. 1.4.x
   이하 또는 1.6.1 이상 버전을 사용하십시오.
 * 대부분의 최근 OS와 애플리케이션은 1.3.1보다 높은 버전을 사용하고 있으나,
   예외적으로 맥오에스에 내장된 hunspell은 1.2.8을 사용하고 있습니다.
 * hunspell 1.2.8에 맞춰서 빌드하면 1.2.8에서도 사용할 수 있지만, 일부
   동작하지 않는 부분이 있습니다.
 * hunspell 커맨드라인에서 사용할 경우 1.2.11 이전 버전은 한글로 된 단어를
   제대로 분리하지 못해 동작하지 않습니다.
 * 1.6.2 이전 버전은 일반적인 맞춤법 검사 기능에는 문제가 없으나, hunspell
   커맨드라인에서 사용할 때 '+' 기호로 시작하는 어근이 제대로 변환되지 않습니다.

## 저작권 정보

이 소프트웨어의 저작권은 hunspell-dict-ko 프로젝트 개발자와 기여자, 사전 단어
기여자, 국립국어원에 있습니다.

전체 결과물은 GNU General Public License 3.0 라이선스에 따라 배포됩니다.

개별 파일의 경우 각각의 라이선스에 따라 배포될 수 있습니다. 사전 생성 코드와
일부 단어 데이터는 Mozilla Public License 1.1, GNU General Public License 2.0
또는 그 이후 버전, GNU Lesser General Public License 2.1 또는 그 이후 버전의
(MPL 1.1/GPL 2.0/LGPL 2.1) 3중 라이선스에 따라 배포됩니다. 국립국어원 사전
데이터를 비롯한 대부분 단어 데이터는 CreativeCommons Attribution-ShareAlike
4.0 라이선스에 따라 배포됩니다.

자세한 정보는 LICENSE.md 파일을 참고하십시오.

## 참고

 * [프로젝트 정보](https://spellcheck-ko.github.io/)
 * [Github 프로젝트](https://github.com/spellcheck-ko/hunspell-dict-ko/)
 * [의견 교환](https://groups.google.com/group/spellcheck-ko)

## 기타 정보

 * 이 프로젝트는 2017년에 과학기술정보통신부에서 지원하는 공개SW개발자Lab
   글로벌오픈프론티어 프로그램의 지원을 받았습니다. <https://kosslab.kr>
