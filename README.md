# Bước chuẩn bị: Bước cài đặt.
- Giải Nén: Zeppelin: https://zeppelin.apache.org/download.html (Cài phiên bản 0.8.2)
- Cài Java Jre: https://javadl.oracle.com/webapps/download/GetFile/1.8.0_331-b09/165374ff4ea84ef0bbd821706e29b123/windows-i586/jre-8u331-windows-x64.exe
- Cài python 3.7: https://www.python.org/downloads/release/python-370/


# Sau khi tiến hành cài đặt các đường dẫn file như sau:
- Zeppelin: Giải nén ở vị trí bất kì nơi nào mà các bạn cho là thuận tiện nhất.
- Java Jre: C:\Program Files (x86)\Common Files\Oracle\Java\javapath
- Python 3.7: C:\Users\PC\AppData\Local\Programs\Python\Python37
		 C:\Users\Ten_may_cua_ban\AppData\Local\Programs\Python\Python37

## Note: Các bạn cần sao chép đường dẫn thư mục chứa python 3.7 trên và thêm python.exe vào cuối như sau:

- C:\Users\PC\AppData\Local\Programs\Python\Python37\python.exe


## Các bước cài đặt Zeppelin:
- B1. Tạo môi trường ảo python trong thư mục zeppelin-0.8.2-bin-all như sau:
	mkdir .\python\venv
	C:\Users\PC\AppData\Local\Programs\Python\Python37\python.exe -m venv .\python\venv
- B2. Đi vào môi trường ảo python bằng câu lệnh sau:
	.\python\venv\scripts\activate.bat
	Chú ý file: activate.bat chỉ chạy trên cmd, khi chạy trên visual code hay tạo nhầm
	phần powershell chạy bằng ps1 nên hãy cẩn thận
 	Cập nhật các thư viện vào môi trường ảo python như sau:
	pip install py4j==0.10.4
	pip install pyspark==2.2.1
- B3. Tiếp theo ta cần lấy đường dẫn của môi trường ảo trong python, và đường dẫn đến javapath khi cài đặt java
	C:\Program Files (x86)\Common Files\Oracle\Java\javapath
	E:\zeppelin-0.8.2-bin-all\python\venv\Scripts
	Note: Đường dẫn thứ hai là phần đường dẫn tùy thuộc vào vị trí mà bạn đặt, tuy nhiên
	luôn dẫn đến thư mục chứ môi trường ảo venv bên trong file: zeppelin-0.8.2-bin-all	
- B4. Kết hợp hai đường dẫn trên như sau:
	set PATH=C:\Program Files (x86)\Common Files\Oracle\Java\javapath;E:\zeppelin-0.8.2-bin-all\python\venv\Scripts;
## Note: Một số trường hợp bị lỗi, vậy các bạn chú ý thêm dấu /#/ nhé: như sau: http://127.0.0.1:8080/#/
- B5. Chèn vào hai file sau từ khóa REM cuối cùng (Bản chất của từ khóa REM trong cmd đóng vai trò như là comment giống với // trong c)
	common.cmd
	zeppelin.cmd
- B6. Quay lại thư mục chính zeppelin-0.8.2-bin-all
	Tạo hai thư mục mới như sau:
	mkdir .\zeppelin-web\dist
	Tiến hành giải nén file: zeppelin-web-0.8.2.war vào thư mục vừa mới tạo
- B7. Kiểm tra xem liệu có tồn tại một phần mềm khác chạy cổng 8080 hay không bằng câu lệnh sau:
	netstat -ano | findstr 8080
	Nếu có tồn tại sử dụng câu lệnh sau để tắt cổng đó:
	taskkill /PID <PID> /F
	với PID là tiến trình đang chạy
	vd: https://stackoverflow.com/questions/39632667/how-do-i-kill-the-process-currently-using-a-port-on-localhost-in-windows
- B8. Vào thư mục bin chạy file : zeppelin.cmd
- B9. Vào web browser gõ: 127.0.0.1:8080
- B10. Ta cần cấu hình vài thứ để chạy python.
	Vào phàn Interpert tìm phần spark và chỉnh sữa đường dẫn đến môi trường ảo của python:
	E:\zeppelin-0.8.2-bin-all\python\venv\Scripts\python.exe
- B11. Tạo và chạy file.
## Note: Một số trường hợp bị lỗi truy xuất các bạn nhớ thêm /#/ sau đường dẫn ta có: http://127.0.0.1:8080/#/
