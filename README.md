# Baseus-Blade2-140w-4.2V-Battery-BMS-Fimware-Mod
1 bản firmware mod cho mạch bảo vệ của Baseus Blade2 bản 140w thay đổi điện áp ngắt pin từ 4.4 nguyên bản về 4.2 thông dụng cho đa số các dòng pin

Sau đây là phần hướng dẫn ae cách nạp firmware cho mạch bms mà mình có tổng hợp được từ các fapsu và chỉnh sửa để phù hợp và dễ dàng nhất để ae đều làm được

Các linh kiện cần thiết cho việc nạp lại firware bao gồm mạch nạp Jlink OB và phần mềm Jflash 

Đây là mạch nạp JlinkOB sẽ dùng cho việc flash lại Firmware vào chip trên mạch BMS
<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/31a63559-b288-4a6e-92fb-1f003f33918b" />

Ae nào chưa có thì em có để link mua ở đây: https://shopee.vn/Ob-ARM-Emulator-Debugger-L%E1%BA%ADp-tr%C3%ACnh-vi%C3%AAn-Tr%C3%ACnh-t%E1%BA%A3i-xu%E1%BB%91ng-M%C3%B4-ph%E1%BB%8Fng-Thay-th%E1%BA%BF-V8-SWD-M74-STM32-t%E1%BA%A3i-xu%E1%BB%91ng-cho-Arduino-J-Link-TYPE-C-USB-i.1057548384.24975822917?sp_atk=c27345a9-a94e-44bb-bf42-dac37c11158e&xptdk=c27345a9-a94e-44bb-bf42-dac37c11158e

Link tải Jflash: https://www.segger.com/downloads/jlink/

Ae nhấp vào link sẽ hiện ra trang như thế này 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a5dfeefd-58c1-462d-9ca4-ffa0ff8b132e" />

Tiếp đến kéo xuống chọn Phiên bản V6.48 rồi bấm tải về 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/57c9c197-a08e-4ea0-b941-e1d6b6f2e45c" />

Sau khi tải về xong ae mở lên tiến hành cái như bình thường là được

Đến trang này thì chọn như hình rồi bấm Install là xong (Ae nhớ để ý đường dẫn thư mục cài nhé để lát thêm chip vào trong Jflash)
<img width="813" height="488" alt="image" src="https://github.com/user-attachments/assets/de9b44cf-e76d-4737-a7d2-f12be558c72f" />

Giờ đến phần thêm chip vào trong Jflash, ae mở theo đường dẫn thư mục lúc cài, tìm thư mục SEGGER
<img width="1353" height="735" alt="image" src="https://github.com/user-attachments/assets/ea5c71ab-f8f8-4824-8670-98df02b4f4e4" />

Vào bên trong thư mục SEGGER, chọn Jlink_V648, tìm file có tên như này 
<img width="1348" height="743" alt="image" src="https://github.com/user-attachments/assets/dc314bd1-9336-44ef-b040-8abbcd75098f" />

Tải file JLinkDevices.xml em có đính trên bài này, rồi paste vào thư mục trên, nhấn continue là xong 
<img width="1343" height="744" alt="image" src="https://github.com/user-attachments/assets/057dcbdf-7e5a-4aac-bb17-8f58342215ad" />

Cũng trong thư mục này tìm thư mục con Devices
<img width="1357" height="739" alt="image" src="https://github.com/user-attachments/assets/97b292fd-95cd-441c-807a-0d861a2db556" />

Tải về copy toàn bộ thư mục CMSemicon em có đính kèm trên bài và paste vào thư mục này là xong 
<img width="1364" height="744" alt="image" src="https://github.com/user-attachments/assets/f16377f9-356c-4d75-8228-0fd0d10f65fb" />

Ae mở phần Mềm Jflash vừa cài lên, nhấn vào dấu ... ở mục Target Devices, sổ mục Manufacturer lên thấy dòng CMSemicon là thành công rồi nhé 
<img width="1146" height="879" alt="image" src="https://github.com/user-attachments/assets/b60415e1-8b1b-42c7-9d03-a12bc3feb621" />
<img width="1146" height="885" alt="image" src="https://github.com/user-attachments/assets/54fb3d6f-1a39-4212-82b6-c4bbf1803a09" />

Chọn chip rồi nhấn Ok, các thông số còn lại để mặc định rồi Nhấn OK là xong bước tạo chip nạp
<img width="1147" height="880" alt="image" src="https://github.com/user-attachments/assets/fab7ef73-943c-4894-a6fd-c2eb46a64525" />

File có tên 140.bin là file firmware của mạch BMS, ae tải về sau đó trong phần mềm Jflash bấm mục file chọn Open Data file
<img width="1145" height="879" alt="image" src="https://github.com/user-attachments/assets/f093c8ea-ffa4-4074-9197-9cb5bbf543d5" />

Chọn file 140.bin vừa tải về, nhấn Ok là được 
<img width="1143" height="877" alt="image" src="https://github.com/user-attachments/assets/bf650798-0ca8-45d9-aad9-771b6c3aa864" />

Hiện ra như thế này là xong bước chuẩn bị Firmware
<img width="1145" height="878" alt="image" src="https://github.com/user-attachments/assets/d38c3c4d-54ae-4018-bff1-3d53ce2e9734" />

Lưu ý: trước khi tiến hành nạp fw ae nên rút hết pin ra cho mạch mất nguồn hoàn toàn rồi mới bắt đầu nạp nhé

Đến phần mạch BMS, ae tìm hàng 4 chân có ký hiệu như này 

<img width="369" height="490" alt="image" src="https://github.com/user-attachments/assets/ed776a3c-4490-41ac-b29f-b970e2473111" />

Nối dây tương ứng vào mạch nạp JlinkOB như sau: 

5V ----> VCC

G  ----> GND

A  ----> SWDIO

L  ----> SWCLK

Pad hàn của 4 chân này rất nhỏ, ae lưu ý hàn cẩn thận không để chì dính chân này với chân nọ không là đi luôn cả mạch đấy

Kết nối với mạch nạp xong, cắm vào máy tính, đèn đỏ trên mạch BMS sáng chứng tỏ chip đã có nguồn

Ae quay lại phần mềm Jflash bấm chọn Target ở trên cùng ---> chọn Connect
<img width="1146" height="877" alt="image" src="https://github.com/user-attachments/assets/c2199872-b4ad-4fd6-9dee-4b753b53abcc" />

Để ý phần Log phía bên dưới, bấm xong mà thấy phần mềm load ra được đầy đủ thông số chip, bộ nhớ, vùng flash, .... thì đã kết nối thành công

Nếu báo lỗi không tìm được chip thì ae xem lại chỗ hàn hoặc đảo 2 dây SWDIO và SWCLK lại là được.

Ae tiếp tục nhấn vào mục Target -> Manual Programming -> Program and Verify
<img width="1145" height="875" alt="image" src="https://github.com/user-attachments/assets/23318ade-f9c4-4d7b-9680-d86eda4b96f8" />

Phần mềm sẽ tiến hành nạp fw, nếu trong quá trình chạy ae thấy đã Program xong đến phần verify mà phần mềm báo error thì quay lại bước trên nhưng chọn qua Program là được





























