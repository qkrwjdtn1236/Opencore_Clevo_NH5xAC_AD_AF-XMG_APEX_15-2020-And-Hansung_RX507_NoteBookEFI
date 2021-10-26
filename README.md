# Opencore_Clevo_NH5xAC_AD_AF-XMG_APEX_15-2020-And-Hansung_RX507_NoteBookEFI

- 한줄 설명 : 한성 노트북 RX50x(유사 모델 : levo_NH5xAC_AD_AF, XMG_APEX_15-2020) 에서 해킨토시 작동이 되는 EFI 모델입니다.

# 테스트한 노트북 사양 
![스크린샷 2021-10-26 오후 10 05 18](https://user-images.githubusercontent.com/48826426/138893607-eadce32b-b1d9-4f8b-86ce-418820dc3e16.png)

- CPU - Amd Ryzen R9 3900(Non X)
- GPU - Nvidia RTX 2070
- SSD - CT500, PM981
- RAM - SAMSUNG DDR4 32GB - 3200MHz CL21

* 단 Mac os에서 Nvidia 2000세대 호환이 안되어 그래픽 작업은 다소 어렵습니다.
* 그래픽 작업이 필요할 경우 : EGPU 사용하는거 권장드립니다.(단, EGPU 테스트 아직 안했습니다.)
* Mac OS 설치가 필요한 경우는 OpenCore 공식 사이트(윈도우 기준 Link : https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html#downloading-macos)를 참고하십시오.


* 12코어 CPU 모델이 아닌 경우 : config.plist 파일에서 다음처럼 수정해주세요.(수정 안할 경우, 부팅이 안됩니다.) - 참고 문서 : https://github.com/AMD-OSX/AMD_Vanilla
*  - Kernel - Patch - 0 - Replace | Data 타입 형태에서 BA(코어카운트)00000000
*  - Kernel - Patch - 1 - Replace | Data 타입 형태에서 BA(코어카운트)00000000
*  - Kernel - Patch - 2 - Replace | Data 타입 형태에서 BA(코어카운트)00000090

코어카운트는 다음과 같습니다. (코어 수의 16진수 변환한 값)
-CoreCount	Hexadecimal
-4 Core	04
-6 Core	06
-8 Core	08
-12 Core	0C
-16 Core	10
-24 Core	18
-32 Core	20

# CPU 클럭 조정
- 테스트한 노트북 모델은 클럭 조절이 안되는 버그가 있습니다. 소프트웨얼 클럭 조절 필요성이 있습니다.
- https://github.com/trulyspinach/SMCAMDProcessor 사이트를 통해서 AMD.Power.Gadget.app.zip 다운로드 후, 사용하시기 바랍니다.


# 참고 사항 및 주의 사항
* !주의! : 이러한 파일 사용을 통해 불이익 당한 경우, 배포자는 책임지지 않습니다. 신중히 사용하시길 바랍니다.
* 현재, OpenCore 0.7.5 베타버전으로 사용중 입니다.
* MacOS는 Monterey 12.0.1 버전으로 테스트 완료했습니다.
* 참고, 터치패드가 일부 제대로 작동되지 않습니다, 배터리 수치가 확인이 안됩니다, 모니터 밝기 조절이 안됩니다.
