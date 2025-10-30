**Phan Thị Hồng Huế - Tuần 2**


## Phần 1: Giới thiệu tổng quan về Linux

1. **Linux là gì?**

   - Khái niệm: Linux là một hệ điều hành (OS) mã nguồn mở, do Linus Torvalds tạo ra vào năm 1991 và được cộng đồng phát triển thành một trong những OS phổ biến nhất hiện nay.

   - Phân biệt giữa Linux kernel và các bản phân phối (Ubuntu, CentOS, Debian...).
   
     - Linux distro – hay bản phân phối Linux là giLinux distro là các hệ điều hành được phát triển dựa trên nhân Linux. Nó có vai trò đóng gói nhân Linux cùng với các phần mềm và tiện ích cần thiết, tạo thành một hệ điều hành hoàn chỉnh mà mà người dùng có thể cài đặt và khởi chạy. 

| Tên | Khái niệm | Ưu điểm | Nhược điểm |
|---------------|-------------|----------|------------|
Linux kernel|Lõi của hệ điều hành Linux, quản lý phần cứng, bộ nhớ, tiến trình và hệ thống tập tin.|Nhẹ, hiệu suất cao, ổn định, có thể tùy chỉnh.| Không có giao diện người dùng, cần các bản phân phối để sử dụng đầy đủ.
Ubuntu |Bản phân phối phổ biến, thân thiện với người mới, dựa trên Debian | Giao diện thân thiện, dễ sử dụng, hỗ trợ phần cứng tốt, cộng đồng lớn. | Tích hợp nhiều gói phần mềm mặc định khiến hệ thống trở nên nặng nề với cấu hình thấp.
CentOS |Bản phân phối ổn định, miễn phí, gần giống Red Hat.Ổn định, thích hợp cho server, chu kỳ nâng cấp dài.|Ổn định, thích hợp cho server, chu kỳ nâng cấp dài.|Một số phiên bản đã EOL, hỗ trợ phần mềm mới hạn chế.

=> **Kết luận**: 
- Linux Kernel: Lõi của hệ điều hành, quản lý phần cứng và tài nguyên.
- Bản phân phối (Distro): Ubuntu, CentOS, Debian… cung cấp giao diện, trình quản lý gói, phần mềm sẵn có.

