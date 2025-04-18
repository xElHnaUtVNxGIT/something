# PicoCTF
# Lời nói đầu
Một ngày đẹp trời để bắt đầu hành trình với PicoCTF. 
Giờ thì bắt đầu thôi
# General Skill
### Easy
<details close>
<summary><b>Binary Search</b></summary>
<ul>

Đây là bài đầu tiên mình chọn để bắt đầu vì đơn giản cái tên của nó Binary Search (tìm kiếm nhị phân) một thuật toán quá quen thuộc.

Nói sơ qua về tìm kiếm nhị phân:*Tìm kiếm nhị phân dùng để tìm một số trong một dãy đã sắp xếp, nó chia dãy làm đôi nếu số cần tìm lớn hơn thì tìm bên phải, ngược lại thì tìm bên trái, cứ liên tục như thế cho đến khi tìm ra số cần tìm*
![image](https://hackmd.io/_uploads/B1vodT491e.png)

Vậy nó có mối quan hệ gì với bài này. Thử đọc mô tả thì có vẻ đây là một trò chơi mà *chúng ta phải đoán một số ngẫu nhiên từ 1->1000, chúng ta có 10 lần đoán, mỗi lần đoán chương trình sẽ cho biết số chúng ta đã đoán cao hơn hay thấp hơn số cần tìm, nếu đoán đúng sẽ lấy được flag*. Từ đề bài là Binary Search thì rõ ràng chúng ta sẽ sử dụng thuật toán tìm kiếm nhị phân để giải được trong vòng 10 lượt. (Thật ra nếu bạn may mắn thì đoán bừa cũng được)
![image](https://hackmd.io/_uploads/B1wwc649yg.png)

Như vậy, sau 9 lần thử với tìm kiếm nhị phân, mình đã tìm được flag(Thực sự là đen đấy). Biết đâu bạn có thể tìm được flag ngay từ lần thử đầu tiên thì sao :))) ai biết đc

</ul>
</details>

<details close>
<summary><b>Time Machine</b></summary>
<ul>

