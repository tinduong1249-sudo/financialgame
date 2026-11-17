# Hè Này Tiêu Gì? – Hướng dẫn đưa game lên cho cả lớp chơi

Game gồm file `index.html` và thư mục `images/` (ảnh 7 tiệm). Bạn cần làm 3 việc: tạo tài khoản Ably, dán khóa vào file, rồi đưa lên GitHub Pages.

---

## Bước 1. Tạo khóa Ably (khoảng 5 phút, miễn phí, không cần thẻ)

Ably là dịch vụ giúp 47 điện thoại thấy nhau theo thời gian thực. Gói miễn phí cho 200 kết nối và 500 tin nhắn mỗi giây, gấp 5 lần Supabase miễn phí.

1. Vào https://ably.com, bấm **Sign up**, đăng ký bằng Google hoặc GitHub.
2. Tạo một app mới, đặt tên `he-nay-tieu-gi`.
3. Vào tab **API Keys** của app. Nên bấm tạo một khóa mới chỉ có quyền **Publish** và **Subscribe** (an toàn hơn khóa gốc).
4. Bấm **Copy** khóa. Khóa có dạng `abc123.xyz789:AbCdEf...`

## Bước 2. Dán khóa vào game và đổi PIN

Mở `index.html` bằng Notepad hoặc VS Code, tìm đoạn gần đầu phần script:

```js
const CONFIG = {
  ABLY_KEY: '',
```

Dán khóa Ably vào giữa hai dấu nháy, lưu file.

**Đổi mã PIN chủ phòng** (PIN mặc định là `2026`, ai đọc hướng dẫn này cũng biết):
1. Mở game, thêm `#host` vào cuối link, bấm **Đổi mã PIN**.
2. Nhập PIN mới, bấm **Tạo mã để dán vào file**.
3. Chép chuỗi mã hiện ra, dán thay cho chuỗi trong dòng `HOST_PIN_HASH: '...'`.

File chỉ lưu PIN đã mã hóa, nên bạn nào xem mã nguồn cũng không đọc được PIN.

Sửa giá cả ở phần `SHOPS` (giá món, `seatCost` là tiền ngồi mỗi 8 giây) và `CASINO_WIN` (tỉ lệ thắng Tài Xỉu, đang là 25%).

## Bước 3. Ảnh tiệm

Ảnh đã nằm sẵn trong `images/`. Muốn thay ảnh thì giữ đúng tên file: `net.jpg`, `bida.jpg`, `fashion.jpg`, `workshop.jpg`, `food.jpg`, `teddy.jpg`, `casino.jpg`. Ảnh nên ngang, dưới 200 KB.

## Bước 4. Đưa lên GitHub Pages

1. Vào https://github.com → **New repository** → tên `he-nay-tieu-gi`, chọn **Public** → Create.
2. Bấm **uploading an existing file**, kéo thả `index.html` và thư mục `images` → **Commit changes**.
3. Vào **Settings → Pages** → Source: **Deploy from a branch**, Branch: **main**, thư mục **/(root)** → Save.
4. Chờ 1–2 phút. Link game: `https://<tên-github-của-bạn>.github.io/he-nay-tieu-gi/`
5. Bảng chủ phòng: thêm `#host` vào cuối link.

---

## Cách chơi trong tiết sinh hoạt

1. Mở `link#host` trên máy chiếu, nhập PIN. Màn hình hiện **mã phòng** 4 số.
2. Cho cả lớp quét mã QR của link (tạo ở qr-code-generator.com), nhập **tên thật** và mã phòng.
3. Mỗi bạn hiện trong mục **Chờ duyệt vào phòng**. Đối chiếu với danh sách lớp, bấm **Duyệt** từng bạn, **Từ chối** người lạ, hoặc **Duyệt tất cả**.
4. Đặt số phút cho GĐ 1 và GĐ 2 ở dòng **Thời gian** (mặc định 5 phút), rồi bấm **Bắt đầu GĐ 1**. Đang chơi có thể bấm **+ 1 phút / − 1 phút**. Hết giờ game **không tự chuyển**: màn hình hiện "Hết giờ", bạn bấm **Chuyển sang GĐ 2** rồi **Kết thúc, tổng kết** khi cả lớp xong.
5. Ở tổng kết, mỗi bạn thấy hạng của mình. Bấm **Tải file CSV** để mở bằng Excel.