2. **Tại sao nên học Linux**

   - **Ứng dụng rộng rãi trong server, cloud, DevOps, AI, lập trình hệ thống**.
     - Server: 
       - Ổn định, hiệu suất cao, khả năng xử lý đa luồng và khối lượng công việc lớn.
       - Hỗ trợ: Web server, Database server, Email server, Cloud server
       - VD: Ubuntu server
      - Cloud: 
        - Xây dựng và quản lý cơ sở hạ tầng đám mây, chạy VM, container, microservices.
        - Tính năng: khả năng mở rộng (scalability), linh hoạt (flexibility), xử lý đồng thời nhiều tiến trình/luồng.
        - VD: Amazon Web Services (AWS), Google Cloud Platform (GCP), Microsoft Azure.
    
     - DevOps
       - Tự động hóa triển khai, quản lý server, CI/CD, container orchestration.
       - Công cụ: Docker, Kubernetes, Jenkins, Ansible, GitLab CI.
       - VD: Triển khai ứng dụng web tự động, quản lý hạ tầng bằng Infrastructure as Code (IaC)
     - AI/Machine Learning
       - Chạy các framework AI/ML, xử lý dữ liệu lớn, tận dụng GPU/CPU đa luồng.
       - Công cụ: TensorFlow, PyTorch, Hadoop, Spark.
       - VD: Mô hình học sâu (Deep Learning) trên server Linux với GPU.

   - **Sự khác biệt giữa Linux và Windows/macOS**.
   

    | **Tiêu chí** | **Linux** | **Windows** | **macOS** |
    |---------------|------------|--------------|------------|
    | **Tính chất mã nguồn** | Mã nguồn mở, người dùng có quyền truy cập, thay đổi và phân phối lại mã nguồn. | Mã nguồn đóng, phát triển độc quyền bởi Microsoft. | Mã nguồn đóng, phát triển độc quyền bởi Apple, dựa trên nền Unix. |
    | **Bảo mật** | Bảo mật cao nhờ cơ chế phân quyền và cập nhật nhanh; ít bị tấn công hơn do thị phần nhỏ. | Thường là mục tiêu của phần mềm độc hại do thị phần lớn hơn. | Bảo mật tốt, được Apple kiểm soát chặt chẽ cả phần mềm và phần cứng. |
    | **Quản lý tài nguyên** | Hoạt động tốt trên phần cứng yếu, sử dụng ít tài nguyên hệ thống. | Tiêu thụ nhiều tài nguyên, đặc biệt trên hệ thống cấu hình thấp. | Tối ưu tốt trên phần cứng Apple, hiệu suất ổn định nhưng khó cài trên máy khác (hackintosh). |
    | **Cập nhật hệ thống** | Rolling-release hoặc fixed-release, không yêu cầu khởi động lại khi cập nhật. | Cập nhật bắt buộc, thường yêu cầu khởi động lại, đôi khi gây gián đoạn công việc. | Cập nhật định kỳ, ổn định, thường yêu cầu khởi động lại nhưng ít gây lỗi. |
    | **Cộng đồng hỗ trợ** | Cộng đồng mã nguồn mở lớn, hỗ trợ từ diễn đàn, wiki, GitHub. | Hỗ trợ chính thức từ Microsoft và cộng đồng người dùng rộng. | Hỗ trợ chính thức từ Apple, cộng đồng nhỏ hơn, ít tự do phát triển. |
    | **Khả năng tùy chỉnh** | Tùy chỉnh cao, có thể thay đổi từ kernel đến giao diện người dùng. | Giới hạn tùy chỉnh, chủ yếu thông qua các thiết lập sẵn. | Hạn chế tùy chỉnh, ưu tiên trải nghiệm người dùng đồng nhất và ổn định. |
    | **Ứng dụng và phần mềm** | Nhiều phần mềm mã nguồn mở; cần Wine hoặc máy ảo để chạy ứng dụng Windows. | Nhiều phần mềm thương mại, phổ biến trong doanh nghiệp. | Hỗ trợ tốt cho thiết kế đồ họa, âm nhạc, lập trình iOS; ít phần mềm game. |
    | **Phù hợp cho máy chủ** | Phổ biến cho máy chủ web và doanh nghiệp nhờ tính ổn định, bảo mật cao. | Windows Server được dùng trong doanh nghiệp lớn, tích hợp tốt với hệ sinh thái Microsoft. | Ít được dùng cho máy chủ, chủ yếu trong môi trường phát triển macOS/iOS. |
    | **Giá thành** | Miễn phí, hầu hết các bản phân phối không có phí bản quyền. | Phải trả phí bản quyền cho hệ điều hành và phần mềm như Office. | Tính trong giá phần cứng Apple, không bán riêng hệ điều hành. |
    | **Bảo trì hệ thống** | Bảo trì đơn giản, cập nhật linh hoạt, không cần khởi động lại thường xuyên. | Bảo trì phức tạp hơn, cập nhật tự động đôi khi gây lỗi. | Bảo trì dễ dàng, Apple kiểm soát toàn bộ quy trình cập nhật. |
    | **Thị phần và độ phổ biến** | Phổ biến trong server, hệ thống nhúng, môi trường lập trình. | Chiếm thị phần lớn nhất trong máy tính cá nhân. | Phổ biến trong lĩnh vực sáng tạo (thiết kế, âm nhạc, media). |

   
   - **Ưu điểm: bảo mật, miễn phí, tùy biến, hiệu suất cao.**
     + **Mã nguồn mở và miễn phí**: Phần mềm mã nguồn mở cho phép bất kỳ ai cũng có thể đóng góp, chỉnh sửa và cải thiện mã nguồn. Ngoài ra, người dùng có thể tải xuống và sử dụng miễn phí.
     + **Khả năng tùy chỉnh và linh hoạt**: Người dùng có thể linh hoạt trong việc chỉnh sửa hệ điều hành theo nhu cầu của mình. Linux có nhiều bản phân phối, bao gồm Fedora, Ubuntu, Arch Linux, Debian, Linux Mint và các bản phân phối khác. Các bản phân phối này cung cấp cho người dùng nhiều tùy chọn tính năng hơn.
     + **Bảo mật cao**: Quản trị viên phải nhập mật khẩu để cấp quyền cho từng chương trình trong ứng dụng. Linux giảm thiểu khả năng phần mềm độc hại được thực thi theo cách này.
     + **Độ ổn định và tin cậy**: Linux có thể xử lý công việc với khối lượng lớn mà không ảnh hướng đến hiệu suất và được thiết kế để chạy trong thời gian dài mà không cần khởi động lại.
     + **Hỗ trợ cho máy cấu hình yếu**: Linux vẫn hỗ trợ cập nhật, nâng cấp thường xuyên với các máy có cấu hình yếu trong khi sử dụng.
     + **Hiệu suất cao**: Linux quản lý tài nguyên hệ thống hiệu quả, tiêu tốn ít bộ nhớ và CPU hơn so với nhiều hệ điều hành khác, phù hợp với server, máy chủ, và các môi trường cần chạy liên tục với tải nặng.

