# linux

터미널에서 리눅스를 제어하기 위해서 중요한 두가지  
1. 명령어를 통한 제어  
2. 명령은 현재 디렉토리에 내려짐 (pwd 수시 확인)  


## 명령어
*ls : 현재 디렉토리의 파일 목록을 출력하는 명령어.   
>-ls -l : 자세히 보기   
>-ls -a : 숨겨진 파일도 보여줌  
>-ls -al : 숨겨진 파일과 자세히 보기  
```
iwonhwaui-MacBook-Pro:~ wanna$ ls
AndroidStudioProjects	Downloads		Pictures
Applications		Library			Public
Desktop			Movies			VirtualBox VMs
Documents		Music

iiwonhwaui-MacBook-Pro:~ wanna$ ls -l
total 0
drwxr-xr-x   4 wanna  staff   128  5 22 15:39 AndroidStudioProjects
drwx------@  4 wanna  staff   128 11 18  2019 Applications
drwx------@ 16 wanna  staff   512  6 29 23:45 Desktop
drwx------@  7 wanna  staff   224  6 29 23:51 Documents
drwx------+ 20 wanna  staff   640  6 29 23:05 Downloads
drwx------@ 81 wanna  staff  2592  6 29 16:10 Library
drwx------+  4 wanna  staff   128 12 26  2019 Movies
drwx------+  5 wanna  staff   160 12 26  2019 Music
drwx------+  4 wanna  staff   128  1  8  2019 Pictures
drwxr-xr-x+  4 wanna  staff   128 10 14  2018 Public
drwxr-xr-x   4 wanna  staff   128  6 29 22:17 VirtualBox VMs
-rw-r--r--   1 wanna  staff     0  6 30 00:09 empty_file.txt
drwxr-xr-x   2 wanna  staff    64  6 30 00:08 hello_linux

drwxr-xr-x : 디렉토리
-rw-r--r-- : 파일

iwonhwaui-MacBook-Pro:~ wanna$ ls -a
.				.gitconfig
..				.gradle
.AnySign4PC			.lesshst
.CFUserTextEncoding		.local
.DS_Store			.npki_pkcs11.cnf
.Trash				.softforum
.android			.viminfo
.atom				.vscode
.bash_history			.yarnrc
.bash_pfofile			.zshrc
.bash_profile			AndroidStudioProjects
.bash_profile.swp		Applications
.bash_sessions			Desktop
.bitnami			Documents
.config				Downloads
.dart				Library
.dartServer			Movies
.delfino.conf			Music
.emulator_console_auth_token	Pictures
.flutter			Public
.flutter_tool_state		VirtualBox VMs

파일 앞의 .은 숨겨진 파일
```

*pwd : 현재 위치하고 있는 디렉토리를 알려주는 명령어  
```
iwonhwaui-MacBook-Pro:~ wanna$ pwd
/Users/wanna
```

*mkdir : mkdir 새로 생성할 디렉토리이름    
>mkdir -p : 필요하면 부모 디렉토리 생성히고 자식 디렉토리 생성
```
iwonhwaui-MacBook-Pro:~ wanna$ mkdir hello_linux
iwonhwaui-MacBook-Pro:~ wanna$ mkdir -p dir1/dir2/dir3/dir4
```

*cd : cd 이동할 디렉토리의 경로명  
  -상대경로 : 현재 디렉토리의 위치를 기준으로 다른 디렉토리의 위치를 표현하는 것으로 ..은 부모 디렉토리를 의미. 'cd ..'은 현재 디렉토리의 부모 디렉토리로 이동하는 명령이 된다. 참고로 현재 디렉토리는 '.' 다.   
  -절대경로 : 최상위 디렉토리를 기준으로 경로를 표현하는 것을 의미. 최상위 디렉토리는 루트(root) 디렉토리라고 하고 '/' 입니다. 'cd /'는 최상위 디렉토리로 이동한다는 뜻입니다. 'cd /home/wanna'은 현재 디렉토리가 무엇이건 언제나 '/home/wanna'을 의미하는데 이런 식의 경로 표현을 절대경로라고 한다.   
  
