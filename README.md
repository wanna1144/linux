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
