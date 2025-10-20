# Forensic

*Sau đây mình sẽ giới thiệu cho các bạn về Forensic!!!
  -Forensics trong CTF là thể loại nơi mày phải phân tích chứng cứ kỹ thuật số (file, ảnh, ổ đĩa, mạng, log, v.v.) để tìm manh mối hoặc flag.
  -Các dạng về forensic:

| **Disk / Memory image**        | Phân tích ổ đĩa ảo (.dd, .img) hoặc dump RAM để tìm dữ liệu ẩn | `autopsy`, `volatility`, `strings`, `binwalk`, `foremost`, `mmls`, `mount`, `grep` |
| **Network capture (PCAP)**     | Phân tích file `.pcap` để tìm dữ liệu truyền qua mạng          | `Wireshark`, `tshark`, `NetworkMiner`                                              |
| **Steganography**              | Ẩn thông tin trong hình, âm thanh, video                       | `steghide`, `zsteg`, `binwalk`, `exiftool`                                         |
| **File corruption / recovery** | File bị hư, sai định dạng, thiếu header                        | `hexeditor`, `xxd`, `binwalk`, `file`, `dd`                                        |
| **Log analysis**               | Phân tích log hệ thống, web server, trình duyệt, app           | `grep`, `less`, `cat`, `sqlite3`, `json` tools                                     |
| **Email / PDF / Document**     | Tìm metadata, macro, link ẩn trong tài liệu                    | `exiftool`, `strings`, `oletools`                                                  |
| **Malware forensics**          | Phân tích hành vi, chuỗi, file dropper                         | `strings`, `ghidra`, `IDA`, `capa`, `Detect It Easy`                               |