*rm : 파일이나 디렉토리 삭제 명령어. 디렉토리 삭제시 r 옵션을 주어야한다.  
```
iwonhwaui-MacBook-Pro:wanna wanna$ rm hello_linux/
rm: hello_linux/: is a directory
iwonhwaui-MacBook-Pro:wanna wanna$ rm empty_file.txt 
iwonhwaui-MacBook-Pro:wanna wanna$ ls -l
total 0
drwxr-xr-x   4 wanna  staff   128  5 22 15:39 AndroidStudioProjects
drwx------@  4 wanna  staff   128 11 18  2019 Applications
drwx------@ 16 wanna  staff   512  6 29 23:45 Desktop
drwx------@  7 wanna  staff   224  6 30 00:23 Documents
drwx------+ 20 wanna  staff   640  6 29 23:05 Downloads
drwx------@ 81 wanna  staff  2592  6 29 16:10 Library
drwx------+  4 wanna  staff   128 12 26  2019 Movies
drwx------+  5 wanna  staff   160 12 26  2019 Music
drwx------+  4 wanna  staff   128  1  8  2019 Pictures
drwxr-xr-x+  4 wanna  staff   128 10 14  2018 Public
drwxr-xr-x   4 wanna  staff   128  6 29 22:17 VirtualBox VMs
drwxr-xr-x   2 wanna  staff    64  6 30 00:08 hello_linux
iwonhwaui-MacBook-Pro:wanna wanna$ rm -r hello_linux/

리눅스에서 성공시는 메시지 없음. 실패시만 메시지 보임
```

*--help : 명령어 뒤에 --help를 붙이면 명령의 사용설명서가 출력
>맥에선 man 명령어 

*cp : 파일 및 디렉토리 복사 명령어. cp 파일 위치 및 파일 이름 (한칸 띄고) 파일 목적지 파일 위치 및 파일 이름
```
iwonhwaui-MacBook-Pro:~ wanna$ cp cp.txt hello_linux/cp.txt
```
*mv : 파일 및 디렉토리 이동 명령어. mv 파일 위치 및 파일 이름 (한칸 띄고) 파일 목적지 파일 위치 및 파일 이름
```
iwonhwaui-MacBook-Pro:~ wanna$ mv mv.txt hello_linux/mv.txt

파일명 변경시에도 사용
iwonhwaui-MacBook-Pro:hello_linux wanna$ mv mv.txt rename.txt
iwonhwaui-MacBook-Pro:hello_linux wanna$ ls -l
total 0
-rw-r--r--  1 wanna  staff  0  6 30 01:07 rename.txt
```

*sudo : 임시 슈퍼 유저의 권한으로 활동하는 명령어.

*nano : 파일 편집 명령어.
>^O : 파일 저장  
>^X : 편집 종료  
>^K : 잘라내기 _-nano는 복사 기능이 없어서 ^K와 ^U로 사용해야함-_  
>^U : 붙여넣기  
>(mac) esc+6 : mask set _-선택하려는 영역 뒤까지 선택하기-_  
>^W : 검색 _-다음 검색어를 보려면 다시 ^W + enter-_  

