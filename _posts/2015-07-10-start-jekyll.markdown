---
layout: post
title: "Windows 에서 Jekyll 설치"
description: "Jekyll 설치 및 시작"
date: 2015-7-11
category: blog
tags: [blog, windows, jekyll]
---

<!-- <div id="toc"><p class="toc_title">목차</p></div> -->
* TOC
{:toc}

## 소개
- Jekyll 은 아주 심플하고 블로그 지향적인 정적 사이트 생성기입니다.  Mac OSX 또는 Linux에서는 설치하는것이 매우 쉽습니다. 하지만 Windows에서 설치하려면 몇가지 추가 요소가 있는데 여기서 도와 줄겁니다.
	
    참고 : Windows에서 jekyll를 사용하는 것은 공식적으로 지킬 팀에 의해 지원되지 않습니다. 그리고, 이 가이드에 소개되는 동안 [지킬 웹 사이트 ](http://jekyllrb.com/docs/windows/) 아직 비공식 남아있다.

## Windows 에서 Jekyll을 사용하는 방법
- Windows 가 공식적으로 지원되는 플랫폼은 아니지만, 몇 가지만 손보면 Jekyll 을 실행할 수 있습니다. 이 페이지의 목적은 Windows 사용자에 의해서 발굴된 정보들을 수집하는 것입니다.

# 설치
- Julian Thilo 가 작성한 Jekyll 을 Windows 에서 실행하는 방법은 대체적으로 잘 동작하는 것으로 보입니다.

## 설치 루비와 루비 DevKit
- 루비는 지킬을 만든 프로그래밍 언어입니다. 당신은 루비와 "네이티브 확장"으로 지킬의 일부 종속성을 구축하는 데 필요한 해당 DevKit을 설치해야합니다.

### 루비를 설치
- 먼저, 아래 버튼을 클릭 시스템의 아키텍처 (x86 / x64)과 일치 Ruby 2.2.2에 대한 설치 프로그램을 다운로드합니다.

	**[windows용 루비 다운로드](http://rubyinstaller.org/downloads/)**
- 설치 프로그램을 실행하고 설치의 단계를 통해 이동합니다. 아래의 화면에 도착하면, "PATH에 루비 실행 파일을 추가"확인란을 선택해야합니다.

	![](http://jekyll-windows.juthilo.com/public/img/ruby-path.png)

- 설치를 클릭 컴퓨터 사향에 따라 몇분 내에 루비가 설치됩니다.

### 루비 DevKit 설치
- 지킬은 종속성이 설치되어 있으면 복잡한 절차 없이 바로 원시소스를 제공한다. 완전한 기능을 실행 파일로 만들려면, DevKit을 설치해야합니다.

- 아래 버튼을 클릭하여 루비 설치 및 시스템 아키텍처에 해당하는 DevKit 아카이브를 다운로드합니다. Ruby 2.2.2 들어, 파일 이름이 시작됩니다 DevKit-mingw64 . 시스템에 따라 32 비트 또는 64bit를 버전을 선택합니다.

	**[루비 DevKit 다운로드](http://rubyinstaller.org/downloads/)**	
- 다운로드는 자동 압축 해제가능한 아카이브 파일입니다. 파일을 실행하면 설치할 경로 공백없이 입력합니다. 간단한 하게 c:\RubyDevKit\에 'Extract' 클릭하고 프로세스가 완료 될 때까지 기다립니다.

- 다음으로, DevKit를 초기화하고 루비 설치에 바인딩해야합니다. 커맨드창을 열고 DevKit 압축을 푼 폴더로 이동합니다.

	`cd C:\RubyDevKit`

- 루비 설치시 자동 감지하고 다음 단계를 위해 설정 파일에 추가.

	`ruby dk.rb init`

- 루비 설치에 바인딩, DevKit를 설치합니다.

	`ruby dk.rb install`

### 개요
- 좋아 잘따라 왔나요? 에러 없이 잘 따라왔으면 지금 컴퓨터에 루비와 루비 devKit가 설치되어 있을겁니다. 이제 devKit으로 사용가능한 모든 기능을 구축 할수 있습니다. 다음 단계에 gem명령으로 jekyll을 설치 할수 있습니다.

# jekyll gem 설치
## 설치
- jekyll 자체는 설치가 쉬운 소프트웨어 패키지입니다. ruby gem형태로 제공됩니다. jekyll과 모든 기본 종속성을 설치하려면 command창을 열어서 다음 명령어를 입력 합니다.

	`gem jekyll install`

- 설치하는대 종속수에 따라 수분이 걸립니다.

# Syntax Highlighter 설치
## 개요 
- 기본적으로 jekyll python기반의 Syntax Highlighter입니다. pygments.rb도 함께 제공됩니다. Windows에서 사용하려면 python과 몇가지 추가 도구를 설치해야 합니다.

### Rouge 설치
- 커맨드창을 열어서 다음 명령어를 입력 합니다.

	`gem rouge install`
- 설치가 끝나면 ==_config.yml== 에  rouge를 설정 합니다.
	`highlighter: rouge`

- rouge 설치 완료


# Pygments 설치
- Windows에서 Pygments를 사용하려면 python, PIP, pygmrnts.rb를 설치 해야합니다.

## 파이선 설치
- 주의 python 설치 버전은 v2.7.10입니다. python v3.x 버전에서는 작동이 안됩니다.
- 아래 버튼을 클릭하고, 시스템의 아키텍처 (32 비트 / 64bit를)과 일치 V2.7 설치 프로그램을 다운로드합니다
    **[windows용 파이썬 v2.7.10 다운로드](http://rubyinstaller.org/downloads/)**
![](http://jekyll-windows.juthilo.com/public/img/python-path.png)
- 다운로드 한 파일을 실행하고 설치의 단계를 통해 이동합니다. Add python.exe to Path에서 옆에 상자를 클릭 "Entire feature will be installed on local hard drive."을 선택하고 설치합니다.

## PIP 설치
- PIP는 ruby gem과 비슷한 python 패키지를 설치하고 관리하기위한 도구입니다.당신은 Pygments, pygments.rb이 코드를 사용하려면 파이썬 패키지를 설치해야합니다. 먼저, 아래 버튼을 클릭하고 다운로드 get-pip.py 해당 사이트에있는 링크를 통해.
	**[windows용 PIP 다운로드](http://rubyinstaller.org/downloads/)**
- get-pip.py 파일을 다른이름 저장으로 c:\pip에 저장합니다. 그런 다음 저장 폴더로 이동 합니다. 커맨드 창에서 다음 명령어를 입력 합니다.

	`cd c:\pip`

- 그런 다음 필요한 모든 구성 요소를 설치하려면 다음 명령어를 입력 합니ㅏㄷ.
	`python get-pip.py`

## Pygments의 python기반 설치
- ptgments를 설치하려면 커맨드창에서 다음 명령어를 입력합니다.
	`python -m pip install pygments`

## WDM의 gem 설치
- Windows의 경우이 jekyll기능을 사용하려면 하나더 gem으로 설치해야합니다. 간단히 명령 줄에서 다음 명령을 실행합니다.
    `gem install wdm`

### 개요
- 휴~ 이제 Windows에서 jekill을 실행하는데 필요한 모든 기능을 설치를 했습니다.이제 jekyll을 실행해서 잘 작동이 되는지만 확인 하면 됩니다.

# 오류없이 jekyll 실행
## BOM을 허용하지 않습니다.
- 이 경우 BOM에 UTF-8 인코딩된 파일의 헤더 문자가 없는지 확인 합니다.

## 인코딩 설정 옵션
- jekyll v1.3.0 부터 인코딩을 지정 할수 있습니다. ==_config.yml==에 다음과 같이 추가해 줍니다.

`encoding: utf-8`
## 하위 폴더 사용
- jekyll 
```
C:\Users\You>jekyll serve
Configuration file: C:\Users\You\_config.yml
            Source: C:\Users\You
       Destination: C:\Users\You\_site
      Generating...
jekyll 2.4.0 | Error: Permission denied - .
```

## 마무리
```
jekyll build
jekyll build --watch
jekyll build -w
jekyll serve
jekyll serve --watch
jekyll serve -w
```

- 축하합니다. 성공적으로 windows에서 jekyll울 설치 했습니다.

- jekyll를 사용할때 도움이 필요한 경우 
[jekyll 번역 사이트](http://jekyllrb-ko.github.io/)
