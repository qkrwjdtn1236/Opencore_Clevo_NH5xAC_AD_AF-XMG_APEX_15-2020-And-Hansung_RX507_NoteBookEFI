# Opencore_Clevo_NH5xAC_AD_AF-XMG_APEX_15-2020-And-Hansung_RX507_NoteBookEFI

한성 노트북 RX50x(유사 모델 : levo_NH5xAC_AD_AF, XMG_APEX_15-2020) 에서 해킨토시 작동이 되는 EFI 모델입니다.

테스트한 노트북 사양 

CPU - Amd Ryzen R9 3900(Non X)
GPU - Nvidia RTX 2070
SSD - CT500, PM981
RAM - SAMSUNG DDR4 32GB - 3200MHz CL21

* 단 Mac os에서 Nvidia 2000세대 호환이 안되어 그래픽 작업은 다소 어렵습니다.
* 그래픽 작업이 필요할 경우 : EGPU 사용하는거 권장드립니다.(단, EGPU 테스트 아직 안했습니다.)
* Mac OS 설치가 필요한 경우는 OpenCore 공식 사이트(윈도우 기준 Link : https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html#downloading-macos)를 참고하십시오.


* 12코어 CPU 모델이 아닌 경우 : config.plist 파일에서 다음처럼 수정해주세요.(수정 안할 경우, 부팅이 안됩니다.) - 참고 문서 : https://github.com/AMD-OSX/AMD_Vanilla
*  - Kernel - Patch - 0 - Replace | Data 타입 형태에서 BA(코어카운트)00000000
*  - Kernel - Patch - 1 - Replace | Data 타입 형태에서 BA(코어카운트)00000000
*  - Kernel - Patch - 2 - Replace | Data 타입 형태에서 BA(코어카운트)00000090

코어카운트는 다음과 같습니다. (코어 수의 16진수 변환한 값)
CoreCount	Hexadecimal
4 Core	04
6 Core	06
8 Core	08
12 Core	0C
16 Core	10
24 Core	18
32 Core	20

* !주의! : 이러한 파일을 사용을 통해 불이익을 당한 경우, 배포자느 책임지지 않습니다.
* 현재, OpenCore 0.7.5 베타버전으로 사용중 입니다.
