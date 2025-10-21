# Steganoraphy
* Steganoraphy is the technique of hiding secret information inside anther file — usually an image, audio, video, or document in a way that other won't notice anything is hidden
* In steganoraphy challenges our goal is to dig inside the file to find what's hidden so we can extract the flag
  - First, to read hidden information inside a file we often use the command:

      <pre> exiftool (file) </pre>
      
     + Exiftool is a tool used to read hidden file data (metadata)
     + I'll explain metadata <pre> metadata </pre>
     + Metadata is hidden information embedded in a file that does not show up when you open the file normally. Example usage:
       
       <img width="704" height="452" alt="image" src="https://github.com/user-attachments/assets/706d00be-2283-4c63-8f7c-945212ca2df7" />

       Imagine an image that contains a flag. When running <pre> exiftool ukn_reality.jpg </pre> It prints a lot of file information like:
       <pre>
         File name:              .....
         File size:              .....
         File type:              .....
         File type extension:    .....
         MIME type:              .....
         ...and more
       </pre> 
       + All the output form exiftool is data embedded inside the file. If the challenge image contain a flag, you must pay close attention to the metadate output — it's very imoportant, so read carefully and don't miss anything!
   
     <img width="1398" height="710" alt="image" src="https://github.com/user-attachments/assets/3ac41ec9-cf17-49b7-838c-5632c1a21608" />
     
       In the example image metadata one suspicious field Attribution Url contained a string:
    
     <pre>cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==</pre>

       When you find a suspicious-looking encoded string like that, you can decode it with:

     <pre> echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==" | base64 -d </pre>

      The base64 command hleps decode/decoder sush as:

    <img width="603" height="99" alt="image" src="https://github.com/user-attachments/assets/833c9ac3-7228-4e20-8659-26a2870d7b23" />

    You can also use an online base64 decoder such as: https://www.base64decode.org/
    
    <img width="1188" height="857" alt="image" src="https://github.com/user-attachments/assets/c14e07b1-9df6-490f-93ca-0fb7100212f6" />

--> Summary: When tackling CTF Forensics steganography challenges, your first job is to extract the hidden data inside the file. exiftool is a mandatory first step to inspect metadata and find hidden strings or clues. From there you may need decoders (like base64), file carving, stego tools, or deeper analysis depending on what you find.

#
# Steganography

* Steganography là kỹ thuật giấu thông tin bí mật bên trong một dữ liệu khác — thường là ảnh, âm thanh, video, hoặc tài liệu mà người khác không nhận ra là có gì bị giấu
* Với dạng Steganography thì mục tiêu chúng ta là phải tìm sâu bên trong file có những gì khai thác sâu bên trong mới có thể tìm được flag 
  - Đầu tiền muốn đọc được bên trong file thì mình dùng lệnh: 

       <pre> exiftool (file) </pre>

     + Exiftool Là một công cụ dùng để đọc file ẩn (metadata)
     + Mình sẽ giải thích thêm về <pre> metadata </pre>
     + metadata là dạng thông tin ẩn bên trong file nó sẽ không hiển thị khi chúng ta xem file 1 cách bình thường. Tôi sẽ ví dụ về lệnh này nhé:

       <img width="704" height="452" alt="image" src="https://github.com/user-attachments/assets/706d00be-2283-4c63-8f7c-945212ca2df7" />

       Giả sử tôi đang có một bức ảnh có 1 flag ở trên. Các bạn có thể thấy được khi tôi dùng lệnh: <pre> exiftool ukn_reality.jpg </pre> nó sẽ xuất ra rất nhiều thông tin từ file ảnh như:
        <pre>
          Tên file ảnh:        .....
          Kích thước file:     .....
          Loại file:           .....
          Phần mở rộng:        .....
          Kiểu dữ liệu MIME:   .....
           ........ </pre>
      + Từ những dữ liệu được xuất từ exiftool xuất ra đều là phần file ẩn bên trong file. Nhưng chúng ta phải để ý kỉ rằng ở dây tôi đang dùng 1 bức có chứa flag nên các bạn phải để ý là rằng những thứ được xuất từ metadata rất quọng vì thế các bạn hãy đọc thật kỹ trách việc bỏ sai sót!!!
    
    <img width="1398" height="710" alt="image" src="https://github.com/user-attachments/assets/3ac41ec9-cf17-49b7-838c-5632c1a21608" />

       Từ hình ảnh trên khi tôi dùng lệnh exiftool đã xuất ra 1 thông tin khá nghi ngờ ở phần Attribution Url đã xuất hiện ra 1 chuỗi:

        cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==
    
       Với việc khi phát hiện 1 chuỗi dạng encoding được mã hóa thì chúng ta có thể dùng lệnh:

    <pre> echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==" | base64 -d </pre>

       Lệnh base64 có thể giúp chúng ta mã hóa đã các chuỗi như trên:

    <img width="603" height="99" alt="image" src="https://github.com/user-attachments/assets/833c9ac3-7228-4e20-8659-26a2870d7b23" />

      Hoặc chúng ta có thể dùng base64 online: https://www.base64decode.org/
    
    <img width="1188" height="857" alt="image" src="https://github.com/user-attachments/assets/c14e07b1-9df6-490f-93ca-0fb7100212f6" />

--> Tóm lại: Khi tham gia các thử thách CTF về Forensics – Steganography, việc đầu tiên bạn cần làm là trích xuất dữ liệu ẩn bên trong file. Lệnh exiftool là bước bắt buộc đầu tiên để kiểm tra metadata và tìm các chuỗi hoặc manh mối bị ẩn. Từ đó, bạn có thể cần sử dụng thêm các công cụ giải mã (như base64), kỹ thuật file carving, stego tools, hoặc phân tích chuyên sâu hơn tùy vào những gì bạn tìm thấy.