3. **Kiến trúc hệ thống Linux**
   - Cấu trúc: 3 thành phần chính:
      + **Kernel (Nhân)**: Là phần quan trọng nhất trong Linux, có nhiệm vụ quản lý các tài nguyên của phần cứng như bộ nhớ, module, bộ vi xử lý… và giúp phần cứng có thể giao tiếp với các ứng dụng trên hệ điều hành.
      + **Shell**: Là nơi chứa và thực thi các dòng lệnh được yêu cầu đến cho Kernel xử lý từ người dùng hoặc ứng dụng. Đây được xem là cầu nối giữa Application và Kernel.
      + **Application**: Là các ứng dụng hoặc tiện ích được người dùng cài đặt và chạy trên server để phục vụ nhu cầu sử dụng (Ví dụ: Proxy, Samba và FTP…).

    ![Commit graph](images/hoatdongLinux.png)
    
   - **Quá trình khởi động (boot process) cơ bản**.
   
   - **Các thư mục hệ thống chính (`/bin`, `/etc`, `/home`, `/usr`, `/var`...).**
     - `root`: Thư mục cá nhân (home directory) của người dùng root (quản trị viên hệ thống). Nó được tách biệt khỏi /home để đảm bảo quyền truy cập và bảo mật. Ví dụ: `/root/.ssh`
     - `/bin`: Chứa các chương trình thực thi. Các chương trình chung của Linux được sử dụng bởi tất cả người dùng được lưu ở đây. Ví dụ như: `ps, ls, ping...`
     - `/etc`:Chứa các file cấu hình của các chương trình, đồng thời nó còn chứa các shell script dùng để khởi động hoặc tắt các chương trình khác. Ví dụ: `/etc/resolv.conf, /etc/logrolate.conf`
     - `home`: Chứa tất cả các file cá nhân của từng người dùng. Ví dụ: `/home/john, /home/marie`
     - `/usr`: Chứa các thư viện, file thực thi, tài liệu hướng dẫn và mã nguồn cho chương trình chạy ở level 2 của hệ thống.
     - `/var`: Thông tin về các biến của hệ thống được lưu trong thư mục này. Như thông tin về log file: `/var/log`, các gói và cơ sở dữ liệu `/var/lib..`
     - `/dev`: Các file thiết bị, không phải là các file dữ liệu thông thường mà là giao diện để truy cập các thiết bị phần cứng (ví dụ: ổ đĩa cứng, thiết bị đầu cuối). Ví dụ: `/dev/sda (ổ đĩa cứng đầu tiên), /dev/null (thiết bị ảo), /dev/tty`
     - `/lib`: Chứa các thư viện (shared libraries) thiết yếu cho các chương trình nhị phân trong `/bin` và `/sbin.`
     - `/tmp `: Chứa các file tạm thời (temporary files) được tạo ra bởi các chương trình và người dùng. Nội dung của thư mục này thường bị xóa khi hệ thống khởi động lại.
     - `/proc `: Chứa các file hệ thống ảo (virtual filesystem), cung cấp thông tin về tiến trình (processes) và kernel (nhân) của hệ thống đang chạy. Các file này được tạo ra trong bộ nhớ.
     - `/media`: Chứa các thiết bị như CdRom /media/cdrom. floppy /media/floopy hay các phân vùng đĩa cứng /media/Data 
   
   ![Thư mục Linux](images/thumuclinux.png)

