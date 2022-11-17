```yaml
layout: post
title: CpawCTF
date: 2022-10-23
categories: [programming]
tags: [rust]
```

# q6

```rs
fn main() {
    let cs =  "fsdz{Fdhvdu_flskhu_lv_fodvvlfdo_flskhu}";
    for c in cs.chars() {
        print!("{}", (c as u8 - 3) as char);
    }
}
```

# q7

```sh
❯ file exec_me
exec_me: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interprete
r /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.24, BuildID[sha1]=663a3e0e5a079fddd0de92474
688cd6812d3b550, not stripped
```

ELF: Executable and Linking Format
    Red Hatを始めとするLinuxディストリビューションの多くでは標準バイナリ形式として採用されている

```sh
docker start ubuntu_1
docker cp ./exec_me ubuntu_1:/root
docker exec -it ubuntu_1 bash -p
cd /root
chmod u+x ./exec_me
./exec_me
```

# q8

finderでクリックしたらwordが開く

# q9

webインスペクタを起動, `{`を検索

# q10

Exif情報  
mac のプレビューでℹ️ マークをクリック

# q15
webインスペクタを開く
ログを保持をチェック.
レスポンスヘッダーのX-Flagにある.

# q16
1. @wireshark
    - file>export opject>http
2. http拡張子を追加してブラウザでひらく

# q18

`%/s/lovelive!//g`

# q19

```sh
$ file misc100.zip
misc100.zip: OpenDocument Drawing
```

```sh
libreoffice ./misc100.zip
```

# q25

```sh
$ ./a.out ruoYced_ehpigniriks_i_llrg_stae 4
```

# q26

```sh
brew install --cask idafree
```

# q27

```mysql
select * from palloc_home;
```

# q28 can u login

```zsh
brew install tnftp
```

```zsh
ftp
ftp> open 118.27.110.77
Connected to 118.27.110.77.
220 Welcome to Cpaw CTF FTP service.
Name (118.27.110.77:root): cpaw_user
331 Please specify the password.
Password:
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> ls -a
229 Entering Extended Passive Mode (|||60017|)
150 Here comes the directory listing.
drwxr-xr-x    2 ftp      ftp            42 Mar 17  2021 .
drwxr-xr-x    2 ftp      ftp            42 Mar 17  2021 ..
-rw-r--r--    1 ftp      ftp            39 Sep 01  2017 .hidden_flag_file
-rw-r--r--    1 ftp      ftp
ftp> less .hidden_flag_file
```

# q23

Docker上のgdbで以下のエラー

```txt
warning: Error disabling address space randomization: Operation not permitted
```

```sh
docker run -i -t --name ctf1 --cap-add=SYS_PTRACE --security-opt="seccomp=unconfined" ctf1 /bin/bash
```


