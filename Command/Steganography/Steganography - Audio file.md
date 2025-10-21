# Steganography - File âm thanh

* Với Forensic dạng Steganography - file âm thanh thì mục tiêu cần tìm flag gồm:
  + Xác định được file âm thanh đó có thật sự là file âm thanh không hay file âm thanh giả.
  + Khi xác định được flie âm thanh tiếp theo cần phải làm gì để có được thông tin từ file âm thanh.
* Tôi sẽ ví dụ cho các bạn về dạng Steganography - file âm thanh :

    <img width="1716" height="810" alt="image" src="https://github.com/user-attachments/assets/f7db2921-7d07-4833-a65b-8468c307c075" />

- Như các bạn đã thấy ở đây cho sẽ có 1 file âm thanh chứa flag trong đó. Khi các bạn chơi CTF như này thì đầu tiên phải xác định được file âm thanh này là thật hay chứa đựng một file nào đó ở phía sau file âm thanh này không.
- Đầu tiên để xác định được file âm thanh này tôi sẽ sử dụng lệnh:

    <pre> file (file) </pre>

  + Lệnh file này được sử dụng rất nhiều trong tất cả các dạng về Forensic. Nó được ví như là lệnh để xác định được đó là file gì.
  + Ở đây file âm thanh của mình hiện tại là `aline.wav` thì mình sẽ xác định file này bằng lệnh `file`:
 
    <pre> file aline.wav </pre>
 
    <img width="783" height="74" alt="image" src="https://github.com/user-attachments/assets/03ae1898-bf3d-448a-a542-c0506feadbe4" />

    Như các bạn đã thấy khi mình sử dụng lệnh `file` thì lệnh này sẽ xác định cho các bạn thấy file âm thanh `aline.wav` này là:
    
    <pre> alien.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 22050 Hz </pre>

    Bao gòm cả `RIFF (little-endian) data` và `Ware audio` thì chứng tỏ file này là file `aline.wav` thật.

- Tiếp theo, khi chúng ta đã xác định file `aline.wav` này rồi thì chúng ta sẽ tạo 1 file từ file `aline.wav` bằng lệnh:

  <pre>  sox (file âm thanh) -n spectrogram -o (tên file cần tạo).png </pre>   

  + Thực tế lệnh `sox` dùng để xử lí âm thanh và có thể chuyển đổi, ghi âm, chỉnh sữa, phân tích, tạo hiệu ứng cho file âm thanh.
  + `-n` ở đây gọi là không tạo file âm thanh đầu ra. Tức là các bạn chỉ muốn tạo ảnh phổ tần só `spectrogram` từ đó các bạn không cần phải xuất lại 1 file âm thanh mới.
  + `spectrogram` được gọi là hiển thị tần số của âm thanh theo thời gian. Ví dụ như trục tọa độ trong toán học Oxy vậy:
      + Trục x: Thời gian
      + Trục y: Tần số
      + Màu sắc(O): Cường độ âm
  - Từ đó `spectrogram` có thể giúp các bạn thấy âm thanh có chứa tần cao/thấp. Ngoài ra, còn có thể thấy thông tin trong file âm thanh đó.
  + `-o .... .png` là dùng để đặt tên hoặc lưu tên file ảnh từ file ảnh.
  + Tiếp tục với file `aline.wav` các bạn sẽ sử dụng lệnh này:

    <pre> sox alien.wav -n spectrogram -o image.png  </pre>

    Khi các bạn sử dụng lệnh `sox` xong thì lập tức nó sẽ tạo 1 file `image.png`
  + Tiếp theo, khi các bạn đã tạo xong file `image.png` như này thì các bạn sẽ mở file ảnh băng lệnh:
 
    <pre> 
      xdg-open
      eog
      feh
      sqlite3</pre>

      Đây sẽ là những lệnh giúp các bạn xem được file `image.png` các bạn vừa tạo từ file `aline.wav`

    <img width="455" height="49" alt="image" src="https://github.com/user-attachments/assets/7f65c2e4-0d31-45b7-865a-085d779847b3" />

    Mình sẽ dùng lệnh `xdg-open` để xem file `image.png`.

    <img width="1404" height="814" alt="image" src="https://github.com/user-attachments/assets/18c55497-612d-4ab3-bf9c-648b8b3221e4" />

    Ngay lập tức nó sẽ hiện cho các bạn thấy được 1 bức ảnh được tạo từ file `aline.wav` có chứa flag trong đó:

    <pre> QnQSec{h1dd3n_1n_4ud1o} </pre>
    
  + Tóm lại với dạng Forensic Steganography - File âm thì các bạn cần phải xác định được file âm thanh và những bước tiếp theo cần phải làm gì để có được thông tin bên trong file ảnh!!