---

## Phần 2: Làm quen với Terminal và Shell

4. **Terminal & Shell là gì**

   - Terminal: giao diện dòng lệnh (CLI), cung cấp một cửa sổ để bạn nhập và xem kết quả của các lệnh. Terminal không trực tiếp hiểu lệnh, mà chỉ chuyển lệnh đến Shell để xử lý.
   - Shell: là chương trình xử lý lệnh – nhận lệnh từ Terminal, thông dịch rồi gửi yêu cầu cho Kernel (nhân hệ điều hành) để thực thi. Sau khi Kernel xử lý xong, Shell nhận kết quả và gửi trả lại Terminal.
   - Mở terminal, chạy lệnh cơ bản.
   ![Terminal](images/terminal.png)

5. **Lệnh cơ bản trong Linux**

   - `pwd`, `ls`, `cd`, `clear`, `history`.
     - `pwd`: in ra 
     - `ls`: liệt kê nội dung các thư mục
       - `ls -l /` : hiển thị nội dung dạng danh sách
       - `ls -a /` hiển thị các file thư mục ẩn
       - `ls -t /` sắp xếp lại theo thứ tự mới nhất đến cũ nhất
       - ls -lta: gọp 3 câu lệnh trên
    
       ![Câu lệnh](images/terminal.png)

     - `cd`: di chuyển giữa các thư mục
     - `clear`: xóa sạch màn hình terminal
     - `history`: hiển thị lịch sử các lệnh dã dùng
     
     ![Lệnh](images/cd.png)
   - Sử dụng phím tắt: `Tab`, `Ctrl + C`, `Ctrl + D`.
     - `Tab`: tự động hoàn thành tên lệnh, tên file, thư mục..
     - `Ctrl + C`: hủy tiến trình đang chạy
     - `Ctrl + D`: đóng terminal hoặc thoát cell

6. **Hiểu cấu trúc đường dẫn**
   - Đường dẫn tuyệt đối vs tương đối.
     - Đường dẫn tuyệt đối: là đường dẫn đầy đủ bắt dầu từ thu mục gốc, không phụ thuộc vào vị trí hiện tại.
     - Đường dẫn tương đối: là đường dẫn tính từ thư mục hiên tại, không bắt đầu bằng `/`
   - Dấu `~`, `.`, `..` ý nghĩa và cách dùng.
     - `~`: thư mục **home** của người dùng hiện tại
     - `.`: thư mục hiện tại
     - `..`: thư mục cha
---

## Phần 3: Làm việc với file và thư mục

