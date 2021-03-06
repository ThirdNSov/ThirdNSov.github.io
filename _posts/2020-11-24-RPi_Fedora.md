---
layout: post
title: Raspberry Pi3+에 Fedora Linux 설치
category: Linux
tags: linux, raspberrypi, rpi, fedora, rpi3
excerpt_separator:  <!--more-->
---

Fedora를 설치해서 사용해보려고 Hyper-V 설치하고 하다가 문득 집에 RPi3+가 남아서  
여기에 설치를 해보자 싶어서 시작.

라즈베리파이 사용할 때 주로 그냥 라즈비안 올려서 사용했었는데 페도라를 올리면 또  
다른 느낌일 것 같아서 급하게 자료 찾아보고 설치를 진행했다.

우선 다행이도 [Fedora WiKi](https://fedoraproject.org/wiki/Architectures/ARM/Raspberry_Pi#aarch64_supported_images_for_Raspberry_Pi_3){:target="_blank"}에 라즈베리파이 설치 관련 문서가 있었고  
영어의 압박만 견디면 따라하기 나름 쉽게 정리되어있다.

해당 문서 내용 중에 라즈베리파이용 페도라 이미지가 있으니 다운 받아서 설치만  
해주면 된다.

![](/assets/img/fedora_wiki_1.PNG)

ARMv7용과 aarch64용(RPi3용)으로 구분되어있으니 본인 환경에 맞게  
다운 받으면 된다.  
이미지는 구했고 이미지를 SD Card에 구워야하는데 Windows 환경에서 진행하였기  
때문에 자주 사용했던 [balenaEtcher](https://www.balena.io/etcher/){:target="_blank"}를 사용하였다.

리눅스 환경에서 진행하는 방법은 위키에 자세히 잘 설명되어있으니  
참고하면 될 것 같다.

![](/assets/img/fedora_rpi_1.PNG)

이미지가 성공적으로 구워졌으면 이제 라즈베리파이에 SD카드 옮겨 꽂고 부팅만 하면  
끝!

처음에 어려울거라 생각하고 포스팅도 같이 준비한건데 위키가 생각보다  
잘 정리되어있고 페도라가 라즈베리파이를 잘 지원해줘서 특별히 따로 정리할 게  
없는 것 같다..

---

다 구워진 후 부팅을 했는데 가지고 있던 RPi3가 고장이 나있었다..  
아무리 기다려도 부팅은 되지 않고 전원부 온도만 급상승하는 증상이 나와서  
새로 한대를 구했다.. 

![](/assets/img/undervoltage.jpg)

부팅 도중에 전력 부족 로그가 출력되기는 하지만 기다리니 부팅은 되었다.  
다만 Fedora 33 WorkStation으로 설치를 했더니  
RPi3에서 벅찬지 부팅만으로도 굉장히 시간이 오래 걸려서  
Minimal 버전으로 다시 설치 진행해보았다. 

여전히 undervoltage 이슈는 있지만 찾아보니 RPi3 B+는 2.5A 이상급으로
전원이 공급 되어야 안정이 되는 것 같다.

## 참고 링크
[Fedora WiKi](https://fedoraproject.org/wiki/Architectures/ARM/Raspberry_Pi#aarch64_supported_images_for_Raspberry_Pi_3){:target="_blank"}  
[balenaEtcher](https://www.balena.io/etcher/){:target="_blank"}  
[UnderVoltage 관련 ](https://www.raspberrypi.org/forums/viewtopic.php?t=210914){:target="_blank"}