`해커` 당신이 작업 공간에 혼자 있다고 생각하셨나요?
일반적인 Linux 시스템에는 수많은 사용자가 있습니다!
Linux 시스템의 전체 사용자 목록은 `/etc/passwd` 파일에 지정되어 있습니다(이 이름은 역사적인 이유로 붙여졌습니다. 실제로는 더 이상 비밀번호를 저장하지 않습니다).
다음은 dojo 컨테이너의 예시입니다.

```console
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
_apt:x:100:65534::/nonexistent:/usr/sbin/nologin
systemd-timesync:x:101:101:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
systemd-network:x:102:103:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
systemd-resolve:x:103:104:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
mysql:x:104:105:MySQL Server,,,:/nonexistent:/bin/false
messagebus:x:105:106::/nonexistent:/usr/sbin/nologin
sshd:x:106:65534::/run/sshd:/usr/sbin/nologin
hacker:x:1000:1000::/home/hacker:/bin/bash
```

많은 사용자와 많은 정보가 있습니다!
각 줄에는 `:`로 구분된 사용자 이름, 비밀번호가 있던 위치를 나타내는 `x`(실제 비밀번호 위치는 나중에 설명하겠습니다), 숫자로 된 사용자 ID, 숫자로 된 기본 그룹 ID, 긴 사용자 정보, 홈 디렉터리, 기본 셸이 포함되어 있습니다.

하단에 `hacker` 사용자가 보입니다.
바로 당신입니다!
나머지 사용자 대부분은 기존 계정 관리 목적으로 사용하거나, 설치된 다양한 소프트웨어를 지원하는 서비스 계정이거나, 일부는 "유틸리티" 계정입니다(예: `nobody` 사용자는 특정 프로그램이 특별한 권한 없이 실행되도록 하는 데 사용됩니다).

중요한 사용자 중 하나는 시스템 관리자인 `root`입니다.
시스템 관리자는 명백한 보안 문제를 야기합니다. 리눅스의 다양한 기능을 통해 `root` 사용자가 될 수 있는 `해커` 사용자는 시스템에 큰 피해를 입힐 수 있습니다.
해커가 시스템에 침입하는 가장 흔한 목적은 `root` 권한까지 획득하는 것이므로, `root` 권한은 반드시 보호해야 합니다!

이 모듈에서는 다양한 사용자 횡설수설을 살펴보고, 시스템 관리자로 사용자를 전환하는 방법을 배우고, 그 과정에서 즐거움을 느껴보겠습니다!