*wget : url을 통해 파일 다운 _-맥은 brew install wget 후 사용-_
>wget -O (파일 명) (다운로드 링크) : 적은 파일명으로 저장됨
```
iwonhwaui-MacBook-Pro:~ wanna$ wget http://wanna.dothome.co.kr/img/pdf/syeki.pdf
--2020-06-30 23:13:18--  http://wanna.dothome.co.kr/img/pdf/syeki.pdf
Resolving wanna.dothome.co.kr (wanna.dothome.co.kr)... 112.175.184.9
Connecting to wanna.dothome.co.kr (wanna.dothome.co.kr)|112.175.184.9|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8080675 (7.7M) [application/pdf]
Saving to: ‘syeki.pdf’

syeki.pdf           100%[===================>]   7.71M  11.7MB/s    in 0.7s    

2020-06-30 23:13:19 (11.7 MB/s) - ‘syeki.pdf’ saved [8080675/8080675]

iwonhwaui-MacBook-Pro:~ wanna$ ls -l
total 15784
drwxr-xr-x   4 wanna  staff      128  5 22 15:39 AndroidStudioProjects
drwx------@  4 wanna  staff      128 11 18  2019 Applications
drwx------@ 16 wanna  staff      512  6 29 23:45 Desktop
drwx------@  7 wanna  staff      224  6 30 22:43 Documents
drwx------+ 20 wanna  staff      640  6 29 23:05 Downloads
drwx------@ 81 wanna  staff     2592  6 29 16:10 Library
drwx------+  4 wanna  staff      128 12 26  2019 Movies
drwx------+  5 wanna  staff      160 12 26  2019 Music
drwx------+  4 wanna  staff      128  1  8  2019 Pictures
drwxr-xr-x+  4 wanna  staff      128 10 14  2018 Public
drwxr-xr-x   4 wanna  staff      128  6 29 22:17 VirtualBox VMs
-rw-r--r--   1 wanna  staff  8080675  5 22 16:03 syeki.pdf  

iwonhwaui-MacBook-Pro:~ wanna$ wget -O pdfpdf.pdf  http://wanna.dothome.co.kr/img/pdf/syeki.pdf
--2020-06-30 23:15:43--  http://wanna.dothome.co.kr/img/pdf/syeki.pdf
Resolving wanna.dothome.co.kr (wanna.dothome.co.kr)... 112.175.184.9
Connecting to wanna.dothome.co.kr (wanna.dothome.co.kr)|112.175.184.9|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8080675 (7.7M) [application/pdf]
Saving to: ‘pdfpdf.pdf’

pdfpdf.pdf          100%[===================>]   7.71M  29.1MB/s    in 0.3s    

2020-06-30 23:15:44 (29.1 MB/s) - ‘pdfpdf.pdf’ saved [8080675/8080675]

iwonhwaui-MacBook-Pro:~ wanna$ ls -l
total 31568
drwxr-xr-x   4 wanna  staff      128  5 22 15:39 AndroidStudioProjects
drwx------@  4 wanna  staff      128 11 18  2019 Applications
drwx------@ 16 wanna  staff      512  6 29 23:45 Desktop
drwx------@  7 wanna  staff      224  6 30 23:15 Documents
drwx------+ 20 wanna  staff      640  6 29 23:05 Downloads
drwx------@ 81 wanna  staff     2592  6 29 16:10 Library
drwx------+  4 wanna  staff      128 12 26  2019 Movies
drwx------+  5 wanna  staff      160 12 26  2019 Music
drwx------+  4 wanna  staff      128  1  8  2019 Pictures
drwxr-xr-x+  4 wanna  staff      128 10 14  2018 Public
drwxr-xr-x   4 wanna  staff      128  6 29 22:17 VirtualBox VMs
-rw-r--r--   1 wanna  staff  8080675  5 22 16:03 hello.pdf
-rw-r--r--   1 wanna  staff  8080675  5 22 16:03 pdfpdf.pdf
```

*cat : 사용법이 다양한 명령어.
>cat 만 친다면 사용자가 키보드로 입력하는 정보를 받음. _-나올때는 ^D-_
>cat (파일명) : 화면에 내용 출력
```
iwonhwaui-MacBook-Pro:why wanna$ cat hello.html
<html>
	<body>
		hello
	</body>
</html>
```

*grep (찾을 단어) (파일명) : 찾을 단어가 포함된 행을 보여주는 명령어.  

*pipe(|) : 파이프 앞의 결과 값을 가지고 프로그램을 연결하는 명령어.
```
iwonhwaui-MacBook-Pro:why wanna$ man ls | grep sort
     displayed first; directory and non-directory operands are sorted sepa-
     -c      Use time when file status was last changed for sorting (-t) or
     -f      Output is not sorted.  This option turns on the -a option.
     -r      Reverse the order of the sort to get reverse lexicographical
             bined with sort by size
     -t      Sort by time modified (most recently modified first) before sort-
             for sorting (-t) or long printing (-l).
     -U      Use time of file creation, instead of last modification for sort-
             with entries sorted across, rather than down, the columns.
     The following is how to do an ls listing sorted by increasing size
     chflags(1), chmod(1), sort(1), xterm(1), compat(5), termcap(5),
     
     ls의 도움말에서 sort가 포함된 행을 보여줌
```