Những gì đã có sẵn để buổi học không bị hỏng:
- Bạn nào lỡ tải lại trang hoặc tắt trình duyệt sẽ tiếp tục đúng chỗ cũ, giữ nguyên số tiền.
- Bạn lỡ tải lại bảng chủ phòng cũng không mất gì (giai đoạn, đồng hồ, danh sách, diễn biến).
- Tên bậy tự đổi thành "Học sinh + số". Bạn đổi được tên bất kỳ ai, hoặc **mời ra khỏi phòng**, ở mục "Đổi tên bạn".
- Casino là bàn **Tài Xỉu** (3 xúc xắc, tổng 11–18 là Tài, 3–10 là Xỉu), tỉ lệ thắng cài 25%. Màn tổng kết cho mỗi bạn thấy mình đã chơi bao nhiêu ván, thắng bao nhiêu.
- Bạn vào trễ (sau GĐ 1) bị trừ mức tiêu trung bình của lớp và được đánh dấu "vào trễ".
- Bấm "Kết thúc" khi còn bạn chưa xong 5 tình huống, game hỏi lại một lần để tránh bấm nhầm.

## Giai đoạn 2: 5 tình huống (mới)

- 6 con đường: Gia sư, Giao hàng, Phục vụ cà phê, Cổ phiếu, **Thực tập sinh** (Công ty Công Nghệ, phụ cấp 3 triệu/tháng) và **Startup**. Ảnh nằm trong `images/`: `tutor.jpg`, `ship.jpg`, `waiter.jpg`, `stock.jpg`, `intern.jpg`, `startup.jpg`.
- Mỗi con đường có 5 tình huống. Nút bấm không hiện số tiền, chọn xong mới thấy kết quả. Một số lựa chọn để lại hậu quả cho các tình huống sau. Nội dung 30 tình huống nằm trong `index.html`, tìm `const SIT`.
- **D. Cách của tôi**: người chơi tự gõ giải pháp. Câu trả lời hiện ở mục **Cách của tôi · chờ chấm** trên bảng chủ phòng. Bấm −500k, 0k, +300k, +700k hoặc nhập số (nghìn đồng) rồi **Chấm số này**. Mỗi câu chờ tối đa 2 phút, quá giờ người chơi chỉ nhận lương cơ bản.
- Bạn nào chưa xong khi chuyển sang tổng kết thì các tình huống còn lại chỉ tính lương cơ bản.

## Bản mới: nhân vật, mini-game, chat, Arena

- **Nhân vật**: ở sảnh chờ chọn giới tính (Nam mặc quần, Nữ mặc váy), kiểu mắt (Tròn long lanh, To anime, Nam tính), dáng người (Gầy, Vừa, To), kiểu tóc, màu tóc, màu da, phụ kiện (kính, mũ, nơ) và màu áo. Mặt kiểu chibi.
- **Mini-game trong tiệm** (giai đoạn 1, mỗi lượt 100.000đ, chơi một mình): phải **ngồi vào bàn** trong tiệm, rồi bấm **🎮 Chơi game** trên thanh ghế. Tiền ngồi vẫn tính trong lúc chơi.
  Quán Net: Flappy · Bida: bàn bida kéo thả bắn bi · Thời Trang: phòng thử đồ, mặc luôn ra phố · Workshop: tô tượng mèo/gấu/thỏ, lưu tranh · Gà Rán · Trà Sữa: pha trà sữa đúng order · Gấu Bông: máy gắp gấu (gắp trúng vẫn có thể rơi). Casino giữ Tài Xỉu. Đổi giá ở dòng `MG_COST`.
- **Chat cả lớp**: nút 💬. Tối đa 20 chữ mỗi tin, mỗi bạn 5 giây mới gửi được 1 tin, từ bậy tự thành ***. Tin hiện góc trên bên trái và thành bong bóng trên đầu nhân vật. Bảng chủ phòng có mục **Chat lớp**: xem toàn bộ, nhắn với tư cách chủ phòng, **Tắt chat** khi lớp ồn.
- **Arena game** (sàn đấu trên sông Hàn, ngay dưới Photobooth Cầu Rồng, chỉ giai đoạn 1): hai bạn đứng ô A và ô B, cùng bấm "Sẵn sàng". Mỗi người trả 150k, thắng nhận 280k (arena giữ 20k). Muốn tập trước: bấm **Đấu thử với bot** (miễn phí). Trong sàn Arena mọi người chỉ đi được 30% tốc độ (sửa ở `ARENA_SPEED`). Khi đang có trận (cả trận với bot), người khác không bước vào sàn được. Điều khiển: cần điều khiển để đi, ⚔️ chém, 🛡️ đỡ (1,2 giây), ⚡ tăng tốc. Mất 3 tim là thua; hết 90 giây thì ai còn nhiều tim hơn thắng, bằng nhau thì hoàn tiền. Người đứng gần xem được trận. Đổi giá ở `ARENA_FEE`, `ARENA_WIN`.
- Đường phố có vân gạch, nhựa đường, sàn gỗ ven sông; mỗi tiệm có màu riêng, biểu tượng riêng và trang trí bên trong.

