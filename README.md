# myLesson — KHO FILE NGHE

Kho **file nghe (mp3)** cho trang bài tập của học sinh: <https://andrewclasses.com>

Tách riêng khỏi repo `myLesson` (trang web) vì file nghe nặng, mà GitHub Pages
chỉ cho mỗi trang tối đa **1 GB** — để chung thì trang web phình theo, không
gỡ ra được nữa (git giữ cả lịch sử).

## Cách xếp file (thầy chốt 19/08/2026)

**Một thư mục cho mỗi LEVEL**, file đặt tên **đúng bằng mã bài nghe**:

```
LSFLY/   LSFLY-S1.T3.P1-2-3.mp3      ← Listening for Flyers
LSA2/    LSA2-S2.T1.P4-5.mp3         ← Listening for A2
LSB1/    LSB1-S1.T2.P1-2.mp3         ← Listening for B1
IEL/     IEL-S15.T1.P1.mp3           ← Listening for IELTS
```

Level = **phần trước dấu gạch đầu tiên của mã bài**. App và trang web **tự suy
ra đường dẫn từ chính mã bài**, nên bài chỉ cần lưu mỗi mã — không lưu đường dẫn.

Trang bài tập gọi:

```
https://andrewclasses-01.github.io/myLesson-audio/<LEVEL>/<MÃ BÀI>.mp3
```

⛔ **Đừng đổi cách xếp này** nếu không sửa cả `nghe.js` (app) lẫn `veTrinhPhat()`
(web) — đường dẫn được ghép ở hai nơi đó.

## Quy cách file

| | |
|---|---|
| Định dạng | MP3 **64 kbps, 1 kênh (mono)** |
| Nguồn | file gốc trong `D:\4. LISTENING` (mp3 hoặc rút tiếng từ mp4) |
| Cỡ trung bình | ~2,1 MB cho bài 4,4 phút (video mp4 cũ nặng gấp ~8 lần) |

Lệnh nén (ffmpeg ở `D:\APP AND DATA\myLesson-data\bin`):

```
ffmpeg -i "<file gốc>" -vn -ac 1 -ar 44100 -b:a 64k "<MÃ BÀI>.mp3"
```

Bản nén cũng được **cất luôn vào thư mục `AUDIO` của chính buổi đó** trên ổ D
(`D:\4. LISTENING\…\LSFLY-S1.T1\AUDIO\`) — kho này chỉ là bản sao để web gọi.

### Đã làm 19/08/2026 — LSFLY-S1 (mẻ thử đầu tiên)

7 bài, 26,8 phút. File gốc mp3 224 kbps của T1 **đã bị đè bằng bản nén** (thầy
chốt — video mp4 gốc vẫn còn nên rút lại được lúc nào cũng được).

| Bài | Nguồn | Trước | Sau |
|---|---|---|---|
| LSFLY-S1.T1.P1-2 | mp3 gốc 224k | 4,39 MB | **1,26 MB** |
| LSFLY-S1.T1.P3 | mp3 gốc 192k | 2,95 MB | **0,98 MB** |
| LSFLY-S1.T1.P4-5 | mp3 gốc 224k | 5,63 MB | **1,61 MB** |
| LSFLY-S1.T2.P1-2-3 | mp4 | 16,04 MB | **2,18 MB** |
| LSFLY-S1.T2.P4-5 | mp4 | 13,34 MB | **1,81 MB** |
| LSFLY-S1.T3.P1-2-3 | mp4 | 17,45 MB | **2,39 MB** |
| LSFLY-S1.T3.P4-5 | mp4 | 15,04 MB | **2,04 MB** |

Nguồn ưu tiên: **mp3 sẵn có** (nếu trùng tên mã bài) vì nó là bản gần gốc hơn;
không có thì rút tiếng từ mp4.
⚠ Thư mục `Tests Flyers 1 CD` là bản rip đĩa gốc (tên tiếng Nga `01 Дорожка 1`),
KHÔNG phải bài giao — đừng đưa lên kho.

## Vì sao không để trên Google Drive

Đã thử cả ba kiểu link tải trực tiếp của Drive — trình duyệt **từ chối phát**
(Drive gắn cờ "file tải về, cấm đoán định dạng"). Drive chỉ cho nhúng khung
`/preview`, mà khung đó giấu mất đồng hồ và không tua được.

## Đừng để repo phình quá

Trần của GitHub Pages là **1 GB mỗi trang**, và xoá file cũ KHÔNG làm repo nhỏ
lại (lịch sử vẫn giữ). Chỉ đưa lên bài **thực sự giao cho học sinh**; gần đầy
thì mở kho thứ hai (`myLesson-audio-2`).
