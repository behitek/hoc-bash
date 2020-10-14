<p align="center">
  <img src="https://cloud.githubusercontent.com/assets/2059754/24601246/753a7f36-1858-11e7-9d6b-7a0e64fb27f7.png" alt="bash logo"/>
</p>

## Table of Contents
  1. [Basic Operations](#1-basic-operations)  
    1.1. [File Operations](#11-file-operations)  
    1.2. [Text Operations](#12-text-operations)  
    1.3. [Directory Operations](#13-directory-operations)  
    1.4. [SSH, System Info & Network Operations](#14-ssh-system-info--network-operations)  
    1.5. [Process Monitoring Operations](#15-process-monitoring-operations)
  2. [Basic Shell Programming](#2-basic-shell-programming)  
    2.1. [Variables](#21-variables)  
    2.2. [Array](#22-array)  
    2.3. [String Substitution](#23-string-substitution)  
    2.4. [Functions](#24-functions)  
    2.5. [Conditionals](#25-conditionals)  
    2.6. [Loops](#26-loops)  
  3. [Tricks](#3-tricks)  
  4. [Debugging](#4-debugging)  
  

# 1. Basic Operations

### a. `export`
Hiển thị danh sách tất cả các biến môi trường. Nếu bạn muốn xem chi tiết một biến cụ thể, sử dụng `echo $VARIABLE_NAME`.
```bash
$ export
```
Ví dụ:
```bash
$ export
AWS_HOME=/Users/adnanadnan/.aws
LANG=en_US.UTF-8
LC_CTYPE=en_US.UTF-8
LESS=-R

$ echo $AWS_HOME
/Users/adnanadnan/.aws
```

### b. `whatis`
whatis hiển thị mô tả các command của người dùng, command hệ thống, các hàm thư viện, và các command khác có trong **manual page**.
```bash
$ whatis something
```
Ví dụ:
```bash
$ whatis pwd
pwd (1)              - print name of current/working directory
```

### c. `whereis`
whereis giúp bạn tìm kiếm các file thực thi, file nguồn và các manual page sử dụng cơ sở dữ liệu được xây dựng tự động bởi hệ thống. 
```bash
$ whereis name
```
Ví dụ:
```bash
$ whereis python
python: /usr/bin/python3.8 /usr/lib/python2.7 /usr/lib/python3.8 /etc/python3.8 /usr/local/lib/python3.8 /mnt/c/Users/hieunv/AppData/Local/Programs/Python/Python37/python.exe /mnt/c/Users/hieunv/AppData/Local/Programs/Python/Python37/python3.dll /mnt/c/Users/hieunv/AppData/Local/Programs/Python/Python37/python37.dll /mnt/c/Users/hieunv/AppData/Local/Microsoft/WindowsApps/python.exe /mnt/c/Users/hieunv/AppData/Local/Microsoft/WindowsApps/python3.exe
```

### d. `which`
which giúp bạn tìm kiếm các file thực thi từ các đường dẫn thư mục mà bạn đã đặt trong biến môi trường PATH. Command này sẽ in ra [các] đường dẫn tuyệt đối của file thực thi.
```bash
$ which program_name 
```
Ví dụ:
```bash
$ which python3
/usr/bin/python3
```

### e. clear
Xóa nội dung trên cửa sổ làm việc.
```bash
$ clear
```
## 1.1. File Operations
<table>
   <tr>
      <td><a href="#a-cat">cat</a></td>
      <td><a href="#b-chmod">chmod</a></td>
      <td><a href="#c-chown">chown</a></td>
      <td><a href="#d-cp">cp</a></td>
      <td><a href="#e-diff">diff</a></td>
      <td><a href="#f-file">file</a></td>
      <td><a href="#g-find">find</a></td>
      <td><a href="#h-gunzip">gunzip</a></td>
      <td><a href="#i-gzcat">gzcat</a></td>
      <td><a href="#j-gzip">gzip</a></td>
      <td><a href="#k-head">head</a></td>
   </tr>
   <tr>
      <td><a href="#l-lpq">lpq</a></td>
      <td><a href="#m-lpr">lpr</a></td>
      <td><a href="#n-lprm">lprm</a></td>
      <td><a href="#o-ls">ls</a></td>
      <td><a href="#p-more">more</a></td>
      <td><a href="#q-mv">mv</a></td>
      <td><a href="#r-rm">rm</a></td>
      <td><a href="#s-tail">tail</a></td>
      <td><a href="#t-touch">touch</a></td>
   </tr>
</table>

### a. `cat`
Nó có thể sử dụng cho một số mục đích sau trong UNIX hoặc Linux:
* Hiển thị nội dung tệp tin văn bản lên màn hình
* Copy các tệp tin văn bản
* Gộp các tệp tin văn bản
* Tạo các tệp tin văn bản mới
```bash
$ cat filename
$ cat file1 file2 
$ cat file1 file2 > newcombinedfile
$ cat < file1 > file2 #copy file1 to file2
```

### b. `chmod`
Command chmod là viết gọn của "change mode". Nó cho phép bạn thay đổi các quyền đọc (read), ghi (write) và thực thi (excute) của các tệp và thư mục. Xem thêm thông tin về command này [tại đây](https://ss64.com/bash/chmod.html).
```bash
$ chmod -options filename
```

### c. `chown`
Command chown là viết gọn của "change owner". Nó cho phép bạn thay đổi owner của một tệp hoặc thư mục, có thể là một userr và một group. Cách sử dụng cơ bản là truyền vào user (owner), tiếp theo là group và phân tách nhau bởi dấu hai chấm.
```bash
$ chown -options user:group filename
```

### d. `cp`
Copy một tệp tin từ vị trí này tới vị trí khác.
```bash
$ cp filename1 filename2
```
Trong đó `filename1` là đường dẫn ban đầu của tệp tin gốc và `filename2` là đường dẫn đích của tập tin bản sao.

### e. `diff`
So sánh các tệp tin và hiển thị ra các sự khác biệt.
```bash
$ diff filename1 filename2
```

### f. `file`
Xác định loại tệp tin và hiển thị thông tin encoding.  
```bash
$ file filename
```
Ví dụ:
```bash
$ file index.html
 index.html: HTML document, ASCII text
```
### g. `find`
Tìm kiếm các tệp tin trong một thư mục
```bash
$ find directory options pattern
```
Ví dụ:
```bash
$ find . -name README.md
$ find /home/user1 -name '*.png'
```

### h. `gunzip`
Giải nén các tệp tin nén bởi gzip.  
```bash
$ gunzip filename
```

### i. `gzcat`
Cho phép bạn xem nội dung các tệp tin nén gzip mà không cần phải gunzip chúng.
```bash
$ gzcat filename
```

### j. `gzip`
Dùng để nén các tệp tin.
```bash
$ gzip filename
```

### k. `head`
Hiển thị n=10 (mặc định) dòng đầu tiên của một tệp tin. Nếu muốn thay đổi n, sử dụng `head -n <number> filename`.
```bash
$ head filename
$ head -n 1 filename
```

### l. `lpq`
Kiểm tra hàng đợi máy in.
```bash
$ lpq
```
Ví dụ:
```bash
$ lpq
Rank    Owner   Job     File(s)                         Total Size
active  adnanad 59      demo                            399360 bytes
1st     adnanad 60      (stdin)                         0 bytes
```

### m. `lpr`
Thực hiện in 1 tệp tin.  
```bash
$ lpr filename
```

### n. `lprm`
Xóa lệnh in đang có trong hàng đợi máy in.
```bash
$ lprm jobnumber
```

### o. `ls`
Liệt kê các tệp tin và thư mục. `ls` có rất nhiều tham số: `-l` để hiển thị dạng danh sách với các thông tin kích thước, chủ sở hữu, ai có quyền thao tác và thời gian thay đổi lần cuối của các tệp tin. `-a` sẽ hiển thị tất cả các tệp tin (bao gồm các tệp tin bị ẩn). Xem thêm thông tin về command này [tại đây](https://ss64.com/bash/ls.html).
```bash
$ ls option
```
Ví dụ:
```bash
$ ls -la
rwxr-xr-x   33 adnan  staff    1122 Mar 27 18:44 .
drwxrwxrwx  60 adnan  staff    2040 Mar 21 15:06 ..
-rw-r--r--@  1 adnan  staff   14340 Mar 23 15:05 .DS_Store
-rw-r--r--   1 adnan  staff     157 Mar 25 18:08 .bumpversion.cfg
-rw-r--r--   1 adnan  staff    6515 Mar 25 18:08 .config.ini
-rw-r--r--   1 adnan  staff    5805 Mar 27 18:44 .config.override.ini
drwxr-xr-x  17 adnan  staff     578 Mar 27 23:36 .git
-rwxr-xr-x   1 adnan  staff    2702 Mar 25 18:08 .gitignore
```

### p. `more`
Hiển thị một phần đầu nội dung của tệp tin (xem thêm bằng phím cách, gõ `q` để thoát)
```bash
$ more filename
```

### q. `mv`
Di chuyển một tệp tin từ vị trí này tới vị trí khác.
```bash
$ mv filename1 filename2
```
Trong đó `filename1` là đường dẫn ban đầu của tệp tin và `filename2` là đường dẫn nơi bạn muốn chuyển tệp tin tới.

Và command này cũng dùng để đổi tên tệp tin hoặc thư mục.
```bash
$ mv old_name new_name
```

### r. `rm`
Xóa một tệp tin. Sử dụng command này với thư mục bạn sẽ gặp báo lỗi.
`rm: directory: is a directory`
Để xóa một thư mục, bạn cần truyền tham số `-r` để nó xóa thư mục đó và toàn bộ nội dung bên trong. Bạn có thể bổ sung tham số `-f` để yêu cầu xóa và bỏ qua xác nhận của hệ thống.
```bash
rm filename
```

### s. `tail`
Giống `head` command, nhưng là hiển thị nội dung ở cuối tệp tin. Sử dụng tham số `-n` nếu muốn thay đổi số lượng dòng hiển thị.
```bash
tail filename
```

### t. `touch`
Cập nhật thời gian truy cập và sửa đổi của tệp tin tới thời gian hiện tại. Nếu tệp tin đó không tồn tại, nó sẽ được tạo ra.
```bash
touch filename
```
Ví dụ:
```bash
$ touch ltkk.md
```

## 1.2. Text Operations

<table>
    <tr>
      <td><a href="#a-awk">awk</a></td>
      <td><a href="#b-cut">cut</a></td>
      <td><a href="#c-echo">echo</a></td>
      <td><a href="#d-egrep">egrep</a></td>
      <td><a href="#e-fgrep">fgrep</a></td>
      <td><a href="#f-fmt">fmt</a></td>
      <td><a href="#g-grep">grep</a></td>
      <td><a href="#h-nl">nl</a></td>
      <td><a href="#i-sed">sed</a></td>
      <td><a href="#j-sort">sort</a></td>
   </tr>
   <tr>
      <td><a href="#k-tr">tr</a></td>
      <td><a href="#l-uniq">uniq</a></td>
      <td><a href="#m-wc">wc</a></td>
   </tr>
</table>

### a. `awk`
awk là một trong những command rất hữu ích để làm việc với các tệp tin văn bản. Nó tác động tới từng dòng nội dung của văn bản. Mặc định `awk` sẽ dùng khoảng trắng để phân tách các trường. Cú pháp thông dụng nhất của `awk` là
```bash
$ awk '/pattern_cần_tìm/ { hành_động_cần_làm_nếu_khớp_pattern; }' file_to_parse
```

Hãy thử xem xét tệp tin `/etc/passwd`. Ví dụ tệp tin này có các dòng dữ liệu như sau:
```
root:x:0:0:root:/root:/usr/bin/zsh
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
```
Bây giờ bạn chỉ muốn lấy username có trong tệp tin này. Tham số `-F` sẽ giúp chúng ta chỉ định việc phân tách các trường dựa vào đâu. Trong trường hợp này đó là dấu `:`. Và `{ print $1 }` có nghĩa là chúng ta in ra trường đầu tiên.
```bash
$ awk -F':' '{ print $1 }' /etc/passwd
```
Sau khi thực thi command trên bạn sẽ có được kết quả như sau:
```
root
daemon
bin
sys
sync
```
Để xem thêm thông tin về `awk`, hãy tìm đọc [cái này](https://www.cyberciti.biz/faq/bash-scripting-using-awk).


### b. `cut`
Xóa một phần nội dung ở mỗi dòng của các tệp tin văn bản.

Giả sử dưới đây là nội dung của tệp tin *example.txt*:
```bash
red riding hood went to the park to play
```

*Và thử chỉ hiển thị các cột 2, 7 và 9 ngăn cách nhau bởi dấu cách*
```bash
$ cut -d " " -f2,7,9 example.txt
```
Kết quả thực thi command trên là:
```bash
riding park play
```

### c. `echo`
Hiển thị một dòng văn bản lên màn hình.

*Hiển thị "Hello World"*
```bash
$ echo Hello World
```
Kết quả thực thi command trên là:
```bash
Hello World
```

*Hiển thị "Hello World" có ký tự xuống hàng*
```bash
$ echo -ne "Hello\nWorld\n"
```
Kết quả thực thi command trên là:
```bash
Hello
World
```

### d. `egrep`
Tìm và xuất ra các dòng khớp với một pattern nào đó - Extended Expression (đại diện cho: `grep -E`).

*Nội dung tệp tin example.txt*
```bash
Lorem ipsum
dolor sit amet, 
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Xuất ra các dòng có xuất hiện từ "Lorem" hoặc "dolor" trong example.txt*
```bash
$ egrep '(Lorem|dolor)' example.txt
or
$ grep -E '(Lorem|dolor)' example.txt
```
Kết quả thực thi command trên là:
```bash
Lorem ipsum
dolor sit amet,
et dolore magna
duo dolores et ea
sanctus est Lorem
ipsum dolor sit
```

### e. `fgrep`
Tìm và xuất ra các dòng khớp với một pattern nào đó - FIXED pattern matching  (alias for: `grep -F`).

*Nội dung tệp tin example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
foo (Lorem|dolor) 
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Tìm dòng chứa chính xác chuỗi '(Lorem|dolor)' trong example.txt*
```bash
$ fgrep '(Lorem|dolor)' example.txt
or
$ grep -F '(Lorem|dolor)' example.txt
```
Kết quả thực thi command trên là:
```bash
foo (Lorem|dolor) 
```

### f. `fmt`
Định dạng lại cách hiển thị văn bản

*Ví dụ: example.txt (chỉ có 1 dòng)*
```bash
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.
```

*Hiển thị dữ liệu của example.txt có chiều rộng 20 ký tự*
```bash
$ cat example.txt | fmt -w 20
```
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

### g. `grep`
Tìm kiếm văn bản trong các tệp tin. Bạn có thể sử dụng grep để tìm các dòng văn bản khớp với một hoặc nhiều biểu thức chính quy (regular expression). Command này sẽ chỉ xuất ra các dòng khớp với điều kiện của bạn.
```bash
$ grep pattern filename
```
Ví dụ:
```bash
$ grep admin /etc/passwd
_kadmin_admin:*:218:-2:Kerberos Admin Service:/var/empty:/usr/bin/false
_kadmin_changepw:*:219:-2:Kerberos Change Password Service:/var/empty:/usr/bin/false
_krb_kadmin:*:231:-2:Open Directory Kerberos Admin Service:/var/empty:/usr/bin/false
```
Bạn cũng có thể yêu cầu `grep` tìm kiếm bỏ qua yếu tố viết hoa/thường với tham số `-i`. Sử dụng `-r` để tìm kiếm cho tất cả các tệp tin trong 1 thư mục, ví dụ:
```bash
$ grep -r admin /etc/
```
Và dùng `-w` để so khớp từ (word boudary). Xem thêm thông tin về `grep`, hãy đọc [link này](https://www.cyberciti.biz/faq/grep-in-bash).

### h. `nl`
Thêm số thứ tự dòng vào đầu các dòng trong tệp văn bản.

*example.txt*
```bash
Lorem ipsum
dolor sit amet,
consetetur
sadipscing elitr,
sed diam nonumy
eirmod tempor
invidunt ut labore
et dolore magna
aliquyam erat, sed
diam voluptua. At
vero eos et
accusam et justo
duo dolores et ea
rebum. Stet clita
kasd gubergren,
no sea takimata
sanctus est Lorem
ipsum dolor sit
amet.
```

*Hiển thị examlple.txt kèm với số thứ tự dòng*
```bash
$ nl -s". " example.txt 
```
```bash
     1. Lorem ipsum
     2. dolor sit amet,
     3. consetetur
     4. sadipscing elitr,
     5. sed diam nonumy
     6. eirmod tempor
     7. invidunt ut labore
     8. et dolore magna
     9. aliquyam erat, sed
    10. diam voluptua. At
    11. vero eos et
    12. accusam et justo
    13. duo dolores et ea
    14. rebum. Stet clita
    15. kasd gubergren,
    16. no sea takimata
    17. sanctus est Lorem
    18. ipsum dolor sit
    19. amet.
```

### i. `sed`
Trình chỉnh sửa phục vụ cho việc tạo bộ lọc (filter) và chuyển đổi (tranform) dữ liệu văn bản.

*example.txt*
```bash
Hello This is a Test 1 2 3 4
``` 

*replace all spaces with hyphens*
```bash
$ sed 's/ /-/g' example.txt
```
```bash
Hello-This-is-a-Test-1-2-3-4
```

*Thay thế các chữ số bằng ký tự "d"*
```bash
sed 's/[0-9]/d/g' example.txt
```
```bash
Hello This is a Test d d d d
```

### j. `sort`
Sắp xếp các dòng văn bản trong một tệp tin. Sử dụng tham số `-r` để sắp xếp theo thứ tự đảo ngược.
*example.txt*
```bash
f
b
c
d
g
a
e
d
```

*sort example.txt*
```bash
$ sort example.txt
```
```bash
a
b
c
d
d
e
f
g
```

*Xáo trộn các dòng của example.txt nhưng nhóm các dòng giống nhau lại*
```bash
$ sort example.txt | sort -R
or
$ sort -R example.txt
```
```bash
b
f
a
c
d
d
g
e
```

### k. `tr`
Thay đổi hoặc xóa các ký tự

*example.txt*
```bash
Hello World Foo Bar Baz!
```

*Chuyển các ký tự thường thành ký tự hoa*
```bash
$ cat example.txt | tr 'a-z' 'A-Z' 
```
```bash
HELLO WORLD FOO BAR BAZ!
```

*Thay thế khoảng trắng bằng dấu xuống dòng (\n)*
```bash
$ cat example.txt | tr ' ' '\n'
```
```bash
Hello
World
Foo
Bar
Baz!
```

### l. `uniq`
Xóa trùng lặp dữ liệu trong tệp tin văn bản

*example.txt*
```bash
a
a
b
a
b
c
d
c
```

*Hiển thị dữ liệu không còn trùng lặp của example.txt (bạn cần sắp xếp trước, nếu không command uniq sẽ không thấy được sự trùng lặp)*
```bash
$ sort example.txt | uniq
```
```bash
a
b
c
d
```

*Hiển thị các dòng dữ liệu không có trùng lặp kèm theo số lần các dòng này có trong tệp tin văn bản*
```bash
$ sort example.txt | uniq -c
```
```bash
    3 a
    2 b
    2 c
    1 d
```

### m. `wc`
Cho chúng ta biết tệp tin có bao nhiêu dòng, bao nhiều từ và bao nhiêu ký tự trong đó.
```bash
wc filename
```
Ví dụ:
```bash
$ wc demo.txt
7459   15915  398400 demo.txt
```
Trong đó `7459` là số dòng, `15915` là số từ và `398400` số lượng ký tự.

## 1.3. Directory Operations

<table>
   <tr>
      <td><a href="#a-cd">cd</a></td>
      <td><a href="#b-mkdir">mkdir</a></td>
      <td><a href="#c-pwd">pwd</a></td>
   </tr>
</table>

### a. `cd`
`cd` là viết tắt của "change directory". Nó giúp bạn di chuyển vị trí làm việc. Chạy command dưới đây
```bash
$ cd
```
sẽ di chuyển bạn về thư mục home. Bạn có thể truyền vào đường dẫn tương đối hoặc tuyệt đối nơi bạn muốn di chuyển tới để di chuyển tới nơi đó.
```bash
$ cd dirname
$ cd ~/.ssh/ # di chuyển tới thư mục .ssh nằm trong thư mục home
$ cd .. # lùi về trước 1 thư mục
```

### b. `mkdir`
Tạo một thư mục mới.
```bash
$ mkdir dirname
```
Bạn có thể sử dụng để tạo nhiều thư mục cùng lúc tại thư mục bạn đang làm việc.
```bash
$ mkdir 1stDirectory 2ndDirectory 3rdDirectory
```
Bạn cũng có thể sử dụng mkdir để tạo một thư mục có tên `project1` bên trong thư mục `/samples/bash/projects/` đã có trước đó bằng cách chạy command sau:
```bash 
$ mkdir /samples/bash/projects/project1
```
Nếu một trong số các thư mục cha không tồn tại, sẽ có báo lỗi.

### c. `pwd`
Cho bạn biết đường dẫn tuyệt đối của thư mục nơi bạn đang làm việc. Viết tắt của `print working directory`:
```bash
$ pwd
```

## 1.4. SSH, System Info & Network Operations

<table>
   <tr>
      <td><a href="#a-bg">bg</a></td>
      <td><a href="#b-cal">cal</a></td>
      <td><a href="#c-date">date</a></td>
      <td><a href="#d-df">df</a></td>
      <td><a href="#e-dig">dig</a></td>
      <td><a href="#f-du">du</a></td>
      <td><a href="#g-fg">fg</a></td>
      <td><a href="#h-finger">finger</a></td>   
      <td><a href="#i-jobs">jobs</a></td>
      <td><a href="#j-last">last</a></td>
   </tr>
   <tr>
      <td><a href="#k-man">man</a></td>
      <td><a href="#l-passwd">passwd</a></td>
      <td><a href="#m-ping">ping</a></td>
      <td><a href="#n-ps">ps</a></td>
      <td><a href="#o-quota">quota</a></td>
      <td><a href="#p-scp">scp</a></td>
      <td><a href="#q-ssh">ssh</a></td>
      <td><a href="#r-top">top</a></td>
      <td><a href="#s-uname">uname</a></td>
      <td><a href="#t-uptime">uptime</a></td>
   </tr>
   <tr>
      <td><a href="#u-w">w</a></td>
      <td><a href="#v-wget">wget</a></td>
      <td><a href="#w-whoami">whoami</a></td>
      <td><a href="#x-whois">whois</a></td>
   </tr>
</table>

### a. `bg`
Hiển thị danh sách các backgroud job (công việc chạy trong nền).

### b. `cal`
Hiển thị lịch của tháng hiện tại.

### c. `date`
Hiển thị ngày và giờ của thời điểm hiện tại.

### d. `df`
Hiển thị mức dùng ổ đĩa: đã dùng bao nhiêu, còn trống bao nhiêu

### e. `dig`
Kiểm tra thông tin bản ghi DNS của một tên miền.
```bash
$ dig domain
```

### f. `du`
Hiển thị mức sử dụng ổ đĩa của các tệp tin hoặc thư mục. Xem thêm thông tin về command tại [link này](http://www.linfo.org/du.html)
```bash
du [option] [filename|directory]
```
Các option:
- `-h` (Dễ đọc hơn) Hiển thị mức dùng ở đơn vị (KB), (MB) và (GB).
- `-s` (Tóm tắt) Hiển thị mức dùng ổ đĩa của thư mục một cách tóm tắt.

Ví dụ:
```bash
$ du -sh pictures
1.4M pictures
```

### g. `fg`
Di chuyển các job lên foreground (chuyển từ chạy trong nền ra chạy trên màn hình console)

### h. `finger`
Displays information about user.  
Hiển thị thông tin về một user.
```bash
$ finger username
```
### i. `jobs`
Liệt kê các job đang chạy trong backgroud, cung cấp cho bạn chỉ số job (job number)

### j. `last`
Liệt kê các thông tin đăng nhập cuối cùng của bạn về người dùng được chỉ định.
```bash
$ last yourUsername
```

### k. `man`
Hiển thị tài liệu hướng dẫn (manual page) của command cụ thể.
```bash
$ man command
```

### l. `passwd`
Cho phép user đang đăng nhập thay đổi mật khẩu đăng nhập.

### m. `ping`
PING tới 1 host nào đó kèm theo kết quả. Được dùng để kiểm tra xem máy của bạn có kết nối tới host đó hay không.
```bash
$ ping 8.8.8.8
```

### n. `ps`
Lists your processes.  
Liệt kê các tiến trình hiện có của bạn.
```bash
$ ps -u yourusername
```
Sử dụng tham số `-ef`. `-e` cho tất cả các tiến trình and `-f` để hiển thị đầy đủ thông tin. 
```bash
$ ps -ef
```

### o. `quota`
Cho biết mức dùng ổ đĩa của bạn là bao nhiêu.
```bash
$ quota -v
```

### p. `scp`
Truyền dữ liệu từ máy localhost tới máy remote hoặc ngược lại.

*Copy dữ liệu từ localhost tới remote host*
```bash
$ scp source_file user@host:directory/target_file
```
*copy dữ liệu từ remote host về localhost*
```bash
$ scp user@host:directory/source_file target_file
$ scp -r user@host:directory/source_folder target_folder
```
Nếu cổng kết nối SSH không phải cổng 80 (mặc định), bạn cần sử dụng tới tham số `-P`.
```bash
$ scp -P port user@host:directory/source_file target_file
```

### q. `ssh`
ssh (SSH client) là một chương trình cho phép bạn đăng nhập và thực thi các command trên 1 máy remote từ máy tính của bạn.
```bash
$ ssh user@host
```
Bạn có thể sử dụng `-p` để truyền vào cổng kết nối SSH, mặc định là cổng 80.  
```bash
$ ssh -p port user@host
```

### r. `top`
Hiển thị các tiến trình đang được kích hoạt.

### s. `uname`
Hiển thị thông tin nhân hệ điều hành. 
```bash
$ uname -a
```

### t. `uptime`
Hiển thị thời gian hoạt động (uptime).

### u. `w`
Displays who is online.
Hiển thị user nào đang online.

### v. `wget`
Download tệp tin từ internet.
```bash
$ wget file_url
```

### w. `whoami`
Trả về username của user đang đăng nhập.

### x. `whois`
Xem thông tin whois của một tên miền.
```bash
$ whois domain
```

## 1.5. Process Monitoring Operations

<table>
   <tr>
      <td><a href="#a-kill">kill</a></td>
      <td><a href="#b-killall">killall</a></td>
      <td><a href="#c-&">&amp;</a></td>
      <td><a href="#d-nohup">nohup</a></td>
   </tr>
</table>

### a. `kill`
Bắt buộc dừng (kết thúc) một tiến trình có PID mà bạn cung cấp.
```bash
$ kill PID
```

### b. `killall`
Bắt buộc dừng (kết thúc) tất cả các tiến trình theo tên tiến trình.
```bash
$ killall processname
```

### c. &
Ký tự `&` chỉ định cho một command phải chạy ở chế độ backgroud.
```bash
$ command &
```

### d. `nohup`
nohup là viết tắt của "No Hang Up". Nó cho phép bạn chạy các command hoặc tiến trình trong backgroud ngay cả khi bạn đăng xuất (logout, không đồng nghĩa với tắt máy) khỏi terminal. 
```bash
$ nohup command
```
Kết hợp với `&` để tạo ra các job chạy trong backgroud và vẫn chạy khi đã đăng xuất.
```bash
$ nohup command &
```

# 2. Basic Shell Programming

Dòng đầu tiên mà bạn sẽ viết trong các file bash script được gọi là `shebang`. Dòng này trong các file script cho phép các file được thực thi một cách độc lập mà không cần phải gõ `sh`, `bash`, `python`, `php`,... thêm vào đầu command khi chạy.


```bash
#!/usr/bin/env bash
```

## 2.1. Variables

Tạo các biến trong bash cũng tương tự như trong các ngôn ngữ lập trình. Nó không có kiểu dữ liệu. Biến trong bash có thể chưa số, ký tự, chuỗi ký tự, ... Bạn cũng không cần phải khai báo biến, chỉ cần gán giá trị cho biến và tham chiếu của nó sẽ được tạo ra.

Ví dụ:
```bash
str="hello world"
```

Dòng lệnh trên tạo một biến tên `str` và gán giá trị "hello world" cho nó. Để lấy giá trị của biến, bạn chỉ cần thêm `$` vào trước tên biến:

Ví dụ:
```bash
echo $str   # hello world
```
## 2.2. Array
Tương tự các ngôn ngữ lập trình, bash cũng có mảng. Một mảng là một tập hợp chứa nhiều giá trị. Không có kích thước giới hạn cho mảng. Mảng trong bash có chỉ số bắt đầu từ 0. Có một vài cách khác nhau để tạo ra biến mảng trong bash:

Ví dụ:
```bash
array[0]=val
array[1]=val
array[2]=val
array=([2]=val [0]=val [1]=val)
array=(val val val)
```
Để hiển thị một giá trị ở chỉ số nhất định, sử dụng cú pháp sau:

```bash
${array[i]}     # trong đó i là chỉ số mảng
```

Nếu không chỉ định chỉ số mảng, chỉ số 0 sẽ được ngầm định. Để xem có bao nhiêu phần từ trong mảng, sử dụng cú pháp sau:

```bash
${#array[@]}
```

Bash cũng có toán tử 3 ngôi. Xem một số ví dụ dưới đây:

```bash
${varname:-word}    # Nếu varname tồn tại và khác null, trả về varname; ngược lại trả về word
${varname:=word}    # Nếu varname tồn tại và khác null, trả về varname; ngược lại gán giá trị word cho varname và trả về varname
${varname:+word}    # Nếu varname tồn tại và khác null, trả về word; ngược lại trả về null
${varname:offset:length}    # substring, trả về substring của varname bắt đầu từ offset và lấy tới length ký tự.
```

## 2.3 String Substitution

Xem một số cú pháp dưới đây để biết các thao tác thay thế chuỗi

```bash
${variable#pattern}         # Nếu pattern khớp với phần đầu của variable, xóa phần khớp ngắn nhất trong variable và trả về phần còn lại.
${variable##pattern}        # Nếu pattern khớp với phần đầu của variable, xóa phần khớp dài nhất trong variable và trả về phần còn lại.
${variable%pattern}         # Nếu pattern khớp với phần cuối của variable, xóa phần khớp ngắn nhất trong variable và trả về phần còn lại.
${variable%%pattern}        # Nếu pattern khớp với phần cuối của variable, xóa phần khớp dài nhất trong variable và trả về phần còn lại.
${variable/pattern/string}  # Phần khớp dài nhất trong variable sẽ được thay thế bởi string. Chỉ có so khớp đầu tiên bị thay thế.
${variable//pattern/string} # Phần khớp dài nhất trong variable sẽ được thay thế bởi string. Tất cả các so khớp bị thay thế.
${#varname}     # Trả về độ dài của chuỗi trong biến varname.
```

## 2.4. Functions

Như hầu hết các ngôn ngữ lập trình, bạn có thể sử dụng hàm để nhóm các đoạn code vào thành tức chức năng riêng nhằm mục đích cấu trúc và tái sử dụng. Trong Bash, khai báo một hàm nó như thế này `function my_func { my_code }`. Còn việc gọi hàm chỉ đơn giản là viết tên hàm ra thôi.


```bash
function name() {
    shell commands
}
```

Ví dụ:
```bash
#!/bin/bash
function hello {
   echo world!
}
$ hello
# hay một ví dụ khác có tham sô:
$ function say {
    echo $1
}
$ say "hello world!"
```

Khi bạn chạy command `$ hello` phía trên nó sẽ xuất ra "world!". Hai hàm `hello` và `say` ở trên là giống nhau, sự khác biệt ở đây chỉ là hàm `say` có sử dụng đối số đầu tiên mà nó nhận được. Các tham số trong hàm làm việc tương tự như tham số trong các command, tập lệnh.

## 2.5. Conditionals

Cấu trúc điều khiển trong Bash tương tự như các ngôn ngữ lập trình khác. Có nhiều dạng cấu trúc điều khiển nhưng cơ bản nhất là câu lệnh `if` điều kiện `then` khối lệnh và khối lệnh chỉ được thực thi khi điều kiện là đúng (true).

```bash
if [ điều_kiện ]; then
    # Thực thi khi điều_kiện là true
else
    # Thực thi khi điều_kiện là false
fi
```

Đôi khi việc sử dụng `case statements` sẽ làm code bạn rõ ràng hơn so với sử dụng if.

```bash
case expression in
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    ...
esac
```

Ví dụ về các biểu thức:

```bash
statement1 && statement2  # Chỉ đúng khi cả 2 đúng
statement1 || statement2  # Chỉ sai khi cả 2 sai

str1=str2       # str1 và str là như nhau
str1!=str2      # str1 khác str2
str1<str2       # str1 nhỏ str2
str1>str2       # str1 lớn hơn str2
-n str1         # str1 khác null (có độ dài > 0)
-z str1         # str1 là null (có độ dài = 0)

-a file         # file tồn tại
-d file         # file tồn tại và là thư mục
-e file         # file tồn tại; tương đương -a
-f file         # file tồn tại và là tệp tin (i.e., không phải là thư mục)
-r file         # bạn có quyền đọc
-s file         # file tồn tại và không rỗng (có nội dung)
-w file         # bạn có quyền ghi
-x file         # bạn có quyền thực thi (chạy) file này, hoặc có quyền tìm kiếm nếu file là thư mục
-N file         # file được thay đổi ở lần đọc cuối
-O file         # bạn là chủ của file
-G file         # file có group ID là của bạn (của một trong số các group, nếu có nhiều group)

file1 -nt file2     # file1 mới hơn file2
file1 -ot file2     # file1 cũ hơn file2

-lt     # nhỏ hơn (less than)
-le     # nhỏ hơn hoặc bằng (less or equal)
-eq     # bằng (equal)
-ge     # lớn hơn hoặc bằng (greater or equal)
-gt     # lớn hơn (greater)
-ne     # khác bằng (not equal)
```

## 2.6. Loops

Có 3 loại vòng lặp trong Bash: `for`, `while` và `until`.
There are three types of loops in bash. `for`, `while` and `until`.

Các cú pháp `for` khác nhau:
```bash
for x := 1 to 10 do
begin
  statements
end

for name [in list]
do
  statements có thể sử dụng $name
done

for (( initialisation ; ending condition ; update ))
do
  statements...
done
```

Cú pháp `while`:
```bash
while condition; do
  statements
done
```

Cú pháp `until`:
```bash
until condition; do
  statements
done
```

# 3. Tricks

## Set an alias
Việc này giúp bạn tiết kiệm thời gian bằng cách gõ alias để chạy một command dài nào đó thường xuyên. Ví dụ:

Chạy `nano ~/.bash_profile` và thêm dòng dưới đây vào:

```bash
$ alias dockerlogin='ssh www-data@adnan.local -p2222'  # add your alias in .bash_profile
```
Sau khi sửa bạn cần cập nhật lại:
```bash
$ source ~/.bash_profile
```
và giờ đây thay vì gõ `ssh www-data@adnan.local -p2222` thì chỉ cần fox `dockerlogin`.

## To quickly go to a specific directory

Chạy `nano ~/.bashrc` và thêm vào dòng dưới đây:

```bash
$ export hotellogs="/workspace/hotel-api/storage/logs"
```

Bây giờ, bạn cần cập nhật lại `bashrc` và việc di chuyển tới một đường dẫn dài trở nên rất đơn giản:

```bash
$ source ~/.bashrc
$ cd $hotellogs
```

## Re-execute the previous command

Cái này giúp bạn thực thi lại lệnh ngay trước đó. Bạn có thể sử dụng phím mũi tên UP cũng được. Nhưng có thể đôi khi nó vẫn hữu ích.

Để thực thi command ngay trước đó, chạy:
```bash
$ !!
```
Một lỗi phổ biến ta hay gặp đó là quên sử dụng `sudo` đối với các command cần quyền super user. Thay vì gõ lại từ đó, hãy sử dụng:
```bash
$ sudo !!
```
Nó sẽ thêm sudo vào phía trước command vừa chạy, ex: từ `mkdir somedir` thành `sudo mkdir somedir`.

## Exit traps

Làm cho các tập lệnh bash của bạn hoàn hảo hơn bằng cách thực hiện dọn dẹp một cách đáng tin cậy.

```bash
function finish {
  # các công việc dọn dẹp ở đây. vd: kill các tiến trình liên quan không cần dùng tới
  jobs -p | xargs kill
}
trap finish EXIT
```

## Saving your environment variables

Khi bạn thực thi `export FOO = BAR`, biến của bạn chỉ được lưu trong shell làm việc hiện tại. Để có thể lưu và tiếp tục sử dụng trong tương lai, bạn hãy thêm nó vào tệp `~/.bash_profile` như sau:

```bash
echo export FOO=BAR >> ~/.bash_profile # nhớ dùng hai dấu `>` để ghi append
```

## Accessing your scripts

Bạn có thể dễ dàng sử dụng các script bằng cách tạo một thư mục `bin` trong thư mục HOME của bạn với `mkdir ~/bin`. Bây giờ tất cả các script bạn để trong đó có thể sử dụng chỉ bằng cách gọi tên ở bất kỳ nơi đâu.

Nếu trong trường hợp có lỗi, hãy thử thêm code dưới đây vào cuối `~/.bash_profile` và chạy `source ~/.bash_profile` để thử lại xem sao nhé.
```bash
# set PATH so it includes user's private bin if it exists
if [ -d "$HOME/bin" ] ; then
    PATH="$HOME/bin:$PATH"
fi
```

# 4. Debugging
Bạn có thể dễ dàng debug bash script bằng cách thêm các option vào command. Ví dụ, `-n` để chỉ kiểm tra cú pháp mà không chạy command đó. `-v` để in ra command đó trước khi chạy. `-x` để in ra command đó sau khi chạy xong.

```bash
bash -n scriptname
bash -v scriptname
bash -x scriptname
```

## Contribution

- Báo lỗi [How to](https://help.github.com/articles/creating-an-issue/)
- Gửi yêu cầu cải tiến [How to](https://help.github.com/articles/about-pull-requests/)
- Lan tỏa tới mọi người

## Translation
- [English | Original](https://github.com/Idnan/bash-guide)
- [Chinese | 简体中文](https://github.com/vuuihc/bash-guide)
- [Turkish | Türkçe](https://github.com/omergulen/bash-guide)
- [Japanese | 日本語](https://github.com/itooww/bash-guide)

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
