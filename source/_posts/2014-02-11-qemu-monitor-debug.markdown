---
layout: post
title: "QEMU MONITOR 사용하여 Guest OS 상태 확인"
date: 2014-02-11 14:22:15 +0900
comments: true
categories: libvirt, qemu, debug, tools
---

guest os 에 접근할 수 없는 경우, 아래와 같이 QEMU MONITOR 기능을 사용하여 guest os 의 디버그 정보를 획득한다.  (qemu/monitor 명령어 참고: http://en.wikibooks.org/wiki/QEMU/Monitor) 

* cpu register 정보 
    * virsh qemu-monitor-command --hmp <GUEST NAME> info registers
* sysrq 를 사용하여 커널의 상태 정보 획득 
    * sysrq 참고: https://www.kernel.org/doc/Documentation/sysrq.txt
    * "virsh console <GUEST NAME>" 명령어를 사용하여 console 에 연결
    * "virsh qemu-monitor-command --hmp v1 sendkey alt-sysrq-7" 명령어를 사용하여 커널의 로그 레벨을 debug 레벨로 변경 
    * "virsh qemu-monitor-command --hmp v1 sendkey alt-sysrq-t" 명령어를 사용하여 process 의 정보를 확인 
* 커널 로그 확인 
    * 커널의 __log_buf 주소를 System.map 또는 아래와 같이 /proc/kallsysms 파일에서 확인 
    * "virsh qemu-monitor-command --hmp v2  'x/65000hc 0xffffff818d8ca0' " 명령어를 사용하여 __log_buf  확인 
* 첨부한 convlog 를 사용하여 덤프된 데이터를 가독성 있는 포맷으로 변환 