7. **Tạo, xem, xóa và di chuyển file**

   - `touch`, `cat`, `less`, `head`, `tail`.
     - `touch `: tạo 1 file mới 
     -  `cat`: hiển thị nội dung file ra ngoài màn hình
     -  `less`: xem nội dung dài
     -  `head`: hiện thị những dòng đầu của file
     -  `tail`: hiển thị những dòng cuối của file
    
       ![File](images/file.png)

   - `cp`, `mv`, `rm`, `mkdir`, `rmdir`.
     - `cp`: sao chép file/ thư mục
     - `mv`: di chuyển file/thư mục
     - `rm`: xóa file hoặc thư mục
     - `mkdir`: tạo thư mục mới
     - `rmdir`: xóa thư mục trống

    ![File](images/file2.png)

8. **Sao chép và nén file**

   - `tar`, `gzip`, `zip`, `unzip`, `scp`.
     - `tar`: Đóng gói và giải nén nhiều file/thư mục:
       - `c`: create - tạo file nén `.tar`
       - `x`: extract - giải nén
       - `v`: verbose: hiển thị chi tiết quá trình
       - `f`: file - chỉ định tên file nén.
       - `-z`: nén bằng `gzip`
       
    ![Tar](images/tar.png)

     - `gzip`: Nén và giải nén file đơn lẻ
     - `zip`: nén theo định dạng `zip`
     - `unzip`: giải nén theo định dạng `zip`
     - `scp`: Sao chép file giữa các máy qua SSH
    
    ![scp](images/scp.png)
     
   -  Giải thích khái niệm stream (`stdin`, `stdout`, `stderr`).
        - `stdin`: Standard Input - Dữ liệu nhập (thường là bàn phím)
        - `stdout`: Standard Output - Dữ liệu xuất ra (thường là màn hình)
        - `stderr`: Standard Error - Dòng lỗi của chương trình

9. **Tìm kiếm file**
   - `find`, `locate`, `grep`.
     - `find`: Tìm file trong hệ thống
     - `locate`:tìm nhanh
     - `grep`: tìm chuỗi trong file
   - Kết hợp `grep` với `pipe (|)`.

---

## Phần 4: Quyền truy cập và người dùng

10. **Người dùng và nhóm (User & Group)**

    - `whoami`, `id`, `adduser`, `deluser`.
    - `su`, `sudo`, `/etc/passwd`.

11. **Phân quyền file**

    - `ls -l`, quyền đọc/ghi/thực thi (`rwx`).
    - `chmod`, `chown`, `chgrp`.

12. **Quyền root và an toàn**
    - Tại sao không nên chạy mọi thứ bằng root.
      - Tài khoản **root** (còn gọi là superuser) là tài khoản người dùng có đặc quyền cao nhất trên hệ thống. Nó được thiết kế để thực hiện các tác vụ quản trị hệ thống quan trọng
      - Không nên chạy mọi thứ bằng **root**:
        - **Rủi ro bảo mật cao**: Nếu chạy chương trình bằng quyền root, bất kỳ lỗ hổng hoặc mã độc nào trong chương trình đó cũng có thể kiểm soát toàn bộ hệ thống.
        - Vi phạm nguyên tắc **“nguyên tắc đặc quyền tối thiểu”** (Principle of Least Privilege) — chỉ cấp quyền cần thiết để hạn chế thiệt hại khi có sự cố.
        - **Lỗi người dùng có thể gây hại lớn**: Một thao tác sai (ví dụ: xóa nhầm file hệ thống, ghi đè cấu hình quan trọng) có thể khiến hệ thống bị hỏng hoàn toàn.
        - **Giảm khả năng kiểm soát và phân quyền**: Việc luôn dùng root khiến khó theo dõi ai đã thực hiện hành động nào, gây khó khăn cho quản lý và bảo mật.
    - Phân biệt `sudo` và `su`.
      - `Sudo` là một cơ chế quản lý quyền, phụ thuộc vào /etc/sudoers, để cho phép người dùng thực hiện một số lệnh quản trị với quyền root hoặc quyền của người dùng khác mà không cần đăng nhập trực tiếp vào tài khoản đó. Khi dùng sudo, người dùng nhập mật khẩu của chính mình.
      - `su`: (viết tắt của substitute user hoặc switch user) được dùng để chuyển đổi sang tài khoản khác (thường là root) bằng cách nhập mật khẩu của tài khoản đích. Nó mở một phiên shell mới với quyền của người dùng đó cho đến khi thoát ra (exit).