*output(>) : 앞의 프로그램을 실행한 결과값을 화면에 출력하는 대신에 뒤의 프로그램에 저장하는 명령어
> 2> : 에러에 대한 결과를 저장  
>&nbsp;> : 결과값을 덮어쓰기 말고 추가 저장되게 함  
>&nbsp;> /dev/null : 유닉스 계열에서의 쓰레기통, 화면에서도 파일에서도 출력되지 않음  
```
iwonhwaui-MacBook-Pro:why wanna$ ls -l > result.txt
iwonhwaui-MacBook-Pro:why wanna$ cat result.txt
total 176
-rw-r--r--  1 wanna  staff  88025  6 30 23:47 linux.txt
-rw-r--r--  1 wanna  staff      0  7  1 00:41 result.txt  

iwonhwaui-MacBook-Pro:why wanna$ rm rename.txt
rm: rename.txt: No such file or directory
iwonhwaui-MacBook-Pro:why wanna$ rm rename.txt > result.txt
rm: rename.txt: No such file or directory
iwonhwaui-MacBook-Pro:why wanna$ rm rename.txt 2> error.log
iwonhwaui-MacBook-Pro:why wanna$ cat error.log
rm: rename.txt: No such file or directory
```

*head : 문장의 10줄만 출력하는 명령어.
>head -n1 : 한줄만 출력
````
>head -n1 : 한줄만 출력iwonhwaui-MacBook-Pro:~ wanna$ head why/linux.txt 
Linux
From Wikipedia, the free encyclopedia
Jump to navigationJump to search
This article is about the family of operating systems. For the kernel, see Linux kernel. For other uses, see Linux (disambiguation).
Linux
Tux the penguin
Tux the penguin, mascot of Linux[1]
Developer	Community
Linus Torvalds
Written in	C, Assembly language

iwonhwaui-MacBook-Pro:~ wanna$ head -n1 why/linux.txt 
Linux
```

### 순차적 실행
> *mkdir why;cd why : why 폴더 생성후 그 폴더로 이동 _-세미콜론으로 구분-_
```
iwonhwaui-MacBook-Pro:~ wanna$ mkdir why;cd why
iwonhwaui-MacBook-Pro:why wanna$ pwd
/Users/wanna/why
```

### shell script : 한번에 명령어를 실행시키는 기능
> *chmod +x (파일명) : 파일에 실행 기능을 추가하는 명령어
```
 GNU nano 2.0.6               File: backup                                      

#!/bin/bash               _-작성된 backup이라는 프로그램을 bash로 해석되어야 함을 나타냄-_
if ! [ -d bak ]; then     _-현재 디렉토리에 bak라는 디렉토리가 없다면-_
        mkdir bak         _-bak라는 디렉토리를 생성-_
fi                        _-조건문 종료-_
cp *.log bak              _-현재 디렉토리의 .log로 끝나는 모든 파일을 bak로 복사-_


                                  [ New File ]
^G Get Help  ^O WriteOut  ^R Read File ^Y Prev Page ^K Cut Text  ^C Cur Pos
^X Exit      ^J Justify   ^W Where Is  ^V Next Page ^U UnCut Text^T To Spell


iwonhwaui-MacBook-Pro:script wanna$ ls -l
total 8
-rw-r--r--  1 wanna  staff    0  7  2 16:29 a.log
-rw-r--r--  1 wanna  staff    0  7  2 16:29 b.log
-rw-r--r--  1 wanna  staff   61  7  2 16:39 backup
drwxr-xr-x  5 wanna  staff  160  7  2 16:30 bak
-rw-r--r--  1 wanna  staff    0  7  2 16:29 c.log
iwonhwaui-MacBook-Pro:script wanna$ ./backup
-bash: ./backup: Permission denied
iwonhwaui-MacBook-Pro:script wanna$ chmod +x backup
iwonhwaui-MacBook-Pro:script wanna$ ls -l
total 8
-rw-r--r--  1 wanna  staff    0  7  2 16:29 a.log
-rw-r--r--  1 wanna  staff    0  7  2 16:29 b.log
-rwxr-xr-x  1 wanna  staff   61  7  2 16:39 backup<
drwxr-xr-x  5 wanna  staff  160  7  2 16:30 bak
-rw-r--r--  1 wanna  staff    0  7  2 16:29 c.log
iwonhwaui-MacBook-Pro:script wanna$ rm -rf bak
```
