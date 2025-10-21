# Steganography - Audio file

* Với Forensic dạng Steganography - file âm thanh thì mục tiêu cần tìm flag gồm:
  + Xác định được file âm thanh đó có thật sự là file âm thanh không hay file âm thanh giả.
  + Khi xác định được flie âm thanh tiếp theo cần phải vào bên trong file đó có những gì và tìm những dòng khả nghi nhẩt.
* Tôi sẽ ví dụ cho các bạn về dạng Steganography - file âm thanh :

    <img width="1716" height="810" alt="image" src="https://github.com/user-attachments/assets/f7db2921-7d07-4833-a65b-8468c307c075" />

- Như các bạn đã thấy ở đây cho sẽ có 1 file âm thanh chứa flag trong đó. Khi các bạn chơi CTF như này thì đầu tiên phải xác định được file âm thanh này là thật hay chứa đựng một file nào đó ở phía sau file âm thanh này không.
- Đầu tiên để xác định được file âm thanh này tôi sẽ sử dụng lệnh:

    <pre> file (file) </pre>

  + Lệnh file này được sử dụng rất nhiều trong tất cả các dạng về Forensic. Nó được ví như là lệnh để xác định được đó là file gì
  + Ở đây file âm thanh của mình hiện tại là `aline.wav` thì mình sẽ xác định file này bằng lệnh `file`:
 
    <pre> file aline.wav </pre>
 
    <img width="783" height="74" alt="image" src="https://github.com/user-attachments/assets/03ae1898-bf3d-448a-a542-c0506feadbe4" />

    Như các bạn đã thấy khi mình sử dụng lệnh `file` thì lệnh này sẽ xác định cho các bạn thấy file âm thanh `aline.wav` này là:
    
    <pre> alien.wav: RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, mono 22050 Hz </pre>

    Bao gòm cả `RIFF (little-endian) data` và `Ware audio` thì chứng tỏ file này là file `aline.wav` thật

- Tiếp theo, khi chúng ta đã xác định file `aline.wav` này rồi thì chúng ta sẽ tạo 1 file từ file `aline.wav` bằng lệnh:

  <pre>  sox (file âm thanh) -n spectrogram -o (tên file cần tạo).png </pre>   

  + Thực tế lệnh `sox` dùng để xử lí âm thanh 
