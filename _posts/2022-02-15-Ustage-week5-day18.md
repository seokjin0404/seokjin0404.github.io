---
title:  "[Week 5] 리눅스 기초 명령어"

categories:
  - Ustage
tags:
  - [BoostCamp, Ustage]
 
date: 2022-02-15
last_modified_at: 2022-02-15
published: false
---

## 리눅스 기초 명령어 정리

다음 명령어의 간단한 설명과 예시를 정리하겠습니다.

mkdir, ls, pwd, cd, echo, vi, bash,  sudo, cp, mv, cat, clear, history, find, export, alias

head, tail, sort, uniq, grep, cut, 

---



### mkdir

현제 디렉토리에서 폴더를 생성해주는 명령어입니다.

###  ls 

디렉토리에 있는 폴더 및 파일을 확인합니다. -a, -l, -h 등의 옵션이 있습니다.

### pwd 

현재 폴더의 절대경로를 알려줍니다.

### cd

다음 폴더로 변경합니다.

![image](https://user-images.githubusercontent.com/86605720/153990260-9fc0560c-00cf-412f-819e-c8bd1a8366f0.png)  

간단한 예시입니다. example이라는 폴더를 만들고 이동하고 현재 폴더의 절대경로를 받았습니다.

---



### vi

vim 편집기로 파일을 생성할 수 있습니다. vi example.txt로 파일을 생성할 수 있습니다.

command mode, insert mode, last line mode가 있는데 예시를 보겠습니다.

![image](https://user-images.githubusercontent.com/86605720/153990344-cb882d82-9d5c-4951-8e98-35dd293cee35.png) 

콘솔에 vi example.txt를 실행하면 현재 command mode 상태입니다.

![image](https://user-images.githubusercontent.com/86605720/153991311-25077266-d8e9-43bc-bdd3-e9c3d17c875a.png){:.alignleft}



i를 누르면 밑에 insert가 나오는데, 이때 파일을 수정할 수 있고 echo "hello world"를 추가해줍니다.

echo는 터미널에 출력해주는 커맨드입니다. echo\`pwd\`와 같이 사용하면 쉘커맨드의 결과를 출력할 수 있습니다.

![image](https://user-images.githubusercontent.com/86605720/153991385-03644d82-ff0d-4507-a219-d106504feafa.png) {:.alignleft}

esc를 입력하면 다시 command mode로 돌아가고 :를 입력하면 last line mode로 바뀝니다.

wq!를 입력하면 저장한 후 강제종료 할 수 있습니다.

https://blockdmask.tistory.com/25 이 블로그 보면 더 자세한 명령어를 볼 수 있습니다.

### bash

bash는 쉘 스크립트를 진행할 수 있는데, 위에서 작성한 echo "hello world"와 echo "hi world"를 실행한 것을 볼 수 있습니다.

![image](https://user-images.githubusercontent.com/86605720/153992074-e6c0150c-344e-42fb-b415-4a2ddaee32b8.png){:.alignleft}

<br>

---

### cp

파일 또는 폴더를 복사하기

### mv

파일 또는 폴더를 이동할 수 있는데, 같은 폴더 내로 이동시키면 이름을 바꾸는대도 사용할 수 있습니다.

![image](https://user-images.githubusercontent.com/86605720/153992457-f2232168-4cd6-4b5e-a35f-e5ba06e8bc61.png){:.alignleft}

cp를 사용해서 example2.txt로 복사했고 mv로 이름을 변경했습니다.



## cat

cat은 파일의 내용을 출력할 수 있는데, 아래 예시처럼 하나의 파일의 내용을 출력할 수도 있고, 두 개의 파일을 concatenate 해서 출력할 수도 있습니다.

![image](https://user-images.githubusercontent.com/86605720/153992907-7bedd057-1d61-4827-8774-4f38fd5504b5.png){:.alignleft}

Redirection이란 stdout을 다른 파일이나 스트림으로 전달하는 것을 의미하는데

\> 는 내용을 덮어쓰거나, 존재하지 않는 파일이면 새로 파일을 생성하고 저장합니다.

\>\> 는 추가하고 싶은 내용을 뒤에 나오는 파일 맨 아래줄에 추가할 수 있습니다.

![image](https://user-images.githubusercontent.com/86605720/153993121-a9d6ef3e-baf2-46cc-9510-a9cff0270834.png) {:.alignleft}

![image](https://user-images.githubusercontent.com/86605720/153993383-7ffbaff5-33f6-4e03-81ae-c3f89f67b05e.png) {:.alignleft}

<br>

---

### alias

명령어를 줄일 수 있습니다. 복잡하고 자주 사용하는 명령어를 짧고 간단하게 별명을 지어줍니다.

### 기타 head tail sort uniq grep cut

그 밖에도 head, tail, sort, uniq, grep,cut 등이 있습니다. head와 tail은 파일 앞 뒤의 정해진 만큼 출력할 수 있고, sort는 옵션에 따라 오름차순, 내림차순으로 정렬해 줍니다. uniq는 연속으로 중복된 행을 제거할 수 있고 -c 와 함께 쓰면 행 앞에 얼만큼 중복됐는지 표시해줍니다. 

\| 은 pipe라고 부르는데, 출력된 내용을 다음의 입력으로 쓰고 싶을 때 사용합니다. 

sort와 uniq를 활용하면 cat 파일명|sort|uniq 과 같이 입력하면 연속으로 중복된 행 뿐만 아니라 모든 중복된 행을 제거할 수 있습니다.

grep은 특정 패턴과 매칭되는 라인을 검색하는 커맨드이고, cut은 특정 문자를 기준으로 구분되는 필드를 추출할 수 있는 명령어입니다.

지금 언급한 명렁어와 위에 언급한 명령어 정도는 쉽게 쓸 수 있도록 연습해야 할 것 같습니다. 끝. 