---

## Phần 5: Quản lý tiến trình và hệ thống

13. **Quản lý tiến trình (process)**

    - `ps`: liệt kê các dòng lệnh đang chạy.
    - `top`: theo dõi tiến trình đang chạy theo thời gian thực, sắp xếp theo mức sử dụng CPU. Cung cấp cái nhìn động về tải hệ thống.
    - `htop`: phiên bản cải tiến hơn của `top` hỗ trợ thao tác bằng chuột và hiển thị đồ họa dễ nhìn.
    -  `kill`: Gửi tín hiệu tới một tiến trình dựa trên PID (Process ID)
    -  `killall`. Gửi tín hiệu tới các tiến trình dựa trên tên tiến trình (process name).
    
    - **Foreground và background process (`&`, `fg`, `bg`).**
      - **Foreground**: Tiến trình chạy trực tiếp, chiếm quyền điều khiển terminal, phải chờ lệnh hoàn thành hoặc nhấn Ctrl+C để dừng.
      - **Background** : Tiến trình chạy ngầm, không chiếm quyền điều khiển terminal, cho phép tiếp tục thực hiện các lệnh khác.

14. **Kiểm tra tài nguyên hệ thống**

    - `df`, `du`, `free`, `uptime`, `uname`, `lscpu`, `lsblk`.

15. **Dịch vụ và tiến trình nền (daemon)**
    - `systemctl`, `service`, `journalctl`.
    - Start/stop/restart dịch vụ.

---

## Phần 6: Quản lý gói phần mềm

16. **Trình quản lý gói (Package Manager)**

    - Debian/Ubuntu: `apt`, `apt-get`.
    - RedHat/CentOS: `yum`, `dnf`.

17. **Cài đặt và gỡ bỏ phần mềm**

    - `sudo apt install`, `sudo apt remove`, `apt update`, `apt upgrade`.
    - Kiểm tra package đang cài đặt: `dpkg -l`.

18. **Tạo và sử dụng alias**
    - Tạo lệnh tắt trong file `~/.bashrc`.
    - `alias ll='ls -alF'`.

---

## Phần 7: Làm việc với mạng (Networking)

19. **Lệnh kiểm tra mạng**

    - `ping`
    - `ifconfig`
    - `ip addr`
    - `netstat`
    - `ss`
    - `curl`
    - `wget`.

20. **Kết nối SSH và truyền file**

    - `ssh user@ip`
    - `scp`
    - `rsync`
    - Thiết lập SSH key (`ssh-keygen`, `ssh-copy-id`).

21. **Kiểm tra cổng và firewall**
    - `ufw`, `iptables`, `ss -tuln`.

---

## Phần 8: Script & Automation cơ bản

22. **Shell Script là gì**

    - File `.sh`, cú pháp `#!/bin/bash`.
    - Cách chạy: `bash script.sh` hoặc `chmod +x script.sh`.

23. **Biến, vòng lặp và điều kiện**

    - `if`, `for`, `while`, biến môi trường (`$USER`, `$HOME`).

24. **Tự động hóa tác vụ**
    - `cron`, `crontab -e`.
    - Lên lịch chạy script.

---

## Phần 9: Thực hành tổng hợp

25. **Bài tập thực tế**
    - Tạo user mới, cấp quyền hạn chế.
    - Tạo và nén backup thư mục.
    - Viết script tự động sao lưu log hệ thống hàng ngày.
    - Dò tìm file lớn nhất trong thư mục home.
    - Cấu hình SSH và kiểm tra kết nối.

---