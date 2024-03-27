# 42-Born2beroot

## 요약
***가상화 개념***을 학습하고 ***리눅스 시스템 관리***를 실습합니다 <br><br>
<img width="757" alt="image" src="https://github.com/sseunghoon/42-Born2beroot/assets/45088611/00f10717-6eac-44e6-9178-8eb64ca3175f">

### 기간
2022-07-14 ~ 2022-07-22 (3번째 과제)

## 과제 주요 요구사항 해석
- Create Virtual Machine
  - 가상화 개념을 아는가?
- Graphical Interface is forbidden.
  - 효율적인 CLI 에 익숙해지거라
- Choose Debian vs Rocky
  - Redhat계열과 Debian계열 linux의 차이를 아는가?
- You must create at least 2 encrypted partitions using LVM
  - 파티셔닝이란?
  - LVM 이란?
- A SSH service will be running on port 4242 only. For security reasons, it must not be possible to connect using SSH as root.
  - SSH 란?
- You have to configure your operating system with the UFW (or firewalld for Rocky) firewall and thus leave only port 4242 open.
  - Firewall(방화벽)이란?
- The hostname of your virtual machine must be your login ending with 42
  - hostname 이란?
- You have to implement a strong password policy.
  - 비밀번호의 필요성을 알고 정책 설정을 할 수 있는가?
- You have to install and configure sudo following strict rules.
  - sudo 설치 및 권한 설정 (group), sudo 명령어 로깅
- In addition to the root user, a user with your login as username has to be present.
  - 유저를 추가하고 권한 설정을 할 수 있는가? 
- Finally, you have to create a simple script called monitoring.sh. It must be developed in bash.
  - 시스템 상태를 모니터링할 수 있는가?
  - 주기적으로 프로그램이 실행되도록 할 수 있는가? 
- Connect Wordpress and MariaDB
  - 시스템에서 어플리케이션을 구동해봐라

## 과제 풀이
- 가상화 -> 물리적인 하드웨어 자원을 추상화하여 독립적인 가상 환경을 생성
- Redhat 계열 -> 안정적, 높은 서버 OS점유율, yum 사용
  - RHEL (Red Hat Enterprise Linux)
    - CentOS (RHEL 의 무료 파생버전)
      - Amazon (Amazon Linux 2022 부터는 Fedora기반으로 변경)
      - Locky (CentOS가 Redhat에 종속되어 새롭게 만들어진 CentOS)
- Debian 계열 -> 커뮤니티 기반, 쉬운 유지보수, apt 사용
  - Ubuntu (Debian기반)
- 파티셔닝 -> 저장 장치를 여러 구역으로 분할, 효율적인 데이터 관리 가능
- LVM -> ***lsblk*** -> Logical Volume Manager, 저장 장치를 논리적으로 합치거나 분할하는데 사용
- SSH -> Secure Shell, 네트워크를 통해 안전하게 다른 컴퓨터에 접속
- Firewall -> ***ufw allow/delete*** -> 설정된 규칙에 따라 네트워크간 데이터 패킷을 허용/차단
- hostname -> ***hostnamectl*** -> 네트워크 내에서 기기를 구별하는데 사용
- 비밀번호 정책 설정 -> ***chage*** command, ***/etc/pam.d/common-password*** 수정
- sudo 명령어 권한 설정 -> ***visudo***
- 유저 및 그룹 생성 -> ***adduser***, ***groupadd***, ***usermod***
- 주기적인 프로그램 실행 -> ***crontab***

## 과제 이미지
- 파티셔닝<br>
<img width="699" alt="image" src="https://github.com/sseunghoon/42-Born2beroot/assets/45088611/13f53d65-86a5-45a2-b4ec-53bf00f7c5a5">

- Wordpress<br>
<img width="841" alt="image" src="https://github.com/sseunghoon/42-Born2beroot/assets/45088611/800b2936-ec95-4320-9ec3-9d8102537f22">

- 모니터링 스크립트 자동화
<img width="702" alt="image" src="https://github.com/sseunghoon/42-Born2beroot/assets/45088611/e8883594-a04d-4d49-909b-2e5bbc0142b1">

### 명령어 세부 정리 (노션)
https://seunghso.notion.site/Born2beroot-5d774f9356504f7ca51a62aa8baa363c?pvs=4