![image](https://hackmd.io/_uploads/HJqOjpV5Jl.png)

Sau khi tải về giải giải nén, chúng ta tìm được một file txt với nội dung:
```
This is what I was working on, but I'd need to look at my commit history to know why...
```
Kết hợp file txt này với mô tả có vẻ như nhiệm vụ của chúng ta là ngược về quá khứ để biết nội dung trước đây của file này là gì
Lúc đầu tôi cũng bối rối không biết phải làm thế nào cho đến khi nhìn thấy hint là có thể phải dùng đến git.
Đọc tài liệu về git (Gemini AI :)) tôi nhận ra có thể git log để xem lịch sử các commit (lưu thay đổi) trong một repository (kho lưu trữ).
Dùng thử luôn và lấy được flag dễ dàng
![image](https://hackmd.io/_uploads/r1lZyC45kg.png)

</ul>
</details>

<details close>
<summary><b>Super SSH</b></summary>
<ul>
![image](https://hackmd.io/_uploads/rJsP71B9Jg.png)

Mô tả nói về việc SSH rất quan trọng, nhưng có vẻ k có thông tin gì thêm, thử kết nối SSH đến lab này xem có gì xảy ra
![image](https://hackmd.io/_uploads/Byw4VJSqkg.png)
Có vẻ như bài này chỉ yêu cầu chúng ta kết nối SSH đến để lấy flag mà thôi, nếu đã từng tìm hiểu qua về SSH thì lab này không có gì khó cả
![image](https://hackmd.io/_uploads/BJkK4yrc1x.png)
Kết nối SSH đến và lấy được flag
</ul>
</details>


<details close>
<summary><b>Endianness</b></summary>
<ul>

![image](https://hackmd.io/_uploads/BJ1X16uqkx.png)
Đọc qua mô tả ngay từ đầu tôi cứ nghĩ đây là một bài OSINT nhưng không phải 
![image](https://hackmd.io/_uploads/HkOtkpuckg.png)
Yêu cầu thực sự là tìm ra biểu diễn little endian and big endian của một cụm từ cho trước 
Tìm hiểu về little endian and big endian, tôi biết rằng đây là 2 phương thức khác nhau để lưu trữ dữ liệu dạng nhị phân (binary), hiểu đơn giản ví dụ biểu diễn từ "123"
* Đầu tiên, 123 chuyển sang hệ thập phân lần lượt là 48 49 50
* Sau đó, chuyển sang hệ Hex là 31 32 33

Lúc này little endian sẽ biểu diễn là
```
33 32 31
````
Còn big endian sẽ biểu diễn là
```
31 32 33
```
Về cơ bản biểu diễn big endian là ngược lại của little endian.

Bài có cho source nhưng mà dài quá nên tôi cũng lười đọc, vứt vào một con chat bot bất kì và nghe nó giải thích qua đoạn code thì có vẻ như chúng ta đã đi đúng hướng, việc cần làm bây giờ chỉ là vận dụng, dùng một công cụ bất kì trên mạng để chuyển từ chuỗi sang hex và lấy flag mà thôi 
![image](https://hackmd.io/_uploads/Bk86f6u5yg.png)

</ul>
</details>

<details close>
<summary><b>Big Zip</b></summary>
<ul>

![image](https://hackmd.io/_uploads/BJOHFad9yx.png)
Chưa biết bài này định làm gì, cứ thử tải xuống trước đã
![image](https://hackmd.io/_uploads/ByXKtp_91g.png)
Giải nén xong được một đống file trông rất kinh khủng trong đó có cả file thư mục và txt 
Mở thử vài file txt để đọc xem có thông tin gì không
![image](https://hackmd.io/_uploads/HJJW9pd9ke.png)
Có vẻ như ta sẽ phải đi tìm flag trong đống này, tôi sẽ dùng grep để tìm kiếm cụm từ "picoCTF"
![image](https://hackmd.io/_uploads/Hk_qqTu5Jx.png)
Đã lấy được flag
</ul>
</details>

<details close>
<summary><b>Commitment Issues</b></summary>
<ul>

![image](https://hackmd.io/_uploads/HyAZFnucJx.png)
Lí do tôi chọn bài này vì cơ bản trông nó khá là quen, khá giống với time machine nên tôi ấn vào
Mở file txt ban đầu lên để kiểm tra
![image](https://hackmd.io/_uploads/ByCiKnOc1g.png)
Trông khá giống time machine nên sẽ thử các bước tương tự time machine
Bước đầu tiên, cũng thử dùng git log để xem có bản ghi nào được chỉnh sửa hay không
![image](https://hackmd.io/_uploads/S1cbch_q1x.png)
Đúng như dự đoán có 2 bản ghi, bản ghi đầu tiên chứa thông tin để tạo flag, còn bản ghi thứ 2 dùng để xóa flag
Do vậy, có thể dùng git checkout để khôi phục lại bản ghi trước đó dựa vào commit id chúng ta tìm đc khi dùng git log và lấy đc flag
![image](https://hackmd.io/_uploads/HJilohd5kg.png)
</ul>
</details>

<details close>
<summary><b>Repetitions</b></summary>
<ul>

![image](https://hackmd.io/_uploads/BJxE36d5Jg.png)
Mô tả không cho chúng ta quá nhiều thông tin, vậy thì tải về xem nó là gì
![image](https://hackmd.io/_uploads/HkePn6OcJg.png)
Mở file tải về cho chúng ta một chuỗi loằng ngoằng có vẻ như đã được mã hóa, cùng với thông tin kết thúc bằng 2 dấu bằng rất có thể đây là một file mã hóa bằng base64
Sử dụng một công cụ giải mã base64 
![image](https://hackmd.io/_uploads/Hyu4p6u9yg.png)
Vẫn chưa có ý nghĩa, lúc này tôi nghĩ có thể đã đi sai hướng, nên quay lại đề bài để tìm kiếm thêm gợi ý
Thật may vẫn là base64, ý tưởng ban đầu vẫn đúng
![image](https://hackmd.io/_uploads/SyCnTpu5ke.png)
Kết hợp cùng hint mã hóa nhiều lần luôn tốt mà, tôi đã hiểu ra
Có vẻ như khi ta giải mã base của chuỗi ban đầu sẽ là một chuỗi base64 khác, thực hiện giải mã nhiều lần, chúng ta sẽ tìm được flag 
![image](https://hackmd.io/_uploads/HypF0pd9ye.png)
</ul>
</details>

<details close>
<summary><b>First Find</b></summary>
<ul>

![image](https://hackmd.io/_uploads/HJJ_J0ucJe.png)
Có vẻ như lại là một bài tìm kiếm khác
![image](https://hackmd.io/_uploads/BJo910uq1l.png)
Trông số lượng file không quá nhiều(Big Zip trông còn kinh khủng hơn)
Cách thức lấy được cờ tương tự Big zip thôi (thật ra trông khá ít files nếu rảnh có thể tìm bằng cơm cũng được)
![image](https://hackmd.io/_uploads/rkvllCO9yg.png)
</ul>
</details>


### Medium
<details close>
<summary><b>Dont-you-love-banners</b></summary>
<ul>

![image](https://hackmd.io/_uploads/ryO9H0dc1e.png)
Sau những ngày vờn nhau với bài dễ thì tôi muốn thử sức với một bài ở độ khó cao hơn, lí do tôi chọn bài này vì nó có đến 8k submit tức là khá nhiều người đã hoàn thành nên có vẻ độ khó cũng không quá cao :)) (Thật ra là cũng khó)
![image](https://hackmd.io/_uploads/SJuQUROqyg.png)
Bỏ qua thông tin về dữ liệu bị lộ trên cổng 62321, ta cứ thử netcat vào cổng 59425 xem có gì 
![image](https://hackmd.io/_uploads/Hy9jLCuqJe.png)
Yêu cầu mật khẩu :)) có vẻ như việc bỏ qua thông tin trên cổng 62321 là một quyết định sai lầm, thử netcat vào cổng đó xem sao
![image](https://hackmd.io/_uploads/HymzDA_ckx.png)
Có vẻ như chúng ta đã có password, lúc này tôi tưởng bài đã kết thúc, nhưng không, đây là một bài ở độ khó medium, sao có thể dễ dàng kết thúc như thế được :))
![image](https://hackmd.io/_uploads/HkpYvCuckg.png)
Mặc dù có mật khẩu nhưng ta vẫn cần trả lời các câu hỏi khác, không có thông tin gì. Lúc này tôi hơi bối rối, thử tìm kiếm gợi ý xem có thông tin gì không và cái kết là không. Một gợi ý liên quan đến syslink còn một gợi ý về mật khẩu. 
Chúng ta đã tìm được mật khẩu nên gợi ý mật khẩu là không cần thiết, vậy syslink có liên quan gì, tí nữa sẽ rõ
Còn về câu chuyện về câu hỏi, có vẻ như chỉ là một câu hỏi thông tin bình thường có vẻ là tôi đã quá overthinking :))) vậy là tôi bắt đầu tìm kiếm trên Internet về câu hỏi trên và tìm được top 10 hội nghị
![image](https://hackmd.io/_uploads/HksnYRd51x.png)
Thử từng cái và tìm được đáp án là Def Con và tiện tay tìm luôn câu hỏi thứ 3 về hacker đầu tiên biết đến phreaking 
Lúc này ta lấy được một shell, cùng thử xem chúng ta là ai
![image](https://hackmd.io/_uploads/Bk3EqAOq1e.png)
Chúng ta đang là player, giờ hãy kiểm tra xem chúng ta có gì ở đây
![image](https://hackmd.io/_uploads/BkiYq0O51l.png)
Có vẻ như ở đây có 2 tệp và một vài tệp và thư mục ẩn, banner với player là chủ sở hữu, còn text là của root, kiểm tra xem 2 tệp kia có gì
![image](https://hackmd.io/_uploads/Sy5Bj0_9kx.png)
Có vẻ như là một cái banner và một cái gì đấy, cái banner này còn trông khá quen :)))
Tạm bỏ qua cái banner đấy, ta phi luôn đến file /root để lấy flag 
![image](https://hackmd.io/_uploads/S1qfnAuqJe.png)
Nhưng đời vả bôm bốp vào mặt, nào có dễ xơi như thế, vậy làm sao để lấy được flag.
Do không thể lấy được flag ngay nên thử kiểm tra xem trong script.py có gì 
```
import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt
```
Ái chà, có vẻ đây chính là trò chơi ban đầu để xác thực kết nối, trông code python cũng đỡ tởm và dễ đọc hơn. Nội dung thì chính là thứ chúng ta đã chơi để xác thực kết nối
Nhưng có một đoạn đáng chú ý
```
try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")
```
Có vẻ như đoạn này cho phép hiển thị ra banner thông qua đường dẫn /home/player/banner mà chủ sở hữu của file banner là ai? là player. Do vậy có thể tận dụng điều này để hiển thị một file bất kì
Việc chúng ta nghĩ tới sẽ là làm sao để có thể thay thế file banner thành flag.txt để khi khởi tạo kết nối script.py được chạy sẽ hiển thị flag
Nhưng làm thế nào? nhớ lại gợi ý 1 về syslink ở trên, cùng thử tìm hiểu xem syslink là gì? 
*Syslink là một loại tệp đặc biệt đóng vai trò như một "phím tắt" trỏ đến một tệp hoặc thư mục khác.*
Khá giống với shortcut trên windows nhưng syslink lại được xử lý bởi kernel
![image](https://hackmd.io/_uploads/B1Z1b1F9kg.png)
Lúc này chỉ cần khởi tạo lại kết nối, là bú được em flag thơm phức
![image](https://hackmd.io/_uploads/r1Fz-1tqye.png)
Ngoài ra, có thể vọc thêm mấy file ẩn, khá nhiều thông tin, nhưng tôi đọc không hiểu nên là thôi, dù gì cũng lấy được flag rồi :))
</ul>
</details>

### Hard

# Forensics
### Easy
<details close>
<summary><b>Scan Surprise</b></summary>
<ul>

![image](https://hackmd.io/_uploads/Sytxwyrc1g.png)

Đọc mô tả có vẻ như đây là một lab mà flag sẽ được cho dưới dạng ảnh
![image](https://hackmd.io/_uploads/BkBIvJBcyx.png)

Sau quá trình tải xuống giải nén, rồi bật nó lên, chúng ta tìm được flag là một mã qr.
Dùng công cụ quét mã QR bất kì (Điện thoại cũng được) ta đã lấy được flag
</ul>
</details>

<details close>
<summary><b>Verity</b></summary>
<ul>

![image](https://hackmd.io/_uploads/Sk5I92K91g.png)
Đọc qua mô tả, có vẻ như chúng ta sẽ phải sử dụng một file hàm băm cho trước để tìm flag, tạm thời thế đã thử kết nối ssh đến trang xem có gì ở đó 
![image](https://hackmd.io/_uploads/Sy7gjhY9Jl.png)
Chúng ta có một file checksum có thể xem nhưng không sửa được, có một file decrypt có thể thực thi để giải mã một cái gì đó, và files bên trong chứa rất nhiều thư mục có vẻ đã được mã hóa 
![image](https://hackmd.io/_uploads/Sy2f3nt9Jg.png)
Đọc mô tả ta có thể xác thực một file bằng cách thực hiện lệnh sau:
```
./decrypt.sh files/<file>
```
Vậy nhiệm vụ của chúng ta là đi tìm flag trong đống khủng khiếp ở /files/*
Nếu thực hiện thủ công thì cũng là một phương án, nhưng khá chắc là sẽ rất lâu, chính vì vậy chúng ta cần tìm ra một phương án giúp tự động hóa. 
Việc cần làm bây giờ là viết một đoạn script để máy tính thực hiện tự động công việc thay cho chúng ta. Sử dụng vòng lặp for
![image](https://hackmd.io/_uploads/HyTS6nY9kx.png)
Trông hơi kinh tởm nhỉ, đến đây có thể đi tìm flag dễ dàng hơn rồi, nhưng để nó dễ dàng hơn nữa sao ta không grep với từ khóa "pico" để lọc bớt output thừa
![image](https://hackmd.io/_uploads/BJopanKqJx.png)
Trông đỡ kinh hơn một xíu, kéo xuống dưới và lấy được flag
![image](https://hackmd.io/_uploads/rkFgCnK51e.png)
Note: thật ra tôi muốn lọc bớt cho sạch hẳn cơ nhưng lỗi "bad magic number" vẫn xuất hiện, có lẽ là do không chỉ định trình thông dịch #!/bin/bash nên bị lỗi vậy, không chắc nữa. Với trình độ hạn hẹp của tôi thì kéo chuột một tí cũng tạm chấp nhận đc :)) thế thôi
</ul>
</details>


### Medium

### Hard