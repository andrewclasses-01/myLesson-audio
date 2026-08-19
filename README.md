# myLesson — KHO FILE NGHE

Kho **file nghe (mp3)** cho trang bài tập của học sinh: <https://andrewclasses.com>

Tách riêng khỏi repo `myLesson` (trang web) vì file nghe nặng, mà GitHub Pages
chỉ cho mỗi trang tối đa **1 GB** — để chung thì trang web phình theo, không
gỡ ra được nữa (git giữ cả lịch sử).

## Cách dùng

Mỗi file đặt tên **đúng bằng mã bài nghe**, nằm ngay thư mục gốc:

```
LSFLY-S1.T3.P1-2-3.mp3
LSA2-S2.T1.P4-5.mp3
```

Trang bài tập gọi thẳng:

```
https://andrewclasses-01.github.io/myLesson-audio/<MÃ BÀI>.mp3
```

## Quy cách file

| | |
|---|---|
| Định dạng | MP3 **64 kbps, 1 kênh (mono)** |
| Nguồn | file gốc trong `D:\4. LISTENING` (mp3 hoặc rút tiếng từ mp4) |
| Cỡ trung bình | ~2,1 MB cho bài 4,4 phút (video mp4 cũ nặng gấp ~8 lần) |

Lệnh nén (ffmpeg có sẵn ở `D:\APP AND DATA\myStudent-data\bin`):

```
ffmpeg -i "<file gốc>" -vn -ac 1 -ar 44100 -b:a 64k "<MÃ BÀI>.mp3"
```

## Vì sao không để trên Google Drive

Đã thử cả ba kiểu link tải trực tiếp của Drive — trình duyệt **từ chối phát**
(Drive gắn cờ "file tải về, cấm đoán định dạng"). Drive chỉ cho nhúng khung
`/preview`, mà khung đó giấu mất đồng hồ và không tua được.

## Đừng để repo phình quá

Trần của GitHub Pages là **1 GB mỗi trang**, và xoá file cũ KHÔNG làm repo nhỏ
lại (lịch sử vẫn giữ). Chỉ đưa lên bài **thực sự giao cho học sinh**; gần đầy
thì mở kho thứ hai (`myLesson-audio-2`).