## Photobooth Cầu Rồng và chụp ảnh Polaroid

- Giữa phố Bạch Đằng có một đường vòng chìa ra sông Hàn (giống Cầu Tình Yêu), tên **Photobooth Cầu Rồng**. Từ lối đi ven sông, đi sang bên phải là vào được.
- Giữa vòng có **khung ảnh** (ô viền hồng nét đứt). Một bạn đứng trong khung, bấm **Chụp · 100.000đ**, cả phố đếm ngược 3 giây.
- Trong 3 giây đếm ngược, người ở ngoài không bước vào khung được.
- Lúc bấm máy, **ai đứng trong khung cũng lên hình**, mỗi người bị trừ 100k và nhận 1 ảnh Polaroid. Không giới hạn số người, bạn nào không đủ 100k thì không lên hình. Ảnh vẽ đúng từng bạn: đứng chỗ nào trong khung thì lên ảnh đúng chỗ đó (đứng xa máy ảnh thì nhỏ hơn), đúng màu áo, họa tiết, kiểu tóc, màu da và phụ kiện. Phông nền là sông Hàn, Cầu Rồng và pháo hoa.
- Người chơi xem lại và **lưu ảnh** trong **Túi đồ** hoặc ở màn tổng kết. Trên iPhone, bấm "Lưu ảnh về máy" rồi chọn "Lưu hình ảnh".
- Trên bảng chủ phòng có mục **Album lớp · Photobooth Cầu Rồng**: ảnh hiện ngay khi có người chụp. Bấm **Trình chiếu album** để chiếu lên máy chiếu lúc tổng kết.
- Muốn chụp ảnh cả lớp: ở **Sự kiện đặc biệt**, chọn "Photobooth Cầu Rồng (chụp ảnh)" để đưa mọi người vào khung, rồi bảo một bạn bấm chụp.
- Tiền chụp ảnh nằm ở mục "Chụp ảnh sống ảo" trong bảng tổng kết, file CSV và biểu đồ "Cả lớp tiêu tiền ở đâu". Đổi giá ở dòng `PHOTO_COST` đầu file.
- Phố có thêm dây đèn nhấp nháy, sao lấp lánh trên sông, Cầu Rồng đổi màu và pháo hoa. Máy yếu sẽ tự giảm hiệu ứng để không bị giật. Khu đi làm (giai đoạn 2) giữ nguyên như cũ.

## Bắt buộc: chơi thử trước buổi học

Game chưa được thử với 47 điện thoại thật. Hãy rủ 8–10 bạn chơi thử 5 phút:
- Mọi người thấy nhau đi lại, thả biểu cảm thấy nhau, bảng chủ phòng thấy đủ người: ổn.
- 2 bạn thử đấu Arena, 3–4 bạn chat cùng lúc, mỗi bạn thử 1 mini-game.
- 4–5 bạn cùng đứng trong khung ở Photobooth Cầu Rồng, một bạn bấm chụp: ai cũng nhận ảnh, bị trừ 100k, và ảnh hiện trong Album lớp.
- Nhân vật đứng hình hoặc bảng chủ phòng không thấy ai: vào trang Ably → app → **Stats** xem có vượt giới hạn không, rồi báo lại để chỉnh.

Thử trên một máy, không cần Ably: để trống `ABLY_KEY`, mở bảng chủ phòng ở một tab và vài tab người chơi trong **cùng trình duyệt**, nhập cùng mã phòng.

Dùng Supabase thay Ably: để trống `ABLY_KEY`, điền `SUPABASE_URL` và `SUPABASE_KEY` (giới hạn miễn phí thấp hơn: 100 tin nhắn mỗi giây).
