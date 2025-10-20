# Steganography

* Steganography là kỹ thuật giấu thông tin bí mật bên trong một dữ liệu khác — thường là ảnh, âm thanh, video, hoặc tài liệu mà người khác không nhận ra là có gì bị giấu
* Với dạng Steganography thì mục tiêu chúng ta là phải tìm sâu bên trong file có những gì khai thác sâu bên trong mới có thể tìm được flag 
  - Đầu tiền muốn đọc được bên trong file thì mình dùng lệnh: 

       <pre> exiftool (file) </pre>

     + Là một công cụ dùng để đọc file ẩn (metadata)
     + Mình sẽ giải thích thêm về <pre> metadata </pre>
     + metadata là dạng thông tin ẩn bên trong file nó sẽ không hiển thị khi chúng ta xem file 1 cách bình thường
     + Mình sẽ ví dụ về lệnh này nhé:

       <img width="704" height="452" alt="image" src="https://github.com/user-attachments/assets/706d00be-2283-4c63-8f7c-945212ca2df7" />

       Giả sử tôi đang có một bức ảnh có 1 flag ở trên. Các bạn có thể thấy được khi tôi dùng lệnh <pre> exiftool ukn_reality.jpg </pre> nó sẽ xuất ra rất nhiều thông tin từ file ảnh như:
         + Tên file ảnh
         + Kích thước file
         + Loại file
         + Phần mở rộng
         + Kiểu dữ liệu MIME
           ........
      + Từ những dữ liệu được xuất từ exiftool xuất ra đều là phần file ẩn bên trong file. Nhưng chúng ta phải để ý kỉ rằng ở dây tôi đang dùng 1 bức có chứa flag nên các bạn phải để ý là rằng những thứ được xuất từ metadata rất quọng vì thế các bạn hãy đọc thật kỹ trách việc bỏ sai sót!!!
    
    <img width="1398" height="710" alt="image" src="https://github.com/user-attachments/assets/3ac41ec9-cf17-49b7-838c-5632c1a21608" />

       Từ hình ảnh trên khi tôi dùng lệnh exiftool đã xuất ra 1 thông tin khá nghi ngờ ở phần Attribution Url đã xuất hiện ra 1 chuỗi:

        cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==
    
       Với việc khi phát hiện 1 chuỗi dạng encoding được mã hóa thì chúng ta có thể dùng lệnh:

    <pre>base64</pre>

       Lệnh base64 có thể giúp chúng ta mã hóa đã các chuỗi như trên:

    <img width="603" height="99" alt="image" src="https://github.com/user-attachments/assets/833c9ac3-7228-4e20-8659-26a2870d7b23" />

      Hoặc chúng ta có thể dùng base64 online: https://www.base64decode.org/
    
    <img width="1188" height="857" alt="image" src="https://github.com/user-attachments/assets/c14e07b1-9df6-490f-93ca-0fb7100212f6" />

--> Tóm lại thì khi chúng ta muốn chơi CTF Forensic dạng Steganography thì đầu tiên chúng ta phải làm sao khai thác được file ẩn được dấu ở bên trong và không thể thiếu lệnh Command exiftool đây sẽ là bước đầu tiên bắt buộc khi chúng ta muốn tìm thông tin trong file.

 Chúc các bạn may mắn nhé!
        JULIUSDD
     
    
