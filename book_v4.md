# RUST_OZ_V — Giáo trình Rust từ cơ bản đến chuyên sâu

*Tài liệu học lập trình Rust bằng tiếng Việt*

| Thông tin | Chi tiết |
| :--- | :--- |
| Tác giả, biên soạn | Thái Việt |
| Email | [ozsxe@icloud.com](mailto:ozsxe@icloud.com) |
| GitHub | [github.com/ozsx](https://github.com/ozsx) |
| Bản hiệu đính | 16/10/2026 |
| Nền tảng ngôn ngữ | Rust Edition 2024; trình biên dịch Rust 1.85.0 trở lên |


## Lời nói đầu

Rust là ngôn ngữ lập trình hệ thống chú trọng hiệu năng, an toàn bộ nhớ và khả năng tổ chức phần mềm. Ngôn ngữ này phù hợp với các ứng dụng cần kiểm soát tài nguyên, từ công cụ dòng lệnh và dịch vụ mạng đến phần mềm nhúng.

Quản lý bộ nhớ luôn có những đánh đổi. C và C++ cho phép kiểm soát trực tiếp tài nguyên; C++ hiện đại còn có RAII và con trỏ thông minh, nhưng việc dùng con trỏ sai vẫn có thể gây lỗi. Các ngôn ngữ có cơ chế thu hồi bộ nhớ tự động giảm gánh nặng quản lý vòng đời, với chi phí và độ trễ tùy cách triển khai. Rust dùng hệ thống kiểu, quyền sở hữu và mượn để kiểm tra nhiều điều kiện an toàn ngay khi biên dịch, đồng thời tự động hủy tài nguyên khi chủ sở hữu kết thúc vòng đời.

Ba ý tưởng xuyên suốt giáo trình là:

1. **An toàn bộ nhớ:** Safe Rust ngăn các lỗi như dùng dữ liệu sau khi giải phóng và truy cập qua tham chiếu không hợp lệ, với điều kiện phần `unsafe` bên dưới được triển khai đúng. Một số kiểm tra vẫn diễn ra khi chạy, chẳng hạn kiểm tra chỉ mục và quy tắc mượn của `RefCell`. Rust không loại bỏ mọi lỗi logic, `panic` hay rò rỉ bộ nhớ.
2. **Trừu tượng hóa hiệu quả:** Generics, trait và iterator giúp diễn đạt thuật toán rõ ràng mà thường không cần thêm chi phí phân phối động. Hiệu năng thực tế vẫn phụ thuộc thuật toán, cấu trúc dữ liệu, cấp phát và tối ưu hóa; cần đo đạc thay vì suy ra tốc độ từ tên ngôn ngữ.
3. **Đồng thời có kiểm soát:** Quyền sở hữu cùng `Send` và `Sync` giúp ngăn data race trong Safe Rust. Deadlock và race condition ở cấp logic vẫn có thể xảy ra và cần được xử lý trong thiết kế.

Sách gồm 24 chương, ba dự án thực hành và bảy phụ lục. Nội dung tham khảo *The Rust Programming Language*, *The Rust Reference*, *The Rust Edition Guide*, *Google Comprehensive Rust* và *Rust Course*. Đây là tài liệu biên soạn độc lập bằng tiếng Việt; danh mục nguồn nằm ở cuối sách.

## Cách sử dụng giáo trình

- Học tuần tự chương 1–8 trước khi chuyển sang generics, trait và tổ chức dự án. Quyền sở hữu ở chương 5 là nền tảng cho các chương sau.
- Ví dụ có `fn main()` là một chương trình riêng, trừ khi ghi rõ đường dẫn tệp trong dự án nhiều tệp. Các khối chỉ chứa câu lệnh `let` được đặt trong thân `main`; các định nghĩa hàm, kiểu và `impl` đặt ở cấp module. Không ghép mọi khối mã của một chương thành một tệp.
- Những dòng cố ý gây lỗi được chú thích hoặc đặt trong khối `rust,compile_fail`; ví dụ cố ý gây `panic` được đánh dấu `rust,should_panic`. Chúng minh họa hành vi cần hiểu, không phải chương trình mẫu để chạy thành công.
- Các dự án dùng `edition = "2024"`. Edition là tập quy tắc tương thích của ngôn ngữ, không phải số phiên bản trình biên dịch. Các phụ thuộc ngoài có yêu cầu phiên bản Rust riêng; hãy dùng toolchain stable còn được duy trì và lưu `Cargo.lock` của dự án.
- Lệnh shell được ghi rõ cho Bash hoặc PowerShell khi khác nhau. Chạy lệnh Cargo trong thư mục chứa `Cargo.toml`.
- Ký hiệu độ phức tạp mô tả tốc độ tăng chi phí theo số phần tử; không phải cam kết thời gian chạy tuyệt đối. Trong các ví dụ số học, hãy chú ý miền giá trị và chính sách xử lý tràn số.

## Mục lục

- **[Phần I. Khởi động](#phan-i)**
  - [Chương 1. Bắt đầu với Rust và hệ sinh thái Cargo](#chuong-01)
  - [Chương 2. Dự án 1 — Trò chơi đoán số](#chuong-02)
- **[Phần II. Nhập môn](#phan-ii)**
  - [Chương 3. Biến, tính khả biến và phạm vi](#chuong-03)
  - [Chương 4. Kiểu dữ liệu cơ bản, hàm và luồng điều khiển](#chuong-04)
- **[Phần III. Quyền sở hữu và mượn](#phan-iii)**
  - [Chương 5. Quyền sở hữu và mượn](#chuong-05)
- **[Phần IV. Kiểu phức hợp và khớp mẫu](#phan-iv)**
  - [Chương 6. Chuỗi ký tự: String và &str](#chuong-06)
  - [Chương 7. Kiểu dữ liệu tùy chỉnh: struct và enum](#chuong-07)
  - [Chương 8. Khớp mẫu](#chuong-08)
- **[Phần V. Phương thức, generics và trait](#phan-v)**
  - [Chương 9. Phương thức, impl và thiết kế hướng đối tượng](#chuong-09)
  - [Chương 10. Generics và trait](#chuong-10)
- **[Phần VI. Tập hợp dữ liệu, chuyển đổi kiểu và xử lý lỗi](#phan-vi)**
  - [Chương 11. Các cấu trúc dữ liệu tập hợp](#chuong-11)
  - [Chương 12. Chuyển đổi kiểu dữ liệu](#chuong-12)
  - [Chương 13. Xử lý lỗi](#chuong-13)
- **[Phần VII. Tổ chức dự án, kiểm thử và minigrep](#phan-vii)**
  - [Chương 14. Tổ chức dự án: package, crate, module và workspace](#chuong-14)
  - [Chương 15. Kiểm thử tự động và tài liệu hóa](#chuong-15)
  - [Chương 16. Dự án 2 — Công cụ dòng lệnh minigrep](#chuong-16)
- **[Phần VIII. Vòng đời, lập trình hàm và con trỏ thông minh](#phan-viii)**
  - [Chương 17. Vòng đời tham chiếu](#chuong-17)
  - [Chương 18. Closure và iterator](#chuong-18)
  - [Chương 19. Con trỏ thông minh và khả biến nội tại](#chuong-19)
- **[Phần IX. Đồng thời và bất đồng bộ](#phan-ix)**
  - [Chương 20. Lập trình đa luồng](#chuong-20)
  - [Chương 21. Lập trình bất đồng bộ](#chuong-21)
- **[Phần X. Chủ đề nâng cao và máy chủ web](#phan-x)**
  - [Chương 22. Unsafe Rust, FFI và kiểu nâng cao](#chuong-22)
  - [Chương 23. Siêu lập trình với macro](#chuong-23)
  - [Chương 24. Dự án 3 — Máy chủ web với thread pool](#chuong-24)
- **[Phần XI. Phụ lục tra cứu](#phan-xi)**
  - [Phụ lục A. Từ khóa và định danh thô](#phu-luc-a)
  - [Phụ lục B. Toán tử và ký hiệu cú pháp](#phu-luc-b)
  - [Phụ lục C. Các trait có thể dẫn xuất](#phu-luc-c)
  - [Phụ lục D. Công cụ phát triển và hệ sinh thái crate](#phu-luc-d)
  - [Phụ lục E. Rust editions và chuyển đổi dự án](#phu-luc-e)
  - [Phụ lục F. Quy ước đặt tên](#phu-luc-f)
  - [Phụ lục G. Thuật ngữ và nguyên tắc thực hành](#phu-luc-g)
- [Tài liệu tham khảo](#tai-lieu-tham-khao)

---

<a id="phan-i"></a>

## Phần I. Khởi động

---

<a id="chuong-01"></a>

### Chương 1. Bắt đầu với Rust và hệ sinh thái Cargo

Ba công cụ chính để bắt đầu với Rust là `rustup` (quản lý toolchain), `rustc` (trình biên dịch) và `cargo` (quản lý dự án, phụ thuộc và quy trình build).

#### 1.1. Cài đặt môi trường Rust qua `rustup`

`rustup` là công cụ chính thức quản lý các phiên bản trình biên dịch Rust và các công cụ liên quan. Nó hỗ trợ cài đặt, cập nhật, chuyển đổi linh hoạt giữa các kênh phát hành (*stable*, *beta*, *nightly*), và hỗ trợ biên dịch chéo (*cross-compilation*) cho nhiều hệ điều hành và kiến trúc vi xử lý khác nhau (x86_64, ARM64, WebAssembly, RISC-V).

##### Hướng dẫn cài đặt theo từng hệ điều hành

1. **Trên Linux hoặc  macOS:**
   Mở terminal và thực thi lệnh cài đặt từ trang chủ chính thức của ngôn ngữ Rust (`rust-lang.org`):
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
   Bộ cài thường cấu hình `PATH` cho shell được hỗ trợ. Sau khi cài, mở lại terminal; với Bash trên Linux/macOS có thể nạp môi trường bằng `source "$HOME/.cargo/env"`. Làm theo hướng dẫn cuối cùng của bộ cài nếu dùng shell khác.
   -  *Yêu cầu bắt buộc:* Cần có sẵn C compiler và Linker (trình liên kết mã):
     - Trên Ubuntu/Debian: `sudo apt update && sudo apt install build-essential`
     - Trên macOS: `xcode-select --install`

2. **Trên Windows:**
   Truy cập trang web chính thức của Rust, tải về và chạy bộ cài đặt `rustup-init.exe`. Trong quá trình cài đặt, làm theo hướng dẫn để cài đặt công cụ *Microsoft Visual Studio C++ Build Tools* (chọn gói *"Desktop development with C++"* để cung cấp MSVC Linker cần thiết cho môi trường Windows).

##### Kiểm tra cài đặt và lệnh quản trị thiết yếu

```bash
# Kiểm tra phiên bản trình biên dịch rustc
rustc --version
# Edition 2024 yêu cầu rustc từ 1.85.0; kết quả thực tế tùy bản cài đặt.

# Kiểm tra phiên bản trình quản lý gói Cargo
cargo --version
# Cargo được cài cùng toolchain Rust.

# Cập nhật toàn bộ toolchain Rust lên phiên bản ổn định mới nhất
rustup update

# Mở toàn bộ tài liệu chính thức ngoại tuyến (offline) trực tiếp trên trình duyệt
rustup doc
```

---

#### 1.2. Chương trình "hello, world!" đầu tiên

Trong Rust, tệp mã nguồn luôn có phần mở rộng là `.rs`. Khi tên tệp gồm nhiều từ, quy ước chuẩn của cộng đồng (*idiomatic Rust*) là sử dụng dấu gạch dưới (`snake_case`), ví dụ: `hello_world.rs` hoặc `main.rs`.

Hãy tạo một tệp có tên `main.rs` với nội dung như sau:

```rust
// File: main.rs
// Hàm main là điểm bắt đầu (entry point) của mọi chương trình Rust thực thi
fn main() {
    println!("Hello, world! 🦀");
}
```

##### Mổ xẻ chi tiết cú pháp

1. **`fn main() { ... }`:** Khai báo hàm `main`. Trong Rust, từ khóa `fn` dùng để định nghĩa hàm. `main` là điểm vào của chương trình Rust thông thường; mã khởi động của nền tảng chuẩn bị môi trường trước khi gọi hàm này. Cặp ngoặc đơn `()` chứa danh sách tham số (ở đây không có tham số nào). Khối lệnh của thân hàm luôn nằm trong cặp ngoặc nhọn `{}`.
2. **`println!("Hello, world! 🦀");`:** In chuỗi ký tự ra màn hình kèm ký tự xuống dòng. Dấu chấm than `!` trong `println!` cho biết đây là lời gọi macro. macro trong Rust cung cấp khả năng siêu lập trình (*metaprogramming*) tại thời điểm biên dịch, cho phép nhận số lượng tham số linh hoạt và kiểm tra định dạng chuỗi an toàn kiểu dữ liệu ngay lúc biên dịch.
3. **Dấu chấm phẩy `;`:** Đánh dấu sự kết thúc của một câu lệnh (*statement*).

##### Quy trình biên dịch và chạy

Rust là ngôn ngữ biên dịch trước (**Ahead-Of-Time compiled**). Bạn dùng trình biên dịch `rustc` để dịch trực tiếp mã nguồn thành tệp thực thi cho target đã chọn; chương trình có thể vẫn phụ thuộc các thư viện hệ thống được liên kết động:

```bash
# Biên dịch file main.rs thành file thực thi
rustc main.rs

# Chạy tập tin nhị phân vừa sinh ra
# Trên Linux/macOS:
./main

# Trên Windows:
.\main.exe

# Kết quả hiển thị trên màn hình:
# Hello, world! 🦀
```

---

#### 1.3. Hệ thống quản lý dự án Cargo chuyên sâu

Trong các dự án thực tế, mã nguồn sẽ phân tán trên nhiều tệp và tích hợp hàng chục thư viện ngoài (trong Rust gọi là **crates**). Bạn thường dùng **Cargo** — trình quản lý gói và hệ sinh thái build chính thức của Rust.

##### Tạo dự án mới với Cargo

```bash
# Tạo một dự án ứng dụng thực thi (binary project)
cargo new hello_cargo --edition 2024
cd hello_cargo
```

Cấu trúc thư mục chuẩn được sinh ra:

| Đường dẫn trong `hello_cargo` | Vai trò |
| :--- | :--- |
| `Cargo.toml` | Thông tin package và các phụ thuộc |
| `src/main.rs` | Điểm vào của crate thực thi |
| `.gitignore` | Quy tắc bỏ qua tệp sinh ra, như thư mục `target` |
| `.git/` | Kho Git, thường được tạo nếu dự án chưa nằm trong kho có sẵn |

##### Khám phá tệp cấu hình `Cargo.toml`

Tệp này viết bằng định dạng TOML (*Tom's Obvious, Minimal Language*):

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2024"
rust-version = "1.85"
authors = ["Thái Việt <ozsxe@icloud.com>"]

# Danh sách các thư viện ngoài (crates) từ Crates.io mà dự án phụ thuộc
[dependencies]
```

- **`[package]`:** Khối thông tin cấu hình gói gồm tên dự án (`name`), phiên bản phát hành theo chuẩn Semantic Versioning `MAJOR.MINOR.PATCH` (`version`), và phiên bản ấn bản ngôn ngữ (`edition = "2024"`).
- **`[dependencies]`:** Nơi liệt kê các thư viện ngoài. Khi bạn thêm một crate vào đây, Cargo sẽ tự động tải về từ `crates.io`, kiểm tra mã băm checksum, biên dịch và liên kết vào dự án của bạn.

##### Vòng đời các lệnh Cargo thiết yếu trong công việc hàng ngày

1.  **`cargo check`:** Quét cú pháp và kiểm tra kiểu dữ liệu cực nhanh mà không tốn thời gian sinh mã máy thực thi. Đây là lệnh các lập trình viên Rust chạy liên tục trong quá trình viết mã để phát hiện lỗi sớm.
2.  **`cargo build`:** Biên dịch toàn bộ dự án ở chế độ phát triển (*debug mode*). Kết quả lưu tại `target/debug/hello_cargo`. Quá trình này tắt tối ưu hóa sâu (`opt-level = 0`) để tăng tốc độ biên dịch và giữ lại đầy đủ thông tin gỡ lỗi (*debug symbols*).
3. ▶ **`cargo run`:** Tự động kiểm tra thay đổi, biên dịch (nếu cần) và thực thi chương trình ngay lập tức.
4. **`cargo build --release`:** Biên dịch với profile `release`, mặc định có `opt-level = 3`. Các tối ưu hóa có thể cải thiện tốc độ nhưng không bảo đảm hiệu năng tối đa cho mọi chương trình. Tệp thực thi thường nằm tại `target/release/hello_cargo` (thêm `.exe` trên Windows).
5. **`Cargo.lock`:** Tệp khóa ghi lại phiên bản và nguồn đã phân giải của các gói; các gói từ registry còn có checksum. Nên đưa tệp này vào hệ thống quản lý phiên bản. `cargo build --locked` yêu cầu giữ nguyên kết quả phân giải; để tái lập tệp nhị phân còn phải kiểm soát toolchain, target, cờ biên dịch, build script và môi trường. `Cargo.lock` là tệp, không phải lệnh Cargo.
6. **`cargo fmt`, `cargo clippy`, `cargo test`:** Lần lượt định dạng mã, phát hiện vấn đề bằng phân tích tĩnh và chạy kiểm thử. Cài thành phần nếu còn thiếu bằng `rustup component add rustfmt clippy`.

---

<a id="chuong-02"></a>

### Chương 2. Dự án 1 — Trò chơi đoán số

Trò chơi sinh một số nguyên bí mật trong đoạn từ 1 đến 100. Người chơi nhập dự đoán; chương trình cho biết số đó nhỏ hơn, lớn hơn hay bằng số bí mật. Dự án giới thiệu nhập/xuất, biến khả biến, `match`, vòng lặp và `Result`.

#### 2.1. Tạo dự án và khai báo phụ thuộc

```bash
cargo new guessing_game --edition 2024
cd guessing_game
```

Nội dung `Cargo.toml`:

```toml
[package]
name = "guessing_game"
version = "0.1.0"
edition = "2024"
rust-version = "1.85"

[dependencies]
rand = "=0.9.2"
```

Ví dụ dùng API của dòng `rand 0.9`: `rand::rng()` và `Rng::random_range`. Dấu `=` khóa phiên bản phụ thuộc trực tiếp cho bài học; các phụ thuộc gián tiếp được ghi trong `Cargo.lock`. Không đổi phiên bản chính của thư viện mà giữ nguyên mã ví dụ. Xem [hướng dẫn chuyển sang rand 0.9](https://rust-random.github.io/book/update-0.9.html).

Từ khóa `gen` được bảo lưu trong Edition 2024, nhưng `gen_range` là một định danh khác và không bị cấm bởi quy tắc này.

#### 2.2. Mã nguồn hoàn chỉnh: `src/main.rs`

```rust
use rand::Rng;
use std::cmp::Ordering;
use std::io;

fn main() -> io::Result<()> {
    println!("TRÒ CHƠI ĐOÁN SỐ");
    let secret_number: u32 = rand::rng().random_range(1..=100);

    loop {
        println!("Nhập số từ 1 đến 100, hoặc nhập q để thoát:");
        let mut input = String::new();

        // read_line nối dữ liệu vào String và trả số byte đã đọc.
        // Ok(0) là kết thúc đầu vào (EOF); ? chuyển tiếp lỗi I/O.
        if io::stdin().read_line(&mut input)? == 0 {
            println!("Đã kết thúc đầu vào.");
            break;
        }

        let input = input.trim();
        if input.eq_ignore_ascii_case("q") {
            break;
        }

        let guess: u32 = match input.parse() {
            Ok(number) if (1..=100).contains(&number) => number,
            _ => {
                println!("Dữ liệu không hợp lệ. Hãy nhập số nguyên từ 1 đến 100.");
                continue;
            }
        };

        match guess.cmp(&secret_number) {
            Ordering::Less => println!("Quá nhỏ!"),
            Ordering::Greater => println!("Quá lớn!"),
            Ordering::Equal => {
                println!("Chính xác! Số bí mật là {secret_number}.");
                break;
            }
        }
    }

    Ok(())
}
```

#### 2.3. Giải thích các khái niệm

- **`let mut input`:** Chuỗi cần khả biến để `read_line` có thể thêm dữ liệu. Hàm không tự xóa nội dung cũ; ở đây mỗi lượt tạo một chuỗi rỗng mới.
- **`&mut input`:** Cho hàm mượn độc quyền chuỗi để ghi dữ liệu, không chuyển quyền sở hữu.
- **`io::Result<()>` và `?`:** `Ok(())` thể hiện hàm hoàn tất thành công. Khi đọc thất bại, `?` trả lỗi về từ `main`. Chương 13 trình bày cơ chế này chi tiết.
- **Shadowing:** `let input = input.trim()` tạo một ràng buộc mới có kiểu `&str`, mượn nội dung của chuỗi trước đó; nó không biến đổi kiểu của ràng buộc cũ.
- **`parse()` và `match`:** Chú thích `u32` giúp suy luận kiểu số cần phân tích. Nhánh có điều kiện `if` kiểm tra miền 1–100; dữ liệu sai được báo để người chơi thử lại.
- **`Ordering`:** enum có ba biến thể `Less`, `Greater`, `Equal`; `match` xử lý đủ ba trường hợp.

#### 2.4. Chạy và tự kiểm tra

```bash
cargo run
```

Thử lần lượt `abc`, `0`, `101` và một số hợp lệ. Ba giá trị đầu phải bị từ chối; một dự đoán hợp lệ nhận phản hồi so sánh. Nhập `q` hoặc kết thúc luồng nhập để thoát. **Bài tập:** Thêm bộ đếm số lần dự đoán hợp lệ và in kết quả khi thắng.

---

<a id="phan-ii"></a>

## Phần II. Nhập môn

---

<a id="chuong-03"></a>

### Chương 3. Biến, tính khả biến và phạm vi

Trong hầu hết các ngôn ngữ lập trình truyền thống, biến được tạo ra mặc định có thể gán lại giá trị tùy ý. Tuy nhiên, trong Rust, khái niệm cốt lõi là **ràng buộc biến (Variable Binding)**, và biến mặc định luôn luôn là **bất biến (immutable)**.

#### 3.1. Ràng buộc biến và tính bất biến mặc định

>  **Triết lý của Rust:** *Nếu một giá trị không cần thay đổi, đừng cho phép nó thay đổi.* Điều này giúp ngăn chặn hàng loạt lỗi logic tiềm ẩn khi dữ liệu bị thay đổi bất ngờ bởi các hàm khác hoặc trong môi trường đa luồng.

```rust
fn main() {
    let x = 5;
    println!("Giá trị của x là: {x}");
    // x = 6; // ❌ LỖI BIÊN DỊCH: cannot assign twice to immutable variable `x`
}
```

Khi bạn cố gắng gán lại giá trị cho biến bất biến `x`, trình biên dịch `rustc` sẽ chỉ ra chính xác dòng lỗi và gợi ý cách sửa:

```text
error[E0384]: cannot assign twice to immutable variable `x`
 --> src/main.rs:4:5
  |
2 |     let x = 5;
  |         - first assignment to `x`
3 |     println!("Giá trị của x là: {x}");
4 |     x = 6;
  |     ^^^^^ cannot assign twice to immutable variable
  |
help: consider making this binding mutable
  |
2 |     let mut x = 5;
  |         +++
```

---

#### 3.2. Tính khả biến với từ khóa `mut`

Để cho phép một biến thay đổi giá trị, bạn thêm từ khóa `mut` (*mutable*) ngay sau từ khóa `let`:

```rust
fn main() {
    let mut x = 5;
    println!("Giá trị ban đầu của x: {x}");
    x = 6; // ✅ Hợp lệ vì x được khai báo với mut
    println!("Giá trị mới của x: {x}");
}
```

---

#### 3.3. So sánh biến bất biến (`let`) và hằng số (`const`)

|  Đặc tính |  Biến bất biến (`let`) |  Hằng số (`const`) |
| :--- | :--- | :--- |
| **Khai báo cú pháp** | `let x = 5;` | `const MAX_POINTS: u32 = 100_000;` |
| **Bắt buộc chú thích kiểu?** | Không (Rust có thể tự suy luận) | **Bắt buộc** ghi rõ kiểu dữ liệu |
| **Tính khả biến (`mut`)** | Có thể thêm `mut` để thành biến khả biến | **Tuyệt đối không bao giờ** được dùng `mut` |
| **Thời điểm tính giá trị** | Có thể tính khi chạy hoặc được trình biên dịch tính trước | Thời điểm biên dịch (*compile-time constant expression*) |
| **Phạm vi khai báo** | Trong thân hàm hoặc khối lệnh | Mọi phạm vi, bao gồm cả phạm vi toàn cục (*global scope*) |
| **Quy ước đặt tên** | `snake_case` (ví dụ: `user_count`) | `SCREAMING_SNAKE_CASE` (ví dụ: `THREE_HOURS_IN_SECONDS`) |

```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

---

#### 3.4. Kỹ thuật che bóng (shadowing)

Rust cho phép bạn khai báo một biến mới có cùng tên với biến đã tồn tại trước đó. Biến mới này sẽ **che bóng (shadow)** biến cũ:

```rust
fn main() {
    let x = 5;
    let x = x + 1; // x mới (giá trị 6) che bóng x cũ

    {
        let x = x * 2; // x trong khối scope con (giá trị 12) che bóng x ngoài
        println!("Giá trị x trong khối lệnh con là: {x}"); // In ra 12
    }

    println!("Giá trị x ngoài khối lệnh là: {x}"); // In ra 6
}
```

##### Bảng đối chiếu shadowing (`let`) và khả biến (`let mut`)

| Tiêu chí | Khả biến (`let mut x`) | Che bóng biến (`let x = ...; let x = ...;`) |
| :--- | :--- | :--- |
| **Đổi giá trị** |  Được |  Được |
| **Đổi kiểu dữ liệu** |  **Không được** (giữ nguyên kiểu ban đầu) |  **Được phép** (tạo biến hoàn toàn mới) |
| **Tính bất biến** | Biến vẫn có thể bị sửa tiếp sau này | Biến mới mặc định bất biến sau phép gán `let` |

```rust
// ✅ HỢP LỆ VỚI SHADOWING (đổi từ kiểu &str sang usize):
let spaces = "   ";
let spaces = spaces.len();

// ❌ LỖI BIÊN DỊCH NẾU DÙNG MUT:
let mut spaces = "   ";
// spaces = spaces.len(); // LỖI: expected `&str`, found `usize`
```

---

#### 3.5. Phạm vi biến (scope)

Phạm vi (*scope*) là vùng không gian mã nguồn mà một biến có hiệu lực, được giới hạn bởi cặp ngoặc nhọn `{}`:

```rust
fn main() {
    // s chưa xuất hiện ở đây
    {
        let s = "hello"; // s bắt đầu hợp lệ từ dòng này
        println!("{s}"); // sử dụng s bình thường
    } // s hết phạm vi; dữ liệu của chuỗi literal vẫn tồn tại trong chương trình.
}
```

---

<a id="chuong-04"></a>

### Chương 4. Kiểu dữ liệu cơ bản, hàm và luồng điều khiển

Rust là ngôn ngữ **định kiểu tĩnh (statically typed)**: mọi biến đều phải xác định được kiểu dữ liệu tại thời điểm biên dịch. Nhờ cơ chế **suy luận kiểu (type inference)** thông minh, trình biên dịch tự động nhận biết kiểu của hầu hết các biến, và chỉ yêu cầu chú thích tường minh khi có nhiều kiểu khả dĩ (như `.parse()`).

#### 4.1. Kiểu dữ liệu vô hướng (scalar types)

Kiểu vô hướng đại diện cho một giá trị đơn lẻ. Phần này giới thiệu bốn nhóm kiểu vô hướng, sau đó bổ sung kiểu đơn vị `()` (một tuple rỗng, không phải kiểu vô hướng):

##### 1. Kiểu số nguyên (integers)

Số nguyên gồm số có dấu (`i` - *signed*, lưu được số âm và dương) và số không dấu (`u` - *unsigned*, chỉ lưu số không âm).

| Số bit | Kiểu có dấu | Miền giá trị có dấu | Kiểu không dấu | Miền giá trị không dấu |
| :--- | :--- | :--- | :--- | :--- |
| 8 | `i8` | −128 đến 127 | `u8` | 0 đến 255 |
| 16 | `i16` | −32 768 đến 32 767 | `u16` | 0 đến 65 535 |
| 32 | `i32` | $-2^{31}$ đến $2^{31}-1$ | `u32` | 0 đến $2^{32}-1$ |
| 64 | `i64` | $-2^{63}$ đến $2^{63}-1$ | `u64` | 0 đến $2^{64}-1$ |
| 128 | `i128` | $-2^{127}$ đến $2^{127}-1$ | `u128` | 0 đến $2^{128}-1$ |
| Theo target | `isize` | Theo độ rộng con trỏ của target | `usize` | Theo độ rộng con trỏ của target |

`i32` là kiểu mặc định của literal số nguyên khi ngữ cảnh không xác định kiểu khác. `usize` được dùng cho độ dài và chỉ mục tập hợp; kích thước của nó phụ thuộc target biên dịch, thường là 32 hoặc 64 bit.

*Các dạng biểu diễn hằng số nguyên (Integer Literals):*

- Số thập phân (Decimal): `98_222` (dấu `_` giúp dễ đọc, giá trị là 98222).
- Số thập lục phân (Hex): `0xff`.
- Số bát phân (Octal): `0o77`.
- Số nhị phân (Binary): `0b1111_0000`.
- Byte ký tự (chỉ dành cho `u8`): `b'A'`.

*Hiện tượng tràn số nguyên (Integer Overflow):*
Giả sử một biến kiểu `u8` (miền giá trị từ 0 đến 255) đang mang giá trị 255 và được cộng thêm 1:

- **Mặc định ở profile `dev`:** Phép cộng tràn số khi chạy gây `panic`.
- **Mặc định ở profile `release`:** Phép cộng tràn số quay vòng, ví dụ `u8` cộng từ 255 lên 256 cho kết quả 0. Hành vi này phụ thuộc tùy chọn `overflow-checks`, có thể cấu hình lại. Phép toán tràn mà trình biên dịch nhận ra trực tiếp có thể bị báo lỗi ngay khi biên dịch; chia số nguyên cho 0 vẫn gây `panic`, kể cả ở release.
- **Xử lý tràn số tường minh an toàn:** Thư viện chuẩn cung cấp 4 nhóm phương thức cho số nguyên:
  - `wrapping_*` (ví dụ `255u8.wrapping_add(1)` $\rightarrow 0$).
  - `checked_*` (ví dụ `255u8.checked_add(1)` $\rightarrow$ trả về `None` nếu tràn).
  - `overflowing_*` (ví dụ `255u8.overflowing_add(1)` $\rightarrow$ trả về tuple `(0, true)`).
  - `saturating_*` (ví dụ `255u8.saturating_add(10)` $\rightarrow$ chạm trần tại giá trị cực đại 255).

##### 2. Kiểu số thực dấu phẩy động (floating-point types)

Tuân theo chuẩn IEEE 754:

- `f32`: Độ chính xác đơn (*Single precision* - 32-bit).
- `f64`: Độ chính xác kép (*Double precision* - 64-bit). **Mặc định là `f64`** khi không có ngữ cảnh yêu cầu kiểu khác. `f32` dùng ít bộ nhớ hơn; hiệu năng phụ thuộc phần cứng và bài toán. Số thực nhị phân không biểu diễn chính xác mọi số thập phân, vì vậy không dùng phép `==` để kiểm tra kết quả gần đúng nếu chưa xét sai số.

```rust
let x = 2.0;      // f64 (mặc định)
let y: f32 = 3.0; // f32
```

##### 3. Kiểu logic (boolean)

Từ khóa `bool`, nhận hai giá trị `true` hoặc `false`, chiếm đúng 1 byte bộ nhớ.

##### 4. Kiểu ký tự (character)

Từ khóa `char`, đặt trong dấu nháy đơn `'a'`, chiếm **4 byte (32-bit)** bộ nhớ. Đại diện cho một *Unicode Scalar Value* trong dải từ $\text{U+0000}$ đến $\text{U+D7FF}$ và $\text{U+E000}$ đến $\text{U+10FFFF}$. Một `char` biểu diễn một giá trị vô hướng Unicode; một ký tự người dùng nhìn thấy có thể cần nhiều `char`, như chữ kèm dấu tổ hợp hoặc emoji ghép. Ví dụ các giá trị đơn:
```rust
let c = 'z';
let vietnamese_char = 'ệ';
let crab_emoji = '🦀';
```

##### 5. Kiểu đơn vị (unit type `()`)

Tuple rỗng `()` chỉ có một giá trị duy nhất là `()` và có kích thước **0 byte (Zero-Sized Type - ZST)**. Hàm không khai báo kiểu trả về có kiểu trả về mặc định là `()`. Khối lệnh kết thúc bình thường mà không có biểu thức cuối cũng có giá trị `()`; biểu thức không bao giờ kết thúc có thể có kiểu `!`.

---

#### 4.2. Kiểu dữ liệu phức hợp cơ bản (compound types)

##### 1. Bộ giá trị (tuple)

Gom nhóm nhiều giá trị có **nhiều kiểu dữ liệu khác nhau** thành một đơn vị duy nhất, kích thước cố định sau khi khai báo:

```rust
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);

    // Kỹ thuật phân rã cấu trúc (Destructuring):
    let (x, y, z) = tup;
    println!("Giá trị y là: {y}");

    // Truy xuất trực tiếp qua chỉ mục bằng dấu chấm:
    let five_hundred = tup.0;
    let six_point_four = tup.1;
    let one = tup.2;
}
```

##### 2. Mảng tĩnh (array `[T; N]`)

- Mọi phần tử trong mảng phải có **cùng một kiểu dữ liệu `T`**.
- Mảng có **độ dài cố định `N`** là một phần của kiểu. Mảng lưu các phần tử liên tiếp ngay trong giá trị của nó; vị trí thực tế có thể ở stack, trong một cấu trúc trên heap, vùng tĩnh hoặc được tối ưu hóa vào thanh ghi.

```rust
fn main() {
    let a: [i32; 5] = [1, 2, 3, 4, 5];

    // Khởi tạo mảng gồm 5 phần tử đều có giá trị ban đầu là 0:
    let zeros = [0; 5]; // Tương đương: [0, 0, 0, 0, 0]

    let first = a[0];
    let second = a[1];
    println!("Phần tử đầu tiên: {first}, thứ hai: {second}");
}
```

*An toàn bộ nhớ kiểm tra biên (Bounds Checking):*
Truy xuất vượt biên bằng `a[index]` gây `panic` khi chạy; trường hợp hiển nhiên có thể bị chẩn đoán ngay khi biên dịch. Dùng `a.get(index)` nếu cần nhận `Option<&T>` và tự xử lý chỉ mục không hợp lệ.

---

#### 4.3. Câu lệnh (statement) và biểu thức (expression)

Đây là một trong những đặc điểm thiết kế cốt lõi nhất của Rust:

- **Câu lệnh (Statement):** Thực hiện một hành động nhưng **không trả về giá trị** (ví dụ: `let x = 6;`). Do đó, bạn không thể viết `let x = (let y = 6);`.
- **Biểu thức (Expression):** Có kiểu và thường tạo ra một giá trị; một số biểu thức như `return` hay vòng lặp vô hạn không hoàn tất bình thường. Các phép toán, lời gọi hàm, biểu thức `if`, `match`, `loop` và **khối lệnh `{}`** đều là biểu thức!

```rust
fn main() {
    let y = {
        let x = 3;
        x + 1 // 💡 Biểu thức trả về giá trị 4 (KHÔNG có dấu chấm phẩy ở cuối!)
    };

    println!("Giá trị của y là: {y}"); // In ra 4
}
```
>  **Quy tắc vàng:** Nếu bạn thêm dấu chấm phẩy `;` vào cuối dòng `x + 1;`, dòng đó trở thành câu lệnh biểu thức; khối không còn biểu thức cuối nên có giá trị `()`. Khi đó `y` nhận kiểu `()`, khiến phép in `{y}` trong ví dụ không biên dịch vì `()` không triển khai `Display`.

---

#### 4.4. Định nghĩa hàm (functions)

Hàm được khai báo bằng `fn`. Tham số hàm bắt buộc phải chú thích kiểu dữ liệu tường minh, và kiểu trả về đặt sau mũi tên `->`:

```rust
fn print_labeled_measurement(value: i32, unit_label: char) {
    println!("Đo lường: {value}{unit_label}");
}

fn add_numbers(a: i32, b: i32) -> i32 {
    a + b // Biểu thức cuối cùng tự động là giá trị trả về (không có dấu ;)
}

fn main() {
    print_labeled_measurement(5, 'h');
    let sum = add_numbers(10, 20);
    println!("Tổng là: {sum}");
}
```

---

#### 4.5. Cấu trúc luồng điều khiển (control flow)

##### 1. Biểu thức điều kiện `if`

Điều kiện trong `if` bắt buộc phải là kiểu `bool`. Vì `if` là một biểu thức, bạn có thể dùng nó ngay bên phải câu lệnh `let` (hai nhánh `if` và `else` phải có kiểu tương thích sau các phép chuyển đổi được ngôn ngữ cho phép):

```rust
fn main() {
    let condition = true;
    let number = if condition { 5 } else { 6 };

    if number % 4 == 0 {
        println!("Chia hết cho 4");
    } else if number % 3 == 0 {
        println!("Chia hết cho 3");
    } else {
        println!("Không chia hết cho 4 hoặc 3");
    }
}
```

##### 2. Vòng lặp `loop`, trả về giá trị từ `break` và nhãn vòng lặp (`'label`)

```rust
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;
        if counter == 10 {
            break counter * 2; // ✅ Thoát vòng lặp và trả về giá trị 20!
        }
    };
    println!("Kết quả từ loop: {result}");

    // Nhãn vòng lặp (Loop Labels) để thoát khỏi vòng lặp lồng nhau:
    let mut count = 0;
    'counting_up: loop {
        let mut remaining = 10;
        loop {
            if remaining == 9 {
                break; // Chỉ thoát vòng lặp bên trong
            }
            if count == 2 {
                break 'counting_up; // 🚀 Thoát hẳn vòng lặp ngoài cùng!
            }
            remaining -= 1;
        }
        count += 1;
    }
}
```

##### 3. Vòng lặp điều kiện `while` và vòng lặp tập hợp `for`

```rust
fn main() {
    let mut number = 3;
    while number != 0 {
        println!("{number}!");
        number -= 1;
    }

    let a = [10, 20, 30, 40, 50];
    for element in a {
        println!("Giá trị phần tử: {element}");
    }

    // Lặp qua dải số đếm ngược từ 3 về 1:
    for n in (1..4).rev() {
        println!("Đếm ngược: {n}!");
    }
    println!("🚀 PHÓNG TÊN LỬA!");
}
```

---

<a id="phan-iii"></a>

## Phần III. Quyền sở hữu và mượn

---

<a id="chuong-05"></a>

### Chương 5. Quyền sở hữu và mượn

**Quyền sở hữu (ownership)** xác định ai chịu trách nhiệm quản lý một giá trị và khi nào tài nguyên của nó được thu hồi. Rust kiểm tra quyền sở hữu và mượn bằng hệ thống kiểu, đồng thời sinh mã hủy tài nguyên khi cần. Cơ chế này không đòi hỏi bộ thu gom rác truy vết, nhưng cấp phát, giải phóng và một số kiểu quản lý tài nguyên vẫn có chi phí khi chạy.

#### 5.1. Các cách quản lý bộ nhớ

Có nhiều cách quản lý tài nguyên; các ngôn ngữ có thể kết hợp hơn một cách:

| Cách tiếp cận | Cơ chế chính | Đánh đổi cần hiểu |
| :--- | :--- | :--- |
| Quản lý thủ công | Chương trình chủ động cấp phát và giải phóng | Linh hoạt nhưng dễ sai vòng đời khi dùng con trỏ không đúng |
| RAII và con trỏ thông minh | Gắn tài nguyên với vòng đời đối tượng; C++ hiện đại và Rust đều sử dụng ý tưởng này | Cần thiết kế rõ quan hệ sở hữu; cách bảo đảm an toàn khác nhau theo ngôn ngữ |
| Thu hồi tự động | Truy vết đối tượng hoặc đếm tham chiếu tùy runtime | Chi phí bộ nhớ, thời gian và độ trễ tùy bộ thu hồi; không nên quy về một mô hình duy nhất |
| Quyền sở hữu của Rust | Kiểm tra tĩnh việc chuyển và mượn giá trị; tự động hủy theo vòng đời | Cần biểu đạt được quan hệ sở hữu; một số nhu cầu dùng đếm tham chiếu hoặc kiểm tra mượn khi chạy |

Borrow checker không thêm một bộ kiểm tra quyền sở hữu chạy nền. Điều đó không có nghĩa mọi thao tác quản lý bộ nhớ đều miễn phí: `Box` có thể cấp phát heap, `Rc` cập nhật bộ đếm và `Arc` cập nhật bộ đếm nguyên tử.

---

#### 5.2. Stack, heap và bố cục của String

Stack thường chứa các khung lời gọi hàm và dữ liệu cục bộ; việc cấp phát, thu hồi theo khung thường đơn giản. heap phục vụ các vùng nhớ có vòng đời hoặc kích thước linh hoạt và được truy cập qua con trỏ. Đây là mô hình giải thích hữu ích, không phải quy tắc khẳng định mọi giá trị của một kiểu phải nằm ở một vùng nhớ nhất định.

| Đặc điểm | stack | heap |
| :--- | :--- | :--- |
| Tổ chức thường gặp | Khung lời gọi, thu hồi theo thứ tự gọi hàm | Các vùng cấp phát có vòng đời độc lập |
| Cấp phát | Thường chỉ điều chỉnh vị trí stack | Thông qua bộ cấp phát, có chi phí tùy tình huống |
| Dữ liệu | Có thể chứa giá trị hoặc con trỏ quản lý dữ liệu khác | Có thể chứa cả giá trị có kích thước cố định lẫn bộ đệm co giãn |
| Hiệu năng | Phụ thuộc truy cập, bộ nhớ đệm và tối ưu hóa | Không phải mọi truy cập heap đều chậm hơn truy cập stack |

**Mô hình của `String`:** Một `String` quản lý con trỏ tới bộ đệm UTF-8, độ dài và dung lượng theo byte. Ví dụ `String::from("hello")` có `len = 5`, còn `capacity >= 5`. Trên target 64 bit thông dụng, giá trị quản lý có kích thước 24 byte; bộ đệm chứa năm byte `h`, `e`, `l`, `l`, `o` ở vùng cấp phát riêng.

Giá trị `String` có thể nằm trên stack, trong một `Box`, trong phần tử `Vec` hoặc vị trí khác. Không dựa vào thứ tự trường nội bộ như một cam kết ABI. `String::new()` chưa cần cấp phát bộ đệm heap.

---

#### 5.3. Ba quy tắc nhập môn về quyền sở hữu

Ba quy tắc nhập môn về quyền sở hữu:

1. Mỗi giá trị có một chủ sở hữu chịu trách nhiệm quản lý nó.
2. Với sở hữu độc quyền, tại một thời điểm chỉ có một chủ sở hữu; phép move chuyển trách nhiệm đó sang vị trí mới.
3. Khi chủ sở hữu kết thúc vòng đời mà chưa chuyển giá trị đi, Rust thực hiện cơ chế hủy giá trị và tài nguyên do nó quản lý.

Chủ sở hữu có thể là biến, trường của struct hoặc phần tử của tập hợp. `Rc` và `Arc` cho phép **sở hữu chia sẻ** bằng các handle đếm tham chiếu; dữ liệu bên trong thường bị hủy khi handle mạnh cuối cùng bị hủy. Safe Rust vẫn cho phép rò rỉ bộ nhớ, chẳng hạn vòng tham chiếu mạnh hoặc `std::mem::forget`. Việc kết thúc tiến trình bằng `abort` cũng không chạy đầy đủ các hàm hủy.

---

#### 5.4. Cơ chế dịch chuyển quyền sở hữu (move semantics)

Hãy xem chuyện gì xảy ra khi gán biến `s1` cho `s2`:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1; // ⚡ Quyền sở hữu chuyển từ s1 sang s2. s1 bị vô hiệu hóa!

    // println!("{s1}"); // ❌ LỖI BIÊN DỊCH: borrow of moved value: `s1`
    println!("{s2}");    // ✅ Hợp lệ!
}
```

##### Tại sao Rust không dùng shallow Copy mà dùng move?

- Nếu Rust chỉ sao chép con trỏ trên stack (*Shallow Copy*) và giữ cả `s1` lẫn `s2` hợp lệ, thì cả hai biến sẽ cùng trỏ vào một vùng nhớ trên heap. Khi kết thúc hàm, cả `s1` và `s2` sẽ cùng gọi hàm `drop` để giải phóng cùng một vùng nhớ hai lần (**Double Free Error**) — một lỗ hổng bảo mật cực kỳ nguy hiểm!
- **Giải pháp của Rust:** Về ngữ nghĩa, Rust chuyển giá trị quản lý của `String` sang `s2` và không cho dùng lại `s1` như một giá trị còn hợp lệ. Trình biên dịch có thể tối ưu bỏ thao tác sao chép vật lý. Hành động này gọi là **Move (Dịch chuyển quyền sở hữu)**. Khi kết thúc scope, chỉ một mình `s2` giải phóng bộ nhớ heap. Nội dung bộ đệm heap không cần được nhân bản; quyền sở hữu tránh việc hai biến cùng giải phóng bộ đệm trong ví dụ này.

---

#### 5.5. Clone và Copy: hai cách sao chép khác nhau

##### 1. `String::clone()` nhân bản nội dung chuỗi

`Clone` nói chung không bảo đảm sao chép sâu. Ví dụ `Rc::clone()` và `Arc::clone()` tạo handle cùng sở hữu dữ liệu, không nhân bản dữ liệu bên trong.
Khi bạn thực sự muốn nhân bản cả dữ liệu trên heap để có hai biến độc lập:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1.clone(); // Cấp phát vùng nhớ mới trên Heap và sao chép nội dung

    println!("s1 = {s1}, s2 = {s2}"); // ✅ Cả hai đều hợp lệ!
}
```

##### 2. Trait `Copy` và sao chép ngầm định

**`Copy` là một trait**, không phải hệ quả của việc dữ liệu nằm trên stack. Một kiểu triển khai `Copy` cho phép phép gán sao chép giá trị mà không làm mất hiệu lực biến nguồn. Kiểu có `Drop` không thể triển khai `Copy`; kiểu tự định nghĩa cần triển khai hoặc dẫn xuất trait này. Chi phí sao chép phụ thuộc kích thước giá trị, chẳng hạn mảng lớn vẫn có thể tốn nhiều công sức sao chép:

```rust
fn main() {
    let x = 5;
    let y = x; // i32 có trait Copy nên x không bị Move!
    println!("x = {x}, y = {y}"); // ✅ Hợp lệ!
}
```

*Danh sách các kiểu cài đặt `Copy`:*

- Mọi kiểu số nguyên (`i32`, `u64`, `usize`,...), số thực (`f32`, `f64`), `bool`, `char`.
- Tham chiếu chia sẻ `&T` có `Copy`; tham chiếu độc quyền `&mut T` không có `Copy`.
- Tuple và Array cố định, **nếu mọi phần tử bên trong nó đều có `Copy`** (ví dụ: `(i32, bool)` có `Copy`, nhưng `(i32, String)` thì không).

---

#### 5.6. Quyền sở hữu trong hàm

Truyền một biến vào hàm có cơ chế hoàn toàn giống như phép gán:

```rust
fn main() {
    let s = String::from("hello");
    takes_ownership(s); // 🚚 Quyền sở hữu của s chuyển vào hàm
    // println!("{s}"); // ❌ LỖI: s không còn hợp lệ ở đây!

    let x = 5;
    makes_copy(x);      // 📋 x được sao chép vì i32 có trait Copy
    println!("x vẫn dùng được: {x}"); // ✅ Hợp lệ!
}

fn takes_ownership(some_string: String) {
    println!("{some_string}");
} // some_string ra khỏi scope, hàm drop được gọi, bộ nhớ Heap được giải phóng!

fn makes_copy(some_integer: i32) {
    println!("{some_integer}");
}
```

---

#### 5.7. Cơ chế mượn (borrowing) và tham chiếu (references)

Thay vì chuyển giao quyền sở hữu vào hàm rồi lại phải trả về, Rust cho phép tạo một **Tham chiếu (Reference)** trỏ đến giá trị mà không sở hữu nó. Hành động tạo tham chiếu gọi là **Mượn (Borrowing)**.

##### 1. Tham chiếu bất biến (`&T` - shared borrow)

Cho phép đọc dữ liệu. Không thể sửa trực tiếp dữ liệu thông thường qua `&T`; các kiểu có tính khả biến nội tại như `RefCell` và `Mutex` cung cấp API sửa đổi với quy tắc riêng:

```rust
fn main() {
    let s1 = String::from("hello");
    let len = calculate_length(&s1); // Cho mượn tham chiếu bất biến &s1
    println!("Độ dài của '{s1}' là {len}."); // ✅ s1 vẫn thuộc sở hữu của main!
}

fn calculate_length(s: &str) -> usize {
    s.len()
} // s ra khỏi scope, nhưng vì s chỉ mượn (không sở hữu) nên không giải phóng gì cả!
```

##### 2. Tham chiếu khả biến (`&mut T` - exclusive borrow)

Cho phép sửa đổi trực tiếp giá trị đang mượn:

```rust
fn main() {
    let mut s = String::from("hello");
    change(&mut s); // Truyền tham chiếu khả biến
    println!("{s}"); // In ra: hello, world!
}

fn change(some_string: &mut String) {
    some_string.push_str(", world!");
}
```

---

#### 5.8. Quy tắc bất biến của borrow checker và non-lexical lifetimes (NLL)

> **Quy tắc mượn:** Trong thời gian mượn cùng một vùng dữ liệu, có thể có nhiều tham chiếu chia sẻ hoặc một tham chiếu độc quyền đang được sử dụng. Không được đọc hoặc ghi qua đường truy cập xung đột với phép mượn còn hiệu lực.

Rust có thể cho mượn khả biến các trường hoặc lát cắt không chồng lấn; có thể mượn lại qua một tham chiếu khi tham chiếu trước tạm thời không được dùng. Các kiểu khả biến nội tại cung cấp thêm cơ chế kiểm tra hoặc đồng bộ hóa. Cùng với `Send` và `Sync`, những quy tắc này giúp ngăn data race trong Safe Rust; chúng không ngăn mọi race condition hay deadlock.

##### Cơ chế non-lexical lifetimes (NLL)

NLL phân tích luồng điều khiển để thu hẹp thời gian mượn đến phần thực sự cần thiết, thường kết thúc sau lần sử dụng cuối. Điều này khác với phạm vi tên biến và thời điểm chạy hàm hủy. Trong ví dụ tuyến tính sau, phép mượn chia sẻ kết thúc trước khi tạo phép mượn độc quyền:

```rust
fn main() {
    let mut s = String::from("hello");

    let r1 = &s;     // ✅ Mượn bất biến 1
    let r2 = &s;     // ✅ Mượn bất biến 2
    println!("{r1} và {r2}"); // 🏁 Lần cuối cùng r1 và r2 được sử dụng!

    // ✅ Từ dòng này trở đi, r1 và r2 đã kết thúc vòng đời mượn,
    // nên việc tạo tham chiếu khả biến r3 hoàn toàn hợp lệ!
    let r3 = &mut s;
    r3.push_str("!");
    println!("{r3}");
}
```

---

#### 5.9. Ngăn chặn con trỏ lơ lửng (dangling references)

Trong C/C++, nếu bạn trả về địa chỉ của một biến cục bộ trong hàm, con trỏ đó sẽ trỏ vào vùng nhớ rác ngay khi hàm kết thúc. Trong Rust, Borrow Checker chặn đứng lỗi này ngay lập tức:

```rust
// ❌ LỖI BIÊN DỊCH: returns a reference to data owned by the current function
// fn dangle() -> &String {
//     let s = String::from("hello");
//     &s
// } // s bị giải phóng ở đây, tham chiếu &s sẽ trở thành lơ lửng!

// ✅ GIẢI PHÁP: Trả về trực tiếp quyền sở hữu của String
fn no_dangle() -> String {
    let s = String::from("hello");
    s // Quyền sở hữu được Move ra ngoài an toàn!
}
```

---

#### 5.10. Kiểu lát cắt (slices)

Kiểu lát cắt `[T]` biểu diễn một dãy phần tử liên tiếp có độ dài không nằm trong kiểu. Ta thường thao tác qua `&[T]` hoặc `&mut [T]`; những tham chiếu này không sở hữu dữ liệu. Tương tự, `str` là kiểu lát cắt chuỗi và `&str` là tham chiếu tới chuỗi UTF-8 hợp lệ.

```rust
fn main() {
    let s = String::from("hello world");

    let hello: &str = &s[0..5];  // Từ byte 0 đến byte 4
    let world: &str = &s[6..11]; // Từ byte 6 đến byte 10

    // Cú pháp rút gọn:
    let slice1 = &s[..5]; // Tương đương &s[0..5]
    let slice2 = &s[6..]; // Tương đương &s[6..len]
    let slice3 = &s[..];  // Lấy toàn bộ chuỗi
    println!("{hello} - {world} ({slice1}, {slice2}, {slice3})");
}
```

##### Quy ước thiết kế hàm tối ưu với `&str`

Khi hàm chỉ cần đọc nội dung chuỗi, thường nên nhận `&str` thay vì `&String`. Nhờ cơ chế *Deref Coercion*, hàm nhận `&str` có thể truyền vào cả `&str` lẫn `&String`!

```rust
fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();

    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i];
        }
    }
    &s[..]
}
```

Hàm `first_word` ở trên chỉ tách theo dấu cách ASCII `b' ', không nhận diện mọi khoảng trắng Unicode. Với yêu cầu rộng hơn, có thể dùng `split_whitespace().next()`. Chỉ mục dùng để cắt `str` phải nằm trên biên ký tự UTF-8.

Ví dụ lát cắt mảng: `let a = [10, 20, 30]; let middle: &[i32] = &a[1..];`.

> **Thử thách tư duy rustacean (phần iii)**
> **Câu hỏi:** Đoạn mã sau có biên dịch thành công không? Tại sao?
> ```rust,compile_fail
> fn first_word(s: &str) -> &str {
>     s.split_whitespace().next().unwrap_or("")
> }
>
> fn main() {
>     let mut s = String::from("Rust 2024");
>     let word = first_word(&s);
>     s.clear();
>     println!("Từ đầu tiên là: {word}");
> }
> ```
> **Giải đáp:** **không biên dịch được!** Hàm `first_word(&s)` mượn bất biến biến `s` và trả về lát cắt `word` cũng gắn liền với mượn bất biến của `s`. Ở dòng tiếp theo, `s.clear()` yêu cầu một **mượn khả biến (`&mut s`)** để xóa nội dung chuỗi, trong khi `word` (mượn bất biến) vẫn còn được sử dụng ở lệnh `println!` phía dưới. Điều này vi phạm quy tắc vàng của Borrow Checker: *Không thể vừa mượn bất biến vừa mượn khả biến tại cùng một thời điểm!*

---

<a id="phan-iv"></a>

## Phần IV. Kiểu phức hợp và khớp mẫu

---

<a id="chuong-06"></a>

### Chương 6. Chuỗi ký tự: String và &str

Chuỗi ký tự trong Rust phân biệt rõ ràng giữa **chuỗi sở hữu (`String`)** và **lát cắt chuỗi mượn (`&str`)**, đồng thời thực thi nghiêm ngặt chuẩn mã hóa **UTF-8**.

#### 6.1. Bản chất mã hóa UTF-8 và ba góc nhìn về chuỗi

Tại sao trong Rust bạn **không thể** viết `s[0]` để lấy ký tự đầu tiên của chuỗi?
UTF-8 mã hóa mỗi giá trị vô hướng Unicode bằng **1 đến 4 byte**; một cụm ký tự hiển thị có thể gồm nhiều giá trị vô hướng:

- Chữ cái tiếng Anh ASCII (`"hello"`) mỗi ký tự chiếm 1 byte.
- Trong `"Việt"`, các chữ `V`, `i`, `t` là ASCII, còn `ệ` chiếm 3 byte. Các chữ Cyrillic trong `"Здравствуйте"` chiếm 2 byte mỗi chữ.
- Biểu tượng cảm xúc Emoji (`"🦀"`) chiếm 4 byte.

Rust không định nghĩa chỉ mục nguyên cho chuỗi vì “phần tử thứ n” có thể được hiểu là byte, `char` hoặc cụm ký tự hiển thị. Dùng `s.as_bytes().get(n)` để đọc byte và `s.chars().nth(n)` để tìm giá trị vô hướng thứ n (cần duyệt, không bảo đảm O(1)). Việc tách cụm ký tự hiển thị cần một thư viện chuyên về Unicode, chẳng hạn `unicode-segmentation`.

##### Ba góc nhìn về chuỗi trong Rust (ví dụ chuỗi `"Việt"`)

1. **Dưới góc nhìn Bytes (`u8`):** Gồm 6 byte: `[86, 105, 225, 187, 135, 116]` (trong đó riêng chữ `'ệ'` được mã hóa bởi 3 byte `[225, 187, 135]`).
2. **Dưới góc nhìn Scalar Values (`char`):** Gồm 4 ký tự Unicode: `['V', 'i', 'ệ', 't']`.
3. **Dưới góc nhìn Grapheme Clusters (Cụm ký tự hiển thị mắt người nhìn thấy):** `"V"`, `"i"`, `"ệ"`, `"t"`.

```rust
fn main() {
    let word = "Việt";

    println!("Số lượng bytes: {}", word.len()); // 6 bytes!

    // 1. Duyệt theo từng ký tự Unicode (char):
    print!("Các ký tự char: ");
    for c in word.chars() {
        print!("'{c}' ");
    }
    println!();

    // 2. Duyệt theo từng byte thô (u8):
    print!("Các byte thô: ");
    for b in word.bytes() {
        print!("{b} ");
    }
    println!();
}
```

---

#### 6.2. Bảng đối chiếu `String` và `&str`

|  Tiêu chí |  `String` |  `&str` (String Slice) |
| :--- | :--- | :--- |
| **Vùng nhớ lưu trữ** | Dữ liệu nằm trên **heap**, co giãn động | Tham chiếu tới vùng nhớ UTF-8 (trên heap, stack hoặc Binary tĩnh) |
| **Quyền sở hữu** | Sở hữu dữ liệu (*Owned type*) | Chỉ mượn dữ liệu (*Borrowed view*) |
| **Kích thước giá trị quản lý trên target 64 bit thông dụng** | 24 byte: con trỏ, độ dài, dung lượng | 16 byte: con trỏ và độ dài; không bao gồm dữ liệu chuỗi |
| **Khả năng chỉnh sửa** | Thêm, nối, xóa ký tự linh hoạt (với `mut`) | Bất biến (chỉ đọc) |

---

`&s[a..b]` dùng chỉ mục byte và gây `panic` nếu vượt biên hoặc cắt giữa một ký tự UTF-8. Có thể kiểm tra mà không gây `panic` bằng `s.get(a..b)`:

```rust
fn main() {
    let s = "Việt";
    assert_eq!(s.get(2..5), Some("ệ"));
    assert_eq!(s.get(2..3), None);

    // Hai cách mã hóa cùng một hình thức hiển thị, nhưng không có cùng dãy byte.
    let composed = "ệ";
    let decomposed = "e\u{0323}\u{0302}";
    assert_ne!(composed, decomposed);
    assert_eq!(composed.chars().count(), 1);
    assert_eq!(decomposed.chars().count(), 3);
}
```

Rust không tự chuẩn hóa Unicode khi so sánh chuỗi. Nếu nghiệp vụ cần xem các dạng tổ hợp tương đương là như nhau, hãy chọn một chính sách chuẩn hóa rõ ràng.

#### 6.3. Các phép toán thao tác chuỗi thường dùng

```rust
fn main() {
    // Khởi tạo và nối chuỗi:
    let mut s = String::from("Xin chào");
    s.push(' ');            // Thêm 1 ký tự char
    s.push_str("Việt Nam"); // Nối thêm một lát cắt &str

    // Nối chuỗi bằng toán tử + (chú ý: s1 bị Move, s2 truyền tham chiếu):
    let s1 = String::from("Rust ");
    let s2 = String::from("2024");
    let s3 = s1 + &s2; // Chữ ký hàm: fn add(self, s: &str) -> String

    // Ghép chuỗi phức tạp bằng macro format! (KHÔNG chiếm quyền sở hữu của bất kỳ biến nào):
    let a = String::from("tic");
    let b = String::from("tac");
    let c = String::from("toe");
    let game = format!("{a}-{b}-{c}");
    println!("{s} | {s3} | {game}");
}
```

---

<a id="chuong-07"></a>

### Chương 7. Kiểu dữ liệu tùy chỉnh: struct và enum

#### 7.1. Cấu trúc dữ liệu structs (structures)

Struct cho phép gom nhóm nhiều trường dữ liệu có liên quan lại thành một kiểu dữ liệu có tên rõ ràng.

```rust
#[derive(Debug)] // Cho phép in gỡ lỗi bằng {:?} hoặc {:#?}
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn build_user(email: String, username: String) -> User {
    User {
        active: true,
        username, // Cú pháp rút gọn Field Init Shorthand
        email,
        sign_in_count: 1,
    }
}

fn main() {
    let user1 = build_user(
        String::from("viet@example.com"),
        String::from("thaiviet"),
    );

    // Cú pháp cập nhật Struct Update Syntax (..):
    let user2 = User {
        email: String::from("ozsx@example.com"),
        ..user1 // Lấy các trường còn lại từ user1 (chú ý: user1.username bị Move sang user2!)
    };

    println!("Thông tin user2: {user2:#?}");
}
```

##### Các dạng struct đặc biệt

1. **Tuple struct:** Có tên kiểu nhưng các trường không đặt tên. Rất hữu ích để tạo kiểu mới phân biệt ngữ nghĩa (*Newtype Pattern*):
   ```rust
   struct Color(i32, i32, i32);
   struct Point(i32, i32, i32);
   ```
2. **Unit-Like struct:** Không có bất kỳ trường nào (`struct AlwaysEqual;`), kích thước bằng 0 byte (*ZST*), dùng khi cần cài đặt một trait trên một kiểu mà không cần lưu trữ trạng thái dữ liệu.

---

#### 7.2. Kiểu liệt kê enums và vũ khí `Option<T>`

Trong khi struct gom các trường cùng tồn tại đồng thời (*kiểu AND*), **Enum** định nghĩa một giá trị chỉ có thể là **một trong nhiều** biến thể khả dĩ (*kiểu OR - Algebraic Data Type*).

```rust
#[derive(Debug)]
enum Message {
    Quit,                       // Biến thể không chứa dữ liệu
    Move { x: i32, y: i32 },    // Biến thể chứa struct ẩn danh
    Write(String),              // Biến thể chứa một String
    ChangeColor(i32, i32, i32), // Biến thể chứa tuple 3 số nguyên
}
```

##### `Option<T>`: biểu diễn giá trị có thể vắng mặt

Tham chiếu Rust hợp lệ không được là null. Để mô hình hóa dữ liệu có thể vắng mặt, thư viện chuẩn cung cấp `Option<T>`. Con trỏ thô vẫn có thể mang giá trị null, nên không nên nói Rust hoàn toàn không có null. Định nghĩa dưới đây chỉ minh họa enum chuẩn đã có sẵn trong prelude; không cần khai báo lại trong dự án:

```rust
enum Option<T> {
    None,    // Không có giá trị
    Some(T), // Có giá trị kiểu T
}
```

Không thể dùng `Option<T>` trực tiếp như `T`; bạn phải chọn cách xử lý qua `match`, `if let`, `?` hoặc các phương thức phù hợp. `unwrap()` trên `None` vẫn gây `panic`. Kiểu này làm sự vắng mặt trở nên tường minh, chứ không tự loại bỏ mọi lỗi khi chạy.

---

<a id="chuong-08"></a>

### Chương 8. Khớp mẫu

**Pattern (Mẫu)** là cú pháp đặc biệt của Rust dùng để đối sánh và phân rã cấu trúc dữ liệu.

#### 8.1. Sáu vị trí xuất hiện của pattern và phân loại refutable / irrefutable

##### 1. Sáu vị trí pattern xuất hiện trong Rust

1. **Nhánh `match`:** `match value { PATTERN => EXPRESSION }`.
2. **Biểu thức `if let` và `let else`:** Xử lý gọn một mẫu cụ thể.
3. **Vòng lặp `while let`:** Lặp chừng nào mẫu còn khớp.
4. **Vòng lặp `for`:** `for (index, value) in v.iter().enumerate()`.
5. **Câu lệnh `let`:** `let (x, y, z) = (1, 2, 3);`.
6. **Tham số hàm:** `fn print_coordinates(&(x, y): &(i32, i32))`.

##### 2. Phân biệt irrefutable và refutable patterns

-  **Irrefutable (Không thể thất bại):** Mẫu luôn khớp với mọi giá trị có thể có của kiểu đó (ví dụ: `let x = 5;`, `let (a, b) = pair;`). Câu lệnh `let` thông thường (không có `else`), vòng lặp `for` và tham số hàm yêu cầu mẫu irrefutable.
-  **Refutable (Có thể thất bại):** Mẫu có thể không khớp với một số giá trị (ví dụ: `Some(x)` sẽ thất bại nếu giá trị là `None`). Dùng trong `if let`, `let else`, `while let` và các nhánh của `match`.

---

#### 8.2. Cấu trúc `match`, `if let` và `let else`

```rust
fn plus_one(x: Option<i32>) -> Option<i32> {
    match x {
        None => None,
        Some(i) => Some(i + 1),
    }
}

fn process_config(config_max: Option<u8>) {
    // 1. Dùng if let khi chỉ quan tâm đến 1 mẫu:
    if let Some(max) = config_max {
        println!("Giới hạn cấu hình tối đa: {max}");
    }

    // 2. Dùng let else để kiểm tra điều kiện tiên quyết và thoát sớm (Early Return):
    let Some(valid_max) = config_max else {
        println!("⚠️ Không có cấu hình, thoát hàm sớm!");
        return;
    };
    println!("Sử dụng trực tiếp valid_max ở scope ngoài: {valid_max}");
}
```

---

#### 8.3. Các cú pháp khớp mẫu thường dùng

```rust
struct Point {
    x: i32,
    y: i32,
}

enum Command {
    Execute { id: i32 },
}

fn main() {
    // 1. Khớp nhiều mẫu với `|` và khớp dải giá trị với `..=`:
    let x = 3;
    match x {
        1 | 2 => println!("Một hoặc hai"),
        3..=5 => println!("Từ ba đến năm"),
        _ => println!("Giá trị khác"),
    }

    // 2. Phân rã Struct và kiểm tra giá trị trường cụ thể:
    let p = Point { x: 0, y: 7 };
    match p {
        Point { x, y: 0 } => println!("Nằm trên trục hoành tại x = {x}"),
        Point { x: 0, y } => println!("Nằm trên trục tung tại y = {y}"),
        Point { x, y } => println!("Nằm tại tọa độ ({x}, {y})"),
    }

    // 3. Bỏ qua phần tử ở giữa bằng `..`:
    let numbers = (2, 4, 8, 16, 32);
    match numbers {
        (first, .., last) => println!("Số đầu: {first}, Số cuối: {last}"),
    }

    // 4. Điều kiện phụ Match Guards (thêm `if` vào sau mẫu):
    let num = Some(4);
    match num {
        Some(n) if n % 2 == 0 => println!("Số chẵn: {n}"),
        Some(n) => println!("Số lẻ: {n}"),
        None => (),
    }

    // 5. Toán tử ràng buộc `@` (vừa kiểm tra dải giá trị, vừa gán vào biến):
    let cmd = Command::Execute { id: 5 };
    match cmd {
        Command::Execute {
            id: id_val @ 3..=7,
        } => println!("✅ Tìm thấy id nằm trong dải ưu tiên: {id_val}"),
        Command::Execute { id } => println!("Id thông thường: {id}"),
    }
}
```

---

<a id="phan-v"></a>

## Phần V. Phương thức, generics và trait

---

<a id="chuong-09"></a>

### Chương 9. Phương thức, impl và thiết kế hướng đối tượng

#### 9.1. Định nghĩa phương thức (`&self`, `&mut self`, `self`) và hàm liên kết

Trong Rust, dữ liệu (`struct`/`enum`) và hành vi (`impl`) được tách bạch rõ ràng:

```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

impl Rectangle {
    // 1. Hàm liên kết (Associated Function - không có self, đóng vai trò Constructor):
    fn new(width: u32, height: u32) -> Self {
        Self { width, height }
    }

    fn square(size: u32) -> Self {
        Self { width: size, height: size }
    }

    // 2. Phương thức mượn bất biến (&self - chỉ đọc dữ liệu):
    fn area(&self) -> u32 {
        self.width * self.height
    }

    // 3. Phương thức mượn khả biến (&mut self - sửa đổi dữ liệu nội bộ):
    fn scale(&mut self, factor: u32) {
        self.width *= factor;
        self.height *= factor;
    }

    // 4. Phương thức kiểm tra:
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }
}

fn main() {
    let mut rect1 = Rectangle::new(30, 50);
    let sq = Rectangle::square(20);

    rect1.scale(2);
    println!("📐 Diện tích rect1 sau khi phóng đại: {}", rect1.area());
    println!("📦 rect1 chứa được sq? {}", rect1.can_hold(&sq));
}
```

---

#### 9.2. Rust dưới góc nhìn lập trình hướng đối tượng (OOP)

Rust hỗ trợ nhiều kỹ thuật thường dùng trong lập trình hướng đối tượng, với mô hình kiểu riêng:

- **Đóng gói (Encapsulation):** Sử dụng module và các mức hiển thị như `pub`, `pub(crate)`. Trường riêng tư có thể được truy cập trong module định nghĩa và các module con của nó; từ bên ngoài phạm vi đó, API công khai kiểm soát truy cập.
- **Tổ hợp thay vì Kế thừa (Composition over Inheritance):** Rust **không có kế thừa lớp (`extends`)** để tránh sự phụ thuộc chặt chẽ và bài toán đa kế thừa (*Diamond Problem*). Thay vào đó, Rust sử dụng **trait** để chia sẻ hành vi và nhúng các struct vào nhau để tái sử dụng cấu trúc.
- **Đa hình (Polymorphism):** Thực hiện thông qua **Generics** (đa hình tĩnh) và **trait Objects `dyn Trait`** (đa hình động).

---

#### 9.3. Mẫu thiết kế trạng thái chuẩn rustacean: typestate pattern

Trong OOP truyền thống, để biểu diễn một đối tượng thay đổi hành vi theo trạng thái (như bài viết chuyển từ *Nháp* sang *Đã xuất bản*), ta thường dùng *State Pattern* với các biến cờ hoặc nhánh kiểm tra lúc chạy.

Trong Rust, các kỹ sư sử dụng **Typestate Pattern**: **Biến mỗi trạng thái thành một kiểu struct riêng biệt!** Nhờ cơ chế phương thức tiêu thụ quyền sở hữu (`self`), khi chuyển trạng thái, giá trị cũ được tiêu thụ và dữ liệu cần giữ được chuyển sang giá trị có kiểu mới, không nhất thiết được giải phóng rồi cấp phát lại. Những hành vi không có trong API của kiểu trạng thái hiện tại sẽ bị từ chối khi biên dịch. Thiết kế này không tự kiểm tra quyền phê duyệt của người dùng; đó là quy tắc nghiệp vụ bổ sung.

```rust
// Trạng thái 1: Bản nháp (Chưa hề có phương thức đọc nội dung content!)
#[derive(Default)]
pub struct DraftPost {
    content: String,
}

// Trạng thái 2: Đang chờ duyệt
pub struct PendingReviewPost {
    content: String,
}

// Trạng thái 3: Đã xuất bản chính thức (Mới có phương thức .content())
pub struct PublishedPost {
    content: String,
}

impl DraftPost {
    pub fn new() -> DraftPost {
        DraftPost { content: String::new() }
    }

    pub fn add_text(&mut self, text: &str) {
        self.content.push_str(text);
    }

    // Tiêu thụ `self` (DraftPost biến mất) và trả về PendingReviewPost:
    pub fn request_review(self) -> PendingReviewPost {
        PendingReviewPost { content: self.content }
    }
}

impl PendingReviewPost {
    // Tiêu thụ `self` (PendingReviewPost biến mất) và trả về PublishedPost:
    pub fn approve(self) -> PublishedPost {
        PublishedPost { content: self.content }
    }
}

impl PublishedPost {
    pub fn content(&self) -> &str {
        &self.content
    }
}

fn main() {
    let mut post = DraftPost::new();
    post.add_text("Học Rust chuyên sâu với Typestate Pattern!");

    // post.content(); // ❌ LỖI BIÊN DỊCH: DraftPost không có hàm content()!

    let post = post.request_review();
    // post.content(); // ❌ LỖI BIÊN DỊCH: PendingReviewPost vẫn chưa được phép đọc content()!

    let post = post.approve();
    println!("📰 Bài viết đã xuất bản: {}", post.content()); // Hợp lệ: phương thức có trên PublishedPost.
}
```

---

<a id="chuong-10"></a>

### Chương 10. Generics và trait

#### 10.1. Kiểu chung (generics) và const generics

Generics cho phép viết hàm, struct, enum và phương thức hoạt động trên nhiều kiểu dữ liệu mà không phải viết lặp lại mã:

```rust
// 1. Generic Function:
fn largest<T: Ord>(list: &[T]) -> Option<&T> {
    let mut largest = list.first()?; // Trả về None nếu danh sách rỗng.
    for item in list {
        if item > largest {
            largest = item;
        }
    }
    Some(largest)
}

// 2. Generic Struct với nhiều tham số kiểu:
struct Point<T, U> {
    x: T,
    y: U,
}

impl<T, U> Point<T, U> {
    fn mixup<V, W>(self, other: Point<V, W>) -> Point<T, W> {
        Point {
            x: self.x,
            y: other.y,
        }
    }
}

// 3. Const Generics (Generic trên giá trị hằng số kích thước mảng):
fn display_array<T: std::fmt::Debug, const N: usize>(arr: [T; N]) {
    println!("Mảng {N} phần tử: {arr:?}");
}

fn main() {
    let numbers = vec![34, 50, 25, 100, 65];
    println!("Số lớn nhất là: {:?}", largest(&numbers));
    assert_eq!(largest::<i32>(&[]), None);

    let p1 = Point { x: 5, y: 10.4 };
    let p2 = Point { x: "Hello", y: 'c' };
    let p3 = p1.mixup(p2);
    println!("p3.x = {}, p3.y = {}", p3.x, p3.y);

    display_array([10, 20, 30]);
}
```

##### Bản chất hiệu năng: cơ chế đơn hình hóa (monomorphization)

`largest` dùng `Ord` để yêu cầu thứ tự toàn phần và trả `None` khi đầu vào rỗng. Nếu dùng `PartialOrd` cho số thực, cần quy định rõ cách xử lý giá trị không so sánh được như `NaN`.

Rust thường đơn hình hóa mã generic theo những kiểu cụ thể được sử dụng, nhờ đó tránh chi phí phân phối động cho lời gọi trait và mở cơ hội inline. Đánh đổi có thể là thời gian biên dịch và kích thước mã; thuật toán, cấp phát và việc sao chép bên trong vẫn có chi phí.

---

#### 10.2. Định nghĩa traits, trait bounds và blanket implementations

```rust
pub trait Summary {
    fn summarize_author(&self) -> String;

    // Phương thức cài đặt mặc định (Default Implementation):
    fn summarize(&self) -> String {
        format!("(Đọc thêm từ {}...)", self.summarize_author())
    }
}

#[derive(Debug)]
pub struct Article {
    pub author: String,
    pub headline: String,
}

impl Summary for Article {
    fn summarize_author(&self) -> String {
        format!("@{}", self.author)
    }
}

// Ràng buộc Trait Bound với mệnh đề where rõ ràng:
pub fn notify_multiple<T, U>(t: &T, u: &U)
where
    T: Summary + std::fmt::Debug,
    U: std::fmt::Display,
{
    println!("Thông báo: {} — {u}; chi tiết: {t:?}", t.summarize());
}
```

##### Blanket implementations (triển khai bao phủ)

Rust cho phép cài đặt một trait đồng loạt cho mọi kiểu dữ liệu nếu kiểu đó thỏa mãn một trait khác. Ví dụ điển hình trong thư viện chuẩn:
```rust
// Mọi kiểu T có cài đặt Display đều tự động có phương thức .to_string() của trait ToString!
// Đây là chú thích về triển khai sẵn có, không cần viết lại:
// impl<T: std::fmt::Display + ?Sized> ToString for T { /* do std cung cấp */ }
```

---

#### 10.3. Đa hình động với trait objects (`dyn Trait`)

Khi bạn cần một tập hợp (`Vec`) chứa nhiều đối tượng thuộc các kiểu dữ liệu khác nhau nhưng cùng thực hiện một hành vi chung:

```rust
pub trait Draw {
    fn draw(&self);
}

pub struct Button {
    pub label: String,
}

impl Draw for Button {
    fn draw(&self) {
        println!("🔘 Vẽ nút bấm: [{}]", self.label);
    }
}

pub struct SelectBox {
    pub options: Vec<String>,
}

impl Draw for SelectBox {
    fn draw(&self) {
        println!("📋 Vẽ hộp chọn gồm {} mục", self.options.len());
    }
}

pub struct Screen {
    // Vector chứa các Trait Objects thông qua con trỏ Box<dyn Draw>:
    pub components: Vec<Box<dyn Draw>>,
}

impl Screen {
    pub fn run(&self) {
        for component in &self.components {
            component.draw(); // Đa hình động qua bảng phương thức ảo (vtable) tại runtime!
        }
    }
}
```

---

Có thể đặt đoạn gọi sau vào `main` cùng các định nghĩa trên:

```rust
let screen = Screen {
    components: vec![
        Box::new(Button { label: String::from("Lưu") }),
        Box::new(SelectBox { options: vec![String::from("Tiếng Việt")] }),
    ],
};
screen.run();
```

Trait dùng qua `dyn` phải thỏa điều kiện **dyn compatibility** (trước đây gọi là object safety). Ví dụ, phương thức được gọi qua trait object không có tham số kiểu generic riêng và không trả `Self`. Phương thức chỉ dành cho kiểu cụ thể có thể ràng buộc `where Self: Sized`. Xem [Rust Reference: dyn compatibility](https://doc.rust-lang.org/reference/items/traits.html#dyn-compatibility).

`impl Trait` ở tham số là cách viết gọn một ràng buộc generic. Ở kiểu trả về, nó che một kiểu cụ thể do hàm chọn; các nhánh trả về thông thường vẫn phải có cùng kiểu ẩn, không thể tùy ý thay thế cho `Box<dyn Trait>`.

#### 10.4. Các tính năng trait nâng cao (advanced traits)

##### 1. Kiểu liên kết (associated types)

Kiểu liên kết (`type Item;`) được xác định cho một triển khai trait cụ thể. Ví dụ rút gọn sau minh họa `Iterator` trong thư viện chuẩn, không phải định nghĩa cần chép đè lên trait chuẩn:
```rust
pub trait Iterator {
    type Item; // Associated Type
    fn next(&mut self) -> Option<Self::Item>;
}
```

##### 2. Nạp chồng toán tử (operator overloading) với `std::ops`

Cài đặt các trait trong `std::ops` (như `Add`, `Sub`, `Mul`, `Index`) để nạp chồng toán tử cho struct của bạn:

```rust
use std::ops::Add;

#[derive(Debug, Copy, Clone, PartialEq)]
struct Point {
    x: i32,
    y: i32,
}

impl Add for Point {
    type Output = Point;

    fn add(self, other: Point) -> Point {
        Point {
            x: self.x + other.x,
            y: self.y + other.y,
        }
    }
}

fn main() {
    let p1 = Point { x: 1, y: 2 };
    let p2 = Point { x: 3, y: 4 };
    assert_eq!(p1 + p2, Point { x: 4, y: 6 });
}
```

##### 3. Cú pháp định danh đầy đủ (fully qualified syntax) và supertraits

- **Supertrait:** Yêu cầu một kiểu muốn cài đặt trait `A` thì bắt buộc phải cài đặt trait `B` trước (`trait OutlinePrint: std::fmt::Display`).
- **Fully Qualified Syntax:** Khi hai trait có phương thức trùng tên nhau trên cùng một kiểu, dùng cú pháp `<Type as Trait>::function(...)` để chỉ định rõ hàm muốn gọi.

##### 4. Mẫu hình newtype vượt qua quy tắc cô nhi (orphan rule)

Quy tắc **Orphan Rule** ngăn không cho bạn cài đặt `fmt::Display` (thuộc crate `std`) trực tiếp lên `Vec<String>` (cũng thuộc crate `std`). Để vượt qua một cách hợp lệ và không tốn chi phí runtime, ta bọc `Vec<String>` vào một Tuple struct cục bộ:

```rust
use std::fmt;

struct Wrapper(Vec<String>);

impl fmt::Display for Wrapper {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "[{}]", self.0.join(", "))
    }
}

fn main() {
    let w = Wrapper(vec![String::from("Xin chào"), String::from("Rustacean")]);
    println!("w = {w}");
}
```

> **Thử thách tư duy rustacean (phần v)**
> **Câu hỏi:** Khi nào bạn nên dùng **Đa hình tĩnh (`impl Trait` / Generics `<T: Trait>`)** và khi nào nên dùng **Đa hình động (`Box<dyn Trait>`)**?
> **Giải đáp:**
> - Dùng **generics** khi kiểu cụ thể đã được xác định ở lúc biên dịch và cần giữ thông tin kiểu cho tối ưu hóa. Không có một tỷ lệ áp dụng chung cho mọi dự án.
> - Dùng **trait object (`Box<dyn Trait>` hoặc `&dyn Trait`)** khi cần lưu trữ một tập hợp hỗn hợp nhiều kiểu dữ liệu khác nhau trong cùng một cấu trúc tại runtime (ví dụ `Vec<Box<dyn Draw>>`) hoặc khi muốn giảm dung lượng tệp nhị phân đánh đổi lấy một bước nhảy con trỏ hàm qua bảng `vtable`.

---

<a id="phan-vi"></a>

## Phần VI. Tập hợp dữ liệu, chuyển đổi kiểu và xử lý lỗi

---

<a id="chuong-11"></a>

### Chương 11. Các cấu trúc dữ liệu tập hợp

Các tập hợp chuẩn quản lý vùng lưu trữ có thể thay đổi khi chạy. `Vec` thuộc `std::vec` và có sẵn trong prelude; các kiểu như `HashMap`, `BTreeMap` thuộc `std::collections`. Xóa phần tử thường không tự giảm dung lượng đã cấp phát; khi cần có thể cân nhắc các phương thức thu gọn phù hợp.

#### 11.1. So sánh các collection chuẩn

Bảng dưới dùng $n$ là số phần tử. “Khấu hao” tính chi phí trung bình trên một chuỗi thao tác, còn “kỳ vọng” gắn với phân tích xác suất; hai khái niệm này không đồng nghĩa.

| Cấu trúc | Truy cập hoặc tìm kiếm | Thêm, xóa tiêu biểu | Khi sử dụng |
| :--- | :--- | :--- | :--- |
| `Vec<T>` | O(1) theo chỉ mục | `push`: O(1) khấu hao; `pop`: O(1); chèn/xóa giữa: O(n) | Danh sách liên tiếp, phù hợp nhiều bài toán |
| `VecDeque<T>` | O(1) theo chỉ mục | Thêm ở hai đầu: O(1) khấu hao; xóa ở hai đầu: O(1) | Hàng đợi hoặc hàng đợi hai đầu |
| `LinkedList<T>` | O(n) để tìm theo vị trí | Thêm/xóa ở hai đầu và `append`: O(1); `split_off` phải tìm điểm tách | Khi thực sự cần đặc tính của danh sách liên kết; thường kém lợi thế bộ nhớ đệm hơn `Vec` |
| `HashMap<K, V>` | O(1) kỳ vọng | Thêm: O(1) kỳ vọng, khấu hao; xóa: O(1) kỳ vọng | Tra cứu theo khóa, không có thứ tự duyệt được bảo đảm |
| `BTreeMap<K, V>` | O(log n) | Thêm/xóa: O(log n) | Khóa có thứ tự, truy vấn theo khoảng |
| `HashSet<T>` | O(1) kỳ vọng | Tương tự `HashMap` | Tập hợp không trùng lặp, không yêu cầu thứ tự |
| `BTreeSet<T>` | O(log n) | Thêm/xóa: O(log n) | Tập hợp không trùng lặp có thứ tự |
| `BinaryHeap<T>` | `peek`: O(1); tìm giá trị bất kỳ: O(n) | `pop`: O(log n); `push`: O(log n) trường hợp xấu nếu không tính cấp phát lại, O(1) kỳ vọng theo tài liệu chuẩn | Hàng đợi ưu tiên lấy phần tử lớn nhất trước |

Việc cấp phát lại có thể khiến một lần chèn riêng lẻ tốn O(n). Chi phí băm hoặc so sánh khóa cũng cần xét khi khóa lớn. Xem [tài liệu collections](https://doc.rust-lang.org/std/collections/index.html) và [BinaryHeap](https://doc.rust-lang.org/std/collections/struct.BinaryHeap.html).

---

#### 11.2. Vector co giãn (`Vec<T>`)

```rust
fn main() {
    // Khởi tạo bằng Vec::new(), Vec::with_capacity(n), hoặc macro vec![]:
    let mut v = vec![10, 20, 30];
    v.push(40);

    // Cách 1: Truy xuất trực tiếp bằng chỉ mục (sẽ panic nếu vượt biên):
    let second: &i32 = &v[1];
    println!("Phần tử thứ hai: {second}");

    // Cách 2: Truy xuất an toàn bằng .get() trả về Option<&T>:
    match v.get(99) {
        Some(val) => println!("Giá trị: {val}"),
        None => println!("⚠️ Chỉ mục không tồn tại, không bị crash!"),
    }
}
```

##### Tại sao borrow checker cấm `v.push()` khi đang giữ tham chiếu phần tử `&v[0]`?

```rust
let mut v = vec![1, 2, 3, 4, 5];
let first = &v[0]; // Mượn bất biến phần tử đầu tiên
// v.push(6);      // ❌ LỖI BIÊN DỊCH!
println!("Phần tử đầu: {first}");
```
*Giải thích bản chất bộ nhớ:* Khi gọi `v.push(6)`, nếu vùng nhớ hiện tại trên heap đã đầy (`len == capacity`), vector có thể cấp phát lại và chuyển phần tử sang địa chỉ khác, khiến các tham chiếu cũ không còn hợp lệ. Khi đó, con trỏ `first` sẽ trỏ vào vùng nhớ cũ đã bị hủy (*dangling pointer*)! Borrow checker ngăn phép mượn độc quyền của `push` chồng lấn với tham chiếu còn được dùng, kể cả khi bạn biết vector hiện còn dung lượng.

##### Lưu trữ nhiều kiểu dữ liệu khác nhau trong vector qua enum

```rust
#[derive(Debug)]
enum SpreadsheetCell {
    Int(i32),
    Float(f64),
    Text(String),
}

fn main() {
    let row = vec![
        SpreadsheetCell::Int(3),
        SpreadsheetCell::Text(String::from("Doanh thu")),
        SpreadsheetCell::Float(105.75),
    ];
    println!("Dòng bảng tính: {row:?}");
}
```

---

#### 11.3. Bảng băm (`HashMap<K, V>`) và entry API

`HashMap<K, V>` ánh xạ khóa `K` sang giá trị `V` với thời gian tra cứu trung bình $O(1)$:

```rust
use std::collections::HashMap;

fn main() {
    let mut scores = HashMap::new();
    scores.insert(String::from("Blue"), 10);

    // Entry API: Chỉ chèn nếu khóa chưa tồn tại
    scores.entry(String::from("Yellow")).or_insert(50);
    scores.entry(String::from("Blue")).or_insert(50); // Giữ nguyên 10 vì Blue đã có!

    // Bài toán kinh điển: Đếm tần suất từ trong văn bản
    let text = "hello world wonderful world";
    let mut word_count = HashMap::new();

    for word in text.split_whitespace() {
        let count = word_count.entry(word).or_insert(0);
        *count += 1; // Giải tham chiếu &mut V để tăng bộ đếm
    }
    println!("Thống kê từ: {word_count:?}");
}
```

---

#### 11.4. Thực chiến với `VecDeque`, `BTreeMap`, `HashSet` và `BinaryHeap`

```rust
use std::collections::{BTreeMap, BinaryHeap, HashSet, VecDeque};

fn main() {
    // 1. VecDeque: Thêm ở hai đầu có chi phí O(1) khấu hao; xóa có chi phí O(1).
    let mut queue = VecDeque::new();
    queue.push_back("Task 2");
    queue.push_front("Task 1 (Khẩn cấp)");
    println!("Hàng đợi VecDeque: {queue:?}");

    // 2. BTreeMap: Bản đồ tự động sắp xếp khóa và truy vấn theo khoảng (Range query)
    let mut timeline = BTreeMap::new();
    timeline.insert(2025, "Rust 1.85 phát hành Edition 2024");
    timeline.insert(2015, "Rust 1.0 Stable");
    timeline.insert(2021, "Rust Edition 2021");
    for (year, event) in timeline.range(2018..=2025) {
        println!("📅 Năm {year}: {event}");
    }

    // 3. HashSet: Phép toán tập hợp (Giao, Hợp, Hiệu)
    let backend: HashSet<&str> = ["Rust", "Go", "Python"].into_iter().collect();
    let systems: HashSet<&str> = ["Rust", "C", "C++"].into_iter().collect();
    let both: Vec<&&str> = backend.intersection(&systems).collect();
    println!("Ngôn ngữ vừa làm Backend vừa lập trình Hệ thống: {both:?}");

    // 4. BinaryHeap: Hàng đợi ưu tiên (Luôn lấy ra phần tử lớn nhất trước - Max-Heap)
    let mut priority_jobs = BinaryHeap::from([10, 50, 20, 99, 35]);
    if let Some(top_priority) = priority_jobs.pop() {
        println!("🔥 Xử lý công việc có độ ưu tiên cao nhất: {top_priority}"); // 99
    }
}
```

---

<a id="chuong-12"></a>

### Chương 12. Chuyển đổi kiểu dữ liệu

Rust không bao giờ tự động ép kiểu ngầm định giữa các kiểu dữ liệu số để tránh mất mát độ chính xác ngoài ý muốn.

#### 12.1. Ép kiểu số và nguy cơ mất dữ liệu

`as` là phép chuyển kiểu tường minh, không đồng nghĩa với chuyển đổi không mất dữ liệu. Ép số nguyên sang kiểu hẹp hơn có thể mất bit; ép số thực sang số nguyên loại phần thập phân và có quy tắc bão hòa ở biên. Khi cần phát hiện giá trị ngoài miền, ưu tiên `TryFrom`.

```rust
fn main() {
    let a: i32 = 10;
    let b: f64 = f64::from(a); // Chuyển đổi này không mất thông tin.
    assert_eq!(b, 10.0);

    assert_eq!(300_u16 as u8, 44); // Chỉ giữ 8 bit thấp.
    assert!(u8::try_from(300_u16).is_err());
    assert_eq!(3.9_f64 as i32, 3); // Cắt phần thập phân về phía 0.
}
```

Để chuyển văn bản thành số, dùng `parse::<T>()`, không dùng `as`. Ví dụ: `let n: Result<u32, _> = "42".parse();`.

---

#### 12.2. Chuyển đổi không thất bại (`From` / `Into`) và có thể thất bại (`TryFrom` / `TryInto`)

- **`From<T>` và `Into<U>`:** Dành cho các phép chuyển đổi luôn thành công. **Quy tắc vàng:** Hãy luôn ưu tiên cài đặt trait `From`, vì khi có `From`, thư viện chuẩn sẽ tự động cung cấp `Into` cho bạn thông qua Blanket Implementation!
- **`TryFrom<T>` và `TryInto<U>`:** Dành cho các phép chuyển đổi có nguy cơ thất bại, trả về `Result<Self, Self::Error>`.

```rust
#[derive(Debug, PartialEq)]
struct EvenNumber(i32);

impl TryFrom<i32> for EvenNumber {
    type Error = &'static str;

    fn try_from(value: i32) -> Result<Self, Self::Error> {
        if value % 2 == 0 {
            Ok(EvenNumber(value))
        } else {
            Err("Số truyền vào không phải là số chẵn!")
        }
    }
}

fn main() {
    assert_eq!(EvenNumber::try_from(8), Ok(EvenNumber(8)));
    assert!(EvenNumber::try_from(5).is_err());
}
```

---

<a id="chuong-13"></a>

### Chương 13. Xử lý lỗi

Rust phân biệt rạch ròi hai nhóm lỗi:

1.  **Lỗi không thể phục hồi (Unrecoverable Errors):** Do bug lập trình (truy cập mảng vượt biên, chia cho 0). Xử lý bằng `panic!`.
2.  **Lỗi có thể phục hồi (Recoverable Errors):** Sự cố ngoại cảnh dự kiến trước (không tìm thấy file, mất kết nối mạng). Xử lý bằng `Result<T, E>`.

#### 13.1. `panic!` và truy vết ngăn xếp (`RUST_BACKTRACE=1`)

Trên nhiều target dùng `std`, `panic!` mặc định tháo ngăn xếp (*unwinding*) của luồng hiện tại và hủy các giá trị còn sống. Với `panic = "abort"`, tiến trình kết thúc ngay và không chạy các destructor như khi unwinding. Để yêu cầu backtrace trong Bash:

```bash
RUST_BACKTRACE=1 cargo run
```

---

Trong PowerShell:

```powershell
$env:RUST_BACKTRACE = "1"
cargo run
```

Mức độ chi tiết của backtrace phụ thuộc cấu hình biên dịch và ký hiệu gỡ lỗi; `RUST_BACKTRACE=full` yêu cầu bản đầy đủ hơn.

#### 13.2. `Result<T, E>` và toán tử lan truyền lỗi `?`

```rust
use std::fs::File;
use std::io::{self, Read};

fn read_username_from_file() -> Result<String, io::Error> {
    let mut username = String::new();
    // Toán tử ? sẽ tự động giải nén giá trị bên trong Ok,
    // hoặc return sớm Err(e) (kèm chuyển đổi kiểu lỗi qua From::from) nếu gặp lỗi:
    File::open("username.txt")?.read_to_string(&mut username)?;
    Ok(username)
}
```

---

`?` cũng dùng được trong hàm trả `Option<T>`: gặp `None` thì trả sớm `None`. Nó không tự chuyển `Option` thành `Result`; dùng `ok_or` hoặc `ok_or_else` khi cần tạo lỗi. `unwrap()` và `expect()` đều có thể gây `panic`; thông báo của `expect()` nên giải thích vì sao giá trị thành công được kỳ vọng.

#### 13.3. Khi nào dùng `panic!` và `Result` và xác thực bằng kiểu tùy chỉnh

| Tình huống | Lựa chọn khuyến nghị | Lý do |
| :--- | :--- | :--- |
|  Viết mã mẫu, prototype, bài kiểm thử (`#[test]`) | `unwrap()`, `expect()`, `panic!` | Ngắn gọn, làm nổi bật logic chính hoặc báo test thất bại ngay. |
| Viết thư viện dùng chung | Trả `Result<T, E>` cho lỗi dự kiến có thể phục hồi | Để bên gọi chọn cách xử lý. API vẫn có thể có điều kiện gây `panic`, nhưng cần tài liệu hóa rõ. |
|  Vi phạm điều kiện bất biến nội bộ (Contract violation) | `panic!` | Bất biến của API không còn được bảo đảm; quyết định dừng cần dựa trên hợp đồng đã mô tả. |
|  Xác thực dữ liệu đầu vào của người dùng | Tạo Custom Type + trả `Result` | Đảm bảo mọi hàm nhận kiểu đó luôn nhận dữ liệu đã được kiểm chứng. |

##### Mẫu thiết kế tạo kiểu tùy chỉnh để xác thực (validation custom type)

Thay vì kiểm tra số dự đoán nằm trong khoảng $1 \dots 100$ ở khắp mọi hàm, ta đóng gói nó thành một kiểu `Guess` có trường `value` là `private`:

```rust
pub struct Guess {
    value: i32, // Chỉ module định nghĩa và các module con truy cập trực tiếp được.
}

impl Guess {
    pub fn new(value: i32) -> Result<Guess, String> {
        if !(1..=100).contains(&value) {
            return Err(format!("Số dự đoán phải từ 1 đến 100, nhận được: {value}"));
        }
        Ok(Guess { value })
    }

    pub fn value(&self) -> i32 {
        self.value // Getter chỉ đọc
    }
}
```

---

<a id="phan-vii"></a>

## Phần VII. Tổ chức dự án, kiểm thử và minigrep

---

<a id="chuong-14"></a>

### Chương 14. Tổ chức dự án: package, crate, module và workspace

#### 14.1. Workspace, package, crate và module

| Cấp tổ chức | Vai trò |
| :--- | :--- |
| Workspace | Nhóm các package; thường dùng chung `Cargo.lock` và thư mục `target` |
| Package | Được mô tả bởi `Cargo.toml`; có thể chứa nhiều target |
| Crate | Đơn vị biên dịch và cây module; có crate thư viện hoặc thực thi |
| Module | Nhóm các mục và kiểm soát mức hiển thị bên trong một crate |

Theo cách bố trí Cargo thông thường, `src/lib.rs` là gốc crate thư viện, `src/main.rs` là gốc crate thực thi chính, còn `src/bin/*.rs` tạo các binary khác. Một package có tối đa một target thư viện và có thể có nhiều target thực thi. Tệp không tự trở thành module chỉ vì xuất hiện trong `src`; cần khai báo `mod` thích hợp.

Ví dụ `Cargo.toml` của một **virtual workspace** (không có mục `[package]` ở gốc):

```toml
[workspace]
members = ["app", "utils"]
resolver = "3"
```

Mỗi thư mục thành viên cần `Cargo.toml` riêng. Trong `app/Cargo.toml`, dùng `utils = { path = "../utils" }` ở `[dependencies]` để phụ thuộc vào thư viện nội bộ. Resolver phiên bản 3 phù hợp với dự án Edition 2024; virtual workspace cần chỉ định rõ vì không có package gốc để suy ra edition.

---

#### 14.2. Quy tắc riêng tư, đường dẫn (`use`, `pub use`) và tách nhiều file

##### 1. Quy tắc riêng tư (privacy rules)

- Đa số mục mặc định riêng tư trong module định nghĩa và các module con; mục của trait và biến thể của enum có quy tắc riêng.
- Module con có thể truy cập mọi mục trong module cha, nhưng module cha chỉ truy cập được các mục có từ khóa `pub` của module con.
- Với `pub struct`: Các trường bên trong vẫn là `private` trừ khi từng trường được gắn `pub`.
- Với `pub enum`: **Toàn bộ các biến thể bên trong tự động là `pub`**.

##### 2. Tách module thành nhiều tệp

Khi dự án lớn lên, ta tách các module ra thành các tệp riêng biệt theo cấu trúc chuẩn:

| Tệp | Nội dung tối thiểu |
| :--- | :--- |
| `src/lib.rs` | `pub mod front_of_house;` |
| `src/front_of_house.rs` | `pub mod hosting;` |
| `src/front_of_house/hosting.rs` | `pub fn add_to_waitlist() {}` |

---

Cách bố trí dùng `front_of_house/mod.rs` vẫn hợp lệ; không đồng thời dùng cả nó và `front_of_house.rs` cho cùng module.

Trong `src/lib.rs`, có thể viết:

```rust
pub mod front_of_house;

// Tái xuất một API từ đường dẫn ngắn hơn.
pub use crate::front_of_house::hosting::add_to_waitlist;
```

`use` đưa tên vào phạm vi hiện tại, không sao chép mã hay tự công khai API. `pub use` vừa đưa tên vào phạm vi vừa tái xuất nó. Dùng `crate::` từ gốc crate, `self::` từ module hiện tại và `super::` từ module cha; `pub(crate)` chỉ công khai trong cùng crate.

#### 14.3. Tùy biến cấu hình tối ưu hóa với release profiles

Trong `Cargo.toml`, bạn có thể kiểm soát chi tiết cách trình biên dịch tối ưu hóa mã máy:

```toml
[profile.dev]
opt-level = 0       # Tắt tối ưu hóa để biên dịch nhanh nhất khi đang phát triển

[profile.release]
opt-level = 3       # Mức tối ưu hóa tốc độ cao; cần đo trên chương trình thực tế
lto = true          # Bật Link-Time Optimization (tối ưu hóa xuyên suốt toàn bộ các crate)
codegen-units = 1   # Một đơn vị sinh mã mỗi crate; có thể tăng thời gian biên dịch
panic = "abort"     # Dừng ngay khi panic thay vì unwinding, giúp giảm kích thước file nhị phân
strip = true        # Loại bỏ ký hiệu, có thể làm khó phân tích lỗi hơn
```

---

Cấu hình trên là một lựa chọn để đo đạc, không phải thiết lập tốt nhất cho mọi dự án. `panic = "abort"` bỏ qua unwinding và các hàm hủy khi có panic; cân nhắc kỹ nếu cần dọn tài nguyên. Trong workspace, cấu hình profile đặt ở manifest gốc.

<a id="chuong-15"></a>

### Chương 15. Kiểm thử tự động và tài liệu hóa

#### 15.1. Giải phẫu hàm kiểm thử và các cờ điều khiển `cargo test`

```rust
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn it_works() {
        assert_eq!(add(2, 2), 4);
    }

    #[test]
    #[ignore] // Đánh dấu bỏ qua bài kiểm thử tốn nhiều thời gian
    fn expensive_test() {
        assert_ne!(add(10, 20), 0);
    }
}
```

##### Các lệnh điều khiển `cargo test` chuyên sâu

```bash
# 1. Chạy toàn bộ bài kiểm thử song song trên nhiều luồng:
cargo test

# 2. Chạy các bài kiểm thử tuần tự trên 1 luồng duy nhất (khi dùng chung file/database):
cargo test -- --test-threads=1

# 3. Hiển thị nội dung println! ra màn hình ngay cả khi bài test PASS:
cargo test -- --show-output

# 4. Chỉ chạy các bài test có tên chứa chuỗi "it_works":
cargo test it_works

# 5. Chỉ chạy riêng các bài test đã được đánh dấu #[ignore]:
cargo test -- --ignored
```

---

#### 15.2. Phân biệt unit tests và integration tests và doctests

- **Unit Tests:** Đặt ngay trong `src/` cùng file với mã nguồn bên trong module `#[cfg(test)]`. Có đặc quyền kiểm thử được cả các hàm `private` nội bộ.
- **Integration Tests:** Đặt trong thư mục độc lập `tests/` ở gốc dự án. Mỗi tệp trong `tests/*.rs` được biên dịch như một crate riêng biệt và chỉ gọi được các API `pub` của thư viện.
- **Documentation Tests (Doctests):** Các khối mã ví dụ viết trong chú thích tài liệu `///` sẽ được `cargo test` tự động biên dịch và chạy kiểm thử, giúp phát hiện ví dụ lỗi thời. Các khối bị bỏ qua hoặc chỉ kiểm tra biên dịch không chứng minh toàn bộ tài liệu chính xác.

| Vị trí | Loại nội dung |
| :--- | :--- |
| `src/lib.rs`, trong `#[cfg(test)] mod tests` | Kiểm thử đơn vị |
| Chú thích `///` của API thư viện | Tài liệu và doctest |
| `tests/integration_test.rs` | Kiểm thử tích hợp dùng API công khai |

---

Ví dụ doctest cho package có tên `arithmetic_demo`, đặt trong `src/lib.rs`:

````rust
/// Cộng hai số nguyên trong miền không bị tràn.
///
/// ```
/// assert_eq!(arithmetic_demo::add(2, 3), 5);
/// ```
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
````

Chạy `cargo test --doc` để kiểm tra ví dụ tài liệu và `cargo doc --open` để tạo, mở tài liệu. Đây là một định nghĩa `add` độc lập, thay cho định nghĩa mẫu ở trên nếu đặt trong cùng tệp. Trong kiểm thử, `#[should_panic(expected = "...")]` diễn tả panic có chủ đích; hàm test cũng có thể trả `Result<(), E>` để dùng `?`.

<a id="chuong-16"></a>

### Chương 16. Dự án 2 — Công cụ dòng lệnh minigrep

`minigrep` tìm các dòng chứa từ khóa trong một tệp UTF-8. Dự án tách xử lý tham số và tìm kiếm vào thư viện, giữ `main` ngắn gọn, dùng kiểm thử để mô tả hành vi và báo lỗi qua stderr.

#### 16.1. Thiết lập dự án

```bash
cargo new minigrep --edition 2024
cd minigrep
```

Giữ `name = "minigrep"` trong `Cargo.toml`, vì `main.rs` bên dưới dùng tên crate đó. Dự án chỉ cần thư viện chuẩn; tạo thêm `src/lib.rs`.

#### 16.2. Thư viện nghiệp vụ: `src/lib.rs`

```rust
use std::error::Error;
use std::fs;
use std::io::{self, Write};

#[derive(Debug)]
pub struct Config {
    pub query: String,
    pub file_path: String,
    pub ignore_case: bool,
}

impl Config {
    pub fn build(
        mut args: impl Iterator<Item = String>,
        ignore_case: bool,
    ) -> Result<Self, &'static str> {
        args.next(); // Bỏ tên chương trình.
        let query = args.next().ok_or("Thiếu từ khóa tìm kiếm")?;
        let file_path = args.next().ok_or("Thiếu đường dẫn tệp")?;
        if args.next().is_some() {
            return Err("Thừa tham số; cú pháp: minigrep <query> <file_path>");
        }
        Ok(Self { query, file_path, ignore_case })
    }
}

pub fn run(config: Config) -> Result<(), Box<dyn Error>> {
    let contents = fs::read_to_string(&config.file_path)?;
    let results = if config.ignore_case {
        search_case_insensitive(&config.query, &contents)
    } else {
        search(&config.query, &contents)
    };

    let stdout = io::stdout();
    let mut output = stdout.lock();
    for line in results {
        writeln!(output, "{line}")?;
    }
    Ok(())
}

pub fn search<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    contents.lines().filter(|line| line.contains(query)).collect()
}

pub fn search_case_insensitive<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let query_lower = query.to_lowercase();
    contents
        .lines()
        .filter(|line| line.to_lowercase().contains(query_lower.as_str()))
        .collect()
}

#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn case_sensitive() {
        let contents = "Rust is productive.\nDuct tape.\nA quiet day.";
        assert_eq!(search("duct", contents), vec!["Rust is productive."]);
    }

    #[test]
    fn case_insensitive() {
        let contents = "Rust is productive.\nTrust the tests.\nA quiet day.";
        assert_eq!(
            search_case_insensitive("rUsT", contents),
            vec!["Rust is productive.", "Trust the tests."]
        );
    }

    #[test]
    fn no_match_and_empty_input() {
        assert!(search("missing", "Rust").is_empty());
        assert!(search("Rust", "").is_empty());
    }

    #[test]
    fn empty_query_matches_every_line() {
        assert_eq!(search("", "one\ntwo"), vec!["one", "two"]);
    }

    #[test]
    fn parses_config_without_changing_environment() {
        let args = ["minigrep", "Rust", "sample.txt"].into_iter().map(String::from);
        let config = Config::build(args, true).unwrap();
        assert_eq!(config.query, "Rust");
        assert_eq!(config.file_path, "sample.txt");
        assert!(config.ignore_case);
    }

    #[test]
    fn rejects_missing_or_extra_arguments() {
        for args in [
            vec!["minigrep"],
            vec!["minigrep", "Rust"],
            vec!["minigrep", "Rust", "sample.txt", "extra"],
        ] {
            assert!(Config::build(args.into_iter().map(String::from), false).is_err());
        }
    }
}
```

Vòng đời `'a` liên kết các lát cắt kết quả với `contents`; dữ liệu kết quả không bị sao chép thành các `String` mới. Chương 17 giải thích cú pháp này. `Box<dyn Error>` cho phép chuyển tiếp nhiều kiểu lỗi của ứng dụng; trong API thư viện lớn, có thể thiết kế enum lỗi riêng.

Hàm không phân biệt hoa/thường dùng `to_lowercase`, chưa phải phép Unicode case folding hoặc chuẩn hóa đầy đủ. Nó tạo chuỗi tạm cho các dòng; đây là cách triển khai dễ hiểu, không tối ưu cho mọi ngôn ngữ và tệp lớn. Tệp được đọc toàn bộ vào bộ nhớ; để xử lý dữ liệu lớn, cân nhắc đọc theo dòng.

#### 16.3. Điểm vào: `src/main.rs`

```rust
use minigrep::Config;
use std::{env, process};

fn main() {
    // Sự hiện diện của biến bật chế độ, kể cả khi giá trị là "0".
    let ignore_case = env::var_os("IGNORE_CASE").is_some();
    let config = Config::build(env::args(), ignore_case).unwrap_or_else(|error| {
        eprintln!("Lỗi tham số: {error}");
        eprintln!("Cú pháp: minigrep <query> <file_path>");
        process::exit(1);
    });

    if let Err(error) = minigrep::run(config) {
        eprintln!("Lỗi thực thi: {error}");
        process::exit(1);
    }
}
```

`env::args()` giả định tham số là Unicode hợp lệ. Công cụ cần chấp nhận mọi đường dẫn hệ điều hành nên dùng `args_os()` và `PathBuf`, đồng thời xử lý việc chuyển đổi từ khóa một cách tường minh.

#### 16.4. Dữ liệu mẫu, kiểm thử và chạy

Tạo `sample.txt` ở gốc dự án:

```text
Rust is productive.
Trust the tests.
A quiet day.
```

```bash
cargo test
cargo run -- Rust sample.txt
```

Lệnh tìm kiếm phân biệt hoa/thường in `Rust is productive.`. Dấu `--` tách tham số của Cargo và tham số truyền vào chương trình.

Để bật chế độ không phân biệt hoa/thường trong Bash:

```bash
IGNORE_CASE=1 cargo run -- rUsT sample.txt
```

Trong PowerShell:

```powershell
$env:IGNORE_CASE = "1"
cargo run -- rUsT sample.txt
Remove-Item Env:IGNORE_CASE
```

Kết quả gồm hai dòng đầu của `sample.txt`. Chạy với tệp không tồn tại để kiểm tra thông báo stderr và mã thoát khác 0. Khi không có dòng khớp, phiên bản học tập này kết thúc thành công mà không in dữ liệu; chưa mô phỏng đầy đủ mã thoát của lệnh `grep`.

**Bài tập:** Thêm số dòng vào kết quả; viết kiểm thử trước khi chỉnh hàm tìm kiếm. Giữ phép tìm kiếm thuần túy, không đọc biến môi trường bên trong test.

---

<a id="phan-viii"></a>

## Phần VIII. Vòng đời, lập trình hàm và con trỏ thông minh

---

<a id="chuong-17"></a>

### Chương 17. Vòng đời tham chiếu

Mọi tham chiếu trong Rust đều có một **Vòng đời (Lifetime)** — là khoảng thời gian mà tham chiếu đó đảm bảo trỏ tới vùng nhớ hợp lệ. Phần lớn thời gian, trình biên dịch tự suy luận được vòng đời; nhưng khi có nhiều tham chiếu đầu vào có thể liên quan đến tham chiếu đầu ra, bạn cần chú thích bằng ký hiệu `'a` để giúp Borrow Checker xác minh tính an toàn.

#### 17.1. Vòng đời và hợp đồng tham chiếu

Tham chiếu không được dùng sau khi dữ liệu mà nó trỏ tới hết vòng đời. Đoạn sau cố ý không biên dịch:

```rust,compile_fail
fn main() {
    let r;
    {
        let x = 5;
        r = &x;
    } // x hết vòng đời.
    println!("{r}"); // Không thể dùng tham chiếu tới x ở đây.
}
```

Khi hàm có nhiều tham chiếu đầu vào, chữ ký cần diễn tả đầu vào nào ràng buộc tham chiếu trả về. Ví dụ:

```rust
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() { x } else { y }
}

fn main() {
    let owned = String::from("Rust programming");
    let result = longest(&owned, "Rust");
    println!("Chuỗi dài hơn theo byte: {result}");
}
```

`'a` là một vòng đời chung mà cả hai đầu vào đều đáp ứng. Tham chiếu đầu ra chỉ được dùng trong khoảng được ràng buộc bởi cả hai phép mượn; khoảng này có thể ngắn hơn vòng đời của từng giá trị gốc. Chú thích không kéo dài dữ liệu và không buộc hai chuỗi bị hủy cùng lúc. Đây là hợp đồng của chữ ký, được kiểm tra độc lập với từng nơi gọi hàm.

---

#### 17.2. Lifetime trong định nghĩa struct và khối `impl`

Struct có trường tham chiếu phải ghi rõ vòng đời của trường: thường là tham số như `'a`, hoặc một vòng đời cụ thể như `'static`. Ví dụ:

```rust
#[derive(Debug)]
struct ImportantExcerpt<'a> {
    part: &'a str, // Struct không được phép sống lâu hơn dữ liệu mà `part` trỏ tới!
}

impl<'a> ImportantExcerpt<'a> {
    // Quy tắc Elision số 3 tự động gán lifetime của &self cho giá trị trả về:
    fn announce_and_return_part(&self, announcement: &str) -> &str {
        println!("📢 Chú ý: {announcement}");
        self.part
    }
}

fn main() {
    let novel = String::from("Ngày xửa ngày xưa. Ở một vương quốc nọ...");
    let first_sentence = novel.split('.').next().unwrap_or("");
    let excerpt = ImportantExcerpt {
        part: first_sentence,
    };
    println!("Trích đoạn: {}", excerpt.announce_and_return_part("Bắt đầu câu chuyện"));
}
```

---

#### 17.3. Ba quy tắc suy đoán vòng đời tự động (lifetime elision rules) và `'static`

Trình biên dịch tự động suy luận lifetime trong chữ ký hàm theo 3 quy tắc:

1. **Quy tắc 1 (Đầu vào):** Mỗi tham số là tham chiếu được gán một tham số lifetime riêng biệt (`fn foo<'a, 'b>(x: &'a i32, y: &'b i32)`).
2. **Quy tắc 2 (Một đầu vào):** Nếu chỉ có **duy nhất 1 tham số lifetime đầu vào**, lifetime đó được gán cho toàn bộ các tham chiếu đầu ra (`fn first_word<'a>(s: &'a str) -> &'a str`).
3. **Quy tắc 3 (Phương thức):** Nếu là phương thức có `&self` hoặc `&mut self`, lifetime của `self` được tự động gán cho toàn bộ các tham chiếu đầu ra.

##### Vòng đời tĩnh `'static`

Tham chiếu `&'static T` cho phép truy cập dữ liệu hợp lệ suốt chương trình, ví dụ chuỗi literal `let s: &'static str = "Hello";`. Biến chứa tham chiếu đó vẫn có thể hết phạm vi sớm.

Ràng buộc **`T: 'static`** có nghĩa kiểu không chứa tham chiếu mượn có vòng đời ngắn hơn `'static`; nó không bắt giá trị phải sống suốt chương trình. Một `String` sở hữu dữ liệu đáp ứng ràng buộc này nhưng vẫn bị hủy bình thường. Không thêm `'static` chỉ để né lỗi mượn.

---

#### 17.4. Kết hợp chung generics, trait bounds và lifetimes trong một hàm

Ví dụ sau kết hợp tham số kiểu, trait bound và lifetime trong cùng một chữ ký hàm:

```rust
use std::fmt::Display;

fn longest_with_an_announcement<'a, T>(
    x: &'a str,
    y: &'a str,
    ann: T,
) -> &'a str
where
    T: Display,
{
    println!("🔔 Thông báo đặc biệt: {ann}");
    if x.len() > y.len() {
        x
    } else {
        y
    }
}

fn main() {
    let s1 = String::from("Rust Edition 2024");
    let s2 = "Rust";
    let result = longest_with_an_announcement(s1.as_str(), s2, "Đang so sánh độ dài chuỗi!");
    println!("Chuỗi dài hơn là: '{result}'");
}
```

---

<a id="chuong-18"></a>

### Chương 18. Closure và iterator

Rust kết hợp vẻ đẹp thanh lịch của Lập trình Hàm (*Functional Programming*) với hiệu năng cấp thấp của ngôn ngữ hệ thống.

#### 18.1. Closures, chế độ bắt giữ môi trường và ba trait `FnOnce`, `FnMut`, `Fn`

**Closure (Hàm đóng)** là hàm ẩn danh có thể lưu vào biến, truyền làm tham số cho hàm khác, và đặc biệt là **có khả năng bắt giữ (capture) các biến từ phạm vi môi trường nơi nó được định nghĩa**.

Cách **bắt giữ biến** và trait **gọi closure** có liên quan nhưng không đồng nhất. trait phụ thuộc việc thân closure sử dụng dữ liệu đã bắt giữ thế nào:

| Trait | Cách gọi | Ý nghĩa |
| :--- | :--- | :--- |
| `FnOnce` | Tiêu thụ closure | Mọi closure đều triển khai; có thể gọi ít nhất một lần. Closure chuyển dữ liệu không có `Copy` ra khỏi môi trường thường chỉ triển khai trait này |
| `FnMut` | Mượn closure qua `&mut self` | Có thể gọi nhiều lần, có thể thay đổi trạng thái đã bắt giữ |
| `Fn` | Mượn closure qua `&self` | Có thể gọi nhiều lần mà không cần mượn độc quyền chính closure |

Quan hệ là `Fn: FnMut` và `FnMut: FnOnce`. `Fn` không tự bảo đảm có thể chia sẻ closure giữa các luồng; cần xét thêm `Send` và `Sync`. Dữ liệu có tính khả biến nội tại vẫn có thể thay đổi bên trong một closure `Fn`.

Từ khóa `move` yêu cầu bắt giữ theo giá trị (sao chép nếu kiểu có `Copy`, move nếu không). Một closure `move` chỉ đọc dữ liệu vẫn có thể triển khai `Fn`. Chuyển một tham chiếu vào closure không kéo dài vòng đời của dữ liệu mà nó mượn.

```rust
use std::thread;

fn main() {
    let list = vec![1, 2, 3];
    println!("Trước khi định nghĩa closure: {list:?}");

    // 1. Closure chỉ mượn bất biến (Fn):
    let only_borrows = || println!("Trong closure mượn: {list:?}");
    only_borrows();
    println!("Sau khi gọi closure mượn: {list:?}");

    // 2. Dùng từ khóa `move` để chuyển hẳn quyền sở hữu `list` sang luồng mới:
    thread::spawn(move || {
        println!("Từ luồng con (đã Move): {list:?}");
    })
    .join()
    .unwrap();
}
```

---

#### 18.2. Iterators: ba phương thức tạo lặp và xây dựng custom iterator

##### 1. Phân biệt 3 phương thức tạo iterator cốt lõi

- **`.iter()`:** Tạo bộ lặp trả về tham chiếu bất biến **`&T`** (giữ nguyên tập hợp gốc).
- **`.iter_mut()`:** Tạo bộ lặp trả về tham chiếu khả biến **`&mut T`** (sửa trực tiếp phần tử tại chỗ).
- **`.into_iter()`:** Tiêu thụ đối tượng nhận theo triển khai `IntoIterator`. Với `Vec<T>` nhận bằng giá trị, nó cho phần tử `T`; với `&Vec<T>` hoặc `&[T]`, nó cho `&T` và không lấy quyền sở hữu tập hợp gốc.

##### 2. Tự xây dựng một cấu trúc iterator tùy chỉnh từ con số 0

Để biến bất kỳ struct nào thành một Iterator có thể dùng với `for`, `.map()`, `.filter()`, `.zip()`, bạn chỉ cần cài đặt duy nhất phương thức `next()` của trait `Iterator`:

```rust
struct Fibonacci {
    curr: Option<u64>,
    next: Option<u64>,
}

impl Fibonacci {
    fn new() -> Self {
        Fibonacci { curr: Some(0), next: Some(1) }
    }
}

impl Iterator for Fibonacci {
    type Item = u64;

    fn next(&mut self) -> Option<Self::Item> {
        let current = self.curr?;
        self.curr = self.next;
        self.next = self.next.and_then(|next| current.checked_add(next));
        Some(current)
    }
}

fn main() {
    // Lấy 10 số Fibonacci đầu tiên, lọc các số chẵn và tính tổng:
    let even_fib_sum: u64 = Fibonacci::new()
        .take(10)
        .filter(|&x| x % 2 == 0)
        .sum();

    println!("Tổng các số Fibonacci chẵn trong 10 số đầu tiên: {even_fib_sum}");
}
```

Ví dụ in tổng `44`. Bộ lặp dừng khi hết các số Fibonacci biểu diễn được bằng `u64`; `checked_add` tránh việc kết quả phụ thuộc cấu hình kiểm tra tràn.

Iterator thường **lười**: `map` và `filter` không duyệt hết dữ liệu ngay. Một thao tác tiêu thụ như `sum`, `collect` hoặc vòng `for` mới thúc đẩy việc duyệt. Trình biên dịch có thể inline, loại bỏ kiểm tra biên hoặc vector hóa, nhưng không bảo đảm mọi chuỗi iterator nhanh hơn vòng lặp; hãy đo trên dữ liệu thực tế.

---

<a id="chuong-19"></a>

### Chương 19. Con trỏ thông minh và khả biến nội tại

Con trỏ thông minh là các kiểu cung cấp hành vi quản lý dữ liệu qua một giao diện giống con trỏ, chẳng hạn sở hữu độc quyền, đếm tham chiếu hoặc quản lý mượn. `Deref` hỗ trợ truy cập dữ liệu đích; `Drop` tùy biến việc dọn tài nguyên. Không phải kiểu nào trong nhóm công cụ quản lý dữ liệu dưới đây cũng trực tiếp triển khai cả hai trait. `RefCell` là một container cho tính khả biến nội tại, thường được dùng cùng con trỏ thông minh.

#### 19.1. Chọn kiểu quản lý dữ liệu

| Kiểu | Sở hữu và truy cập | Điều kiện đa luồng cần nhớ |
| :--- | :--- | :--- |
| `Box<T>` | Sở hữu độc quyền giá trị; thông thường cấp phát heap | `Send` nếu `T: Send`; `Sync` nếu `T: Sync` |
| `Rc<T>` | Sở hữu chia sẻ bằng đếm tham chiếu không nguyên tử; đọc qua tham chiếu chia sẻ | Không có `Send` và `Sync` |
| `RefCell<T>` | Chứa trực tiếp `T`; kiểm tra mượn khi chạy qua `Ref`/`RefMut` | `Send` nếu `T: Send`, nhưng không `Sync`; không chia sẻ truy cập giữa luồng qua `&RefCell<T>` |
| `Arc<T>` | Sở hữu chia sẻ bằng đếm tham chiếu nguyên tử | `Send` và `Sync` khi `T: Send + Sync`; không tự làm dữ liệu bên trong an toàn đa luồng |
| `Cow<'a, B>` | Mượn hoặc sở hữu; `to_mut()` chuyển sang dạng sở hữu khi cần | Phụ thuộc các điều kiện của `B` và kiểu sở hữu tương ứng |

Khi có quyền truy cập duy nhất, `Rc::get_mut` hoặc `Arc::get_mut` có thể cho phép sửa dữ liệu; `make_mut` hỗ trợ clone-on-write. Khi chia sẻ trạng thái cần thay đổi giữa các luồng, thường dùng `Arc<Mutex<T>>`, `Arc<RwLock<T>>` hoặc atomics. Xem [tài liệu Arc](https://doc.rust-lang.org/std/sync/struct.Arc.html) và [RefCell](https://doc.rust-lang.org/std/cell/struct.RefCell.html).

---

#### 19.2. Bố cục và kiểm tra mượn khi chạy

| Kiểu | Mô hình lưu trữ | Điều không nên suy diễn |
| :--- | :--- | :--- |
| `Box<T>` | Handle sở hữu vùng lưu trữ của `T` | Giá trị `Box` không bắt buộc nằm trên stack; kiểu kích thước 0 không cần vùng cấp phát dữ liệu |
| `Rc<T>` | Nhiều handle cùng trỏ tới một vùng dữ liệu và bộ đếm | `Rc::clone` tăng bộ đếm, không sao chép `T` |
| `RefCell<T>` | `T` và trạng thái mượn được chứa trong container | `RefCell::new` không tự cấp phát heap; bố cục nội bộ không phải hợp đồng công khai |

`borrow()` cho phép nhiều mượn chia sẻ, còn `borrow_mut()` đòi quyền mượn độc quyền. Các guard `Ref` và `RefMut` duy trì trạng thái đó đến khi bị hủy; có thể dùng `drop(guard)` để kết thúc sớm. Dùng `try_borrow` hoặc `try_borrow_mut` khi muốn nhận lỗi thay vì `panic`.

---

#### 19.3. Minh họa Deref và Drop bằng MyBox

`MyBox<T>` dưới đây chứa `T` trực tiếp, không cấp phát heap như `Box<T>`. Ví dụ chỉ minh họa cơ chế trait. Khi `MyBox` bị hủy, Rust gọi `drop` rồi tiếp tục hủy các trường của nó.

```rust
use std::ops::Deref;

struct MyBox<T>(T);

impl<T> MyBox<T> {
    fn new(x: T) -> MyBox<T> {
        MyBox(x)
    }
}

impl<T> Deref for MyBox<T> {
    type Target = T;

    fn deref(&self) -> &Self::Target {
        &self.0
    }
}

impl<T> Drop for MyBox<T> {
    fn drop(&mut self) {
        println!("Đang hủy MyBox; trường bên trong sẽ được hủy tiếp theo.");
    }
}

fn hello(name: &str) {
    println!("Xin chào, {name}!");
}

fn main() {
    let m = MyBox::new(String::from("Rustacean"));
    // Deref Coercion tự động chuyển &MyBox<String> -> &String -> &str:
    hello(&m);
}
```

---

#### 19.4. Kết hợp `Rc<RefCell<T>>` và chống rò rỉ bộ nhớ với `Weak<T>`

Khi xây dựng cấu trúc Cây (*Tree*) có nút cha trỏ xuống nút con và nút con trỏ ngược lên nút cha:

- Chiều từ **Cha $\rightarrow$ Con**: Dùng `Rc<T>` (Cha sở hữu con).
- Chiều từ **Con $\rightarrow$ Cha**: Có thể dùng **`Weak<T>`** (`Rc::downgrade`) để phá vỡ vòng lặp tham chiếu (*Reference Cycle*), ngăn chặn rò rỉ bộ nhớ!

```rust
use std::cell::RefCell;
use std::rc::{Rc, Weak};

#[derive(Debug)]
struct Node {
    value: i32,
    parent: RefCell<Weak<Node>>,      // Tham chiếu yếu lên nút cha (không tăng strong_count)
    children: RefCell<Vec<Rc<Node>>>, // Tham chiếu mạnh sở hữu các nút con
}

fn main() {
    let leaf = Rc::new(Node {
        value: 3,
        parent: RefCell::new(Weak::new()),
        children: RefCell::new(vec![]),
    });

    let branch = Rc::new(Node {
        value: 5,
        parent: RefCell::new(Weak::new()),
        children: RefCell::new(vec![Rc::clone(&leaf)]),
    });

    // Gán nút cha cho leaf bằng Rc::downgrade:
    *leaf.parent.borrow_mut() = Rc::downgrade(&branch);

    let parent_value = leaf.parent.borrow().upgrade().map(|node| node.value);
    assert_eq!(parent_value, Some(5));
    assert_eq!(branch.children.borrow().len(), 1);
    drop(branch);
    assert!(leaf.parent.borrow().upgrade().is_none());
}
```

---

#### 19.5. Tối ưu hóa cấp phát với `Cow<'a, B>` (Clone-on-write)

`std::borrow::Cow` (clone-on-write) biểu diễn dữ liệu ở một trong hai dạng:

- `Cow::Borrowed(&'a B)`: Chỉ mượn dữ liệu gốc (không tốn bất kỳ chi phí cấp phát heap nào) nếu dữ liệu không cần chỉnh sửa.
- `Cow::Owned(<B as ToOwned>::Owned)`: Giữ dữ liệu ở dạng sở hữu. Có thể nhận một giá trị đã có sẵn; không nhất thiết vừa cấp phát hoặc vừa sao chép. Gọi `to_mut()` trên biến thể mượn sẽ tạo dữ liệu sở hữu, còn trên biến thể sở hữu sẽ dùng lại dữ liệu hiện có.

```rust
use std::borrow::Cow;

// Thay dấu cách ASCII bằng dấu gạch dưới; đây không phải bộ xác thực tên người dùng.
// Nếu không có dấu cách, trả về lát cắt gốc; nếu có, tạo String thay thế.
fn sanitize_username(input: &str) -> Cow<'_, str> {
    if input.contains(' ') {
        Cow::Owned(input.replace(' ', "_"))
    } else {
        Cow::Borrowed(input)
    }
}

fn main() {
    let clean = sanitize_username("thaiviet_rust"); // Không tốn cấp phát Heap!
    let dirty = sanitize_username("thai viet rust"); // Chỉ cấp phát Heap ở trường hợp này!
    println!("Clean: {clean} | Sanitized: {dirty}");
}
```

> **Thử thách tư duy rustacean (phần viii)**
> **Câu hỏi:** Điều gì sẽ xảy ra khi chạy đoạn mã sử dụng `RefCell` dưới đây?
> ```rust,should_panic
> use std::cell::RefCell;
> fn main() {
>     let data = RefCell::new(vec![1, 2, 3]);
>     let r1 = data.borrow();
>     let r2 = data.borrow_mut();
>     println!("{r1:?}, {r2:?}");
> }
> ```
> **Giải đáp:** Chương trình sẽ **biên dịch thành công** nhưng bị **`panic!` ngay tại thời điểm chạy (runtime)** với thông báo: `already borrowed: BorrowMutError`. Lý do là `RefCell<T>` chuyển việc kiểm tra quy tắc mượn từ lúc biên dịch sang lúc chạy: khi biến `r1` (`Ref<Vec<i32>>`) vẫn đang còn hiệu lực trong scope, việc gọi `data.borrow_mut()` để lấy tham chiếu khả biến sẽ vi phạm quy tắc độc quyền và kích hoạt `panic!`.

---

<a id="phan-ix"></a>

## Phần IX. Đồng thời và bất đồng bộ

---

<a id="chuong-20"></a>

### Chương 20. Lập trình đa luồng

#### 20.1. Tạo luồng (`thread::spawn`), luồng theo phạm vi (`thread::scope`) và kênh `mpsc`

```rust
use std::sync::mpsc;
use std::thread;

fn main() {
    // 1. Scoped Threads: Cho phép các luồng con mượn trực tiếp biến cục bộ trên Stack an toàn!
    let data = vec![10, 20, 30];
    thread::scope(|s| {
        s.spawn(|| {
            println!("🧵 Luồng trong scope mượn trực tiếp data: {data:?}");
        });
    }); // Tự động join mọi luồng trong scope tại đây!

    // 2. Kênh truyền thông điệp mpsc (Multiple Producer, Single Consumer):
    let (tx, rx) = mpsc::channel();
    let tx_clone = tx.clone();

    thread::spawn(move || {
        tx.send(String::from("Thông điệp từ luồng 1")).unwrap();
    });

    thread::spawn(move || {
        tx_clone.send(String::from("Thông điệp từ luồng 2")).unwrap();
    });

    for msg in rx {
        println!("📩 Nhận được: {msg}");
    }
}
```

---

#### 20.2. Chia sẻ trạng thái đa luồng với `Arc<Mutex<T>>` và xử lý poisoned mutex

```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];

    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            let mut num = counter.lock().unwrap();
            *num += 1;
        }); // MutexGuard tự động mở khóa khi ra khỏi scope
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    println!("🎯 Giá trị bộ đếm cuối cùng: {}", *counter.lock().unwrap()); // 10
}
```

>  **Cơ chế Poisoned Mutex (Khóa bị nhiễm độc):** Tại sao `counter.lock()` lại trả về `Result`? Trong Rust, nếu một luồng đang giữ khóa `Mutex` mà bất ngờ bị `panic!`, khóa đó sẽ được đánh dấu là *"Poisoned"* để cảnh báo các luồng khác rằng dữ liệu bên trong có thể đang ở trạng thái dở dang, mất tính nhất quán. Các luồng khác có thể dùng `.unwrap()` để dừng theo, hoặc gọi `.unwrap_or_else(|poisoned| poisoned.into_inner())` để lấy guard dù khóa đã bị poison. `into_inner()` không tự sửa bất biến hoặc xóa trạng thái poison; phải kiểm tra, phục hồi dữ liệu trước khi tiếp tục và dùng `clear_poison()` khi thích hợp. Poisoning là cơ chế cảnh báo, không phải nền tảng để chứng minh an toàn bộ nhớ trong mã `unsafe`.

---

#### 20.3. Khóa đọc-ghi (`RwLock<T>`) và kiểu nguyên tử không khóa (`Atomics`)

1. **`RwLock<T>` (Read-Write Lock):** Trong khi `Mutex<T>` chỉ cho phép duy nhất 1 luồng truy cập tại một thời điểm (dù chỉ để đọc), `RwLock<T>` cho phép **nhiều luồng cùng đọc đồng thời (`.read()`)** hoặc **duy nhất 1 luồng ghi độc quyền (`.write()`)**. Có thể phù hợp khi đọc nhiều, ghi ít; hiệu năng và tính công bằng tùy triển khai, nên đo thay vì mặc định nó nhanh hơn `Mutex`.
2. **Kiểu Nguyên Tử (`std::sync::atomic`):** Cung cấp các thao tác nguyên tử trên những kiểu được target hỗ trợ. Tránh được một số nhu cầu dùng mutex nhưng vẫn có chi phí đồng bộ và tranh chấp bộ nhớ đệm; thuật toán ghép nhiều thao tác nguyên tử chưa chắc đúng nếu thiếu quy tắc thứ tự bộ nhớ:

```rust
use std::sync::atomic::{AtomicUsize, Ordering};
use std::sync::{Arc, RwLock};
use std::thread;

fn main() {
    // 1. Sử dụng AtomicUsize cho bộ đếm tốc độ siêu cao không cần Mutex:
    let active_requests = Arc::new(AtomicUsize::new(0));
    let req_clone = Arc::clone(&active_requests);

    thread::spawn(move || {
        req_clone.fetch_add(1, Ordering::SeqCst);
    })
    .join()
    .unwrap();

    println!("⚡ Số request nguyên tử: {}", active_requests.load(Ordering::SeqCst));

    // 2. Sử dụng RwLock cho phép nhiều luồng đọc cùng lúc:
    let config = Arc::new(RwLock::new(String::from("v1.0.0")));
    let r1 = config.read().unwrap();
    let r2 = config.read().unwrap(); // Nhiều người đọc cùng lúc hoàn toàn không chặn nhau!
    println!("📖 Đọc cấu hình song song: {} & {}", *r1, *r2);
}
```

##### Hai marker traits cốt lõi: `Send` và `Sync`

-  **`Send`:** Đánh dấu kiểu dữ liệu an toàn khi **chuyển giao quyền sở hữu (Move) giữa các luồng**.
-  **`Sync`:** Đánh dấu kiểu dữ liệu an toàn khi **chia sẻ tham chiếu bất biến (`&T`) giữa nhiều luồng cùng lúc** ($T$ là `Sync` $\iff \&T$ là `Send`).

---

`Ordering::Relaxed` chỉ bảo đảm tính nguyên tử của thao tác, không đồng bộ dữ liệu khác. `Acquire`/`Release` dùng để thiết lập quan hệ công bố và quan sát dữ liệu; `SeqCst` bổ sung một thứ tự toàn cục cho các thao tác dùng chế độ đó. Chọn ordering theo chứng minh của thuật toán, không chỉ theo kỳ vọng tốc độ.

Safe Rust có thể ngăn data race nhưng vẫn có deadlock nếu các luồng lấy nhiều khóa theo thứ tự xung đột. Giữ phạm vi khóa ngắn, thống nhất thứ tự lấy khóa và tránh giữ khóa trong khi chờ một tác vụ phụ thuộc vào chính khóa đó.

<a id="chuong-21"></a>

### Chương 21. Lập trình bất đồng bộ

#### 21.1. Luồng hệ điều hành, task và future

| Đặc điểm | Luồng hệ điều hành | Task bất đồng bộ |
| :--- | :--- | :--- |
| Lập lịch | Do hệ điều hành quản lý | Do executor của runtime quản lý |
| Bộ nhớ | Có stack riêng với kích thước phụ thuộc nền tảng/cấu hình | Giữ trạng thái future và dữ liệu còn sống qua `.await`; không có kích thước cố định chung |
| Điểm mạnh | Công việc đồng bộ, tính toán song song trên nhiều lõi | Nhiều tác vụ thường xuyên chờ I/O |
| Rủi ro | Chi phí tạo luồng, khóa và tranh chấp | Chặn executor, hủy tác vụ sai thời điểm, tạo quá nhiều task không giới hạn |

**Concurrency** là khả năng quản lý nhiều công việc cùng tiến triển; **parallelism** là thực thi cùng lúc trên nhiều tài nguyên xử lý. `async` không tự tạo luồng và không bảo đảm chạy song song.

Gọi `async fn` tạo một future; thân hàm chỉ tiến triển khi future được poll. `.await` có thể hoàn tất ngay nếu kết quả sẵn sàng, hoặc nhường quyền cho executor khi chưa sẵn sàng. Đây là chữ ký rút gọn của trait chuẩn `Future`, không cần định nghĩa lại:

```rust
use std::pin::Pin;
use std::task::{Context, Poll};

pub trait Future {
    type Output;
    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output>;
}
```

`Poll::Ready(value)` chứa kết quả; `Poll::Pending` báo chưa hoàn tất. Future cần đăng ký cơ chế đánh thức qua `Waker` khi có thể tiến triển. Không nên tự poll liên tục trong vòng lặp bận.

`Pin<P>` bảo vệ việc giữ nguyên vị trí của **giá trị đích** khi kiểu cần pinning, không nhất thiết cố định chính handle con trỏ. Điều này quan trọng với một số future có trạng thái tự tham chiếu. Kiểu `Unpin` không cần hạn chế đó. Thư viện và `.await` thường xử lý chi tiết pinning giúp người dùng.

#### 21.2. Thiết lập Tokio

```bash
cargo new async_demo --edition 2024
cd async_demo
```

Nội dung `Cargo.toml`:

```toml
[package]
name = "async_demo"
version = "0.1.0"
edition = "2024"
rust-version = "1.85"

[dependencies]
tokio = { version = "=1.43.0", features = ["macros", "rt-multi-thread", "sync", "time"] }
```

Đây là phiên bản cố định cho các API trong ví dụ, không phải tuyên bố phiên bản mới nhất. Khi nâng thư viện, đọc ghi chú phát hành và chạy lại kiểm thử. Các ví dụ ở mục 21.3 và 21.4 là hai nội dung `src/main.rs` thay thế cho nhau.

#### 21.3. Join!, select!, spawn và kênh bất đồng bộ

```rust
use tokio::sync::mpsc;
use tokio::time::{sleep, Duration};

async fn simulate_service(name: &str, milliseconds: u64) -> String {
    sleep(Duration::from_millis(milliseconds)).await;
    format!("Phản hồi mô phỏng từ {name}")
}

#[tokio::main]
async fn main() {
    // Đồng thời trên cùng task; join! không tự tạo hai luồng.
    let (auth, order) = tokio::join!(
        simulate_service("AuthService", 200),
        simulate_service("OrderService", 300),
    );
    println!("{auth}; {order}");

    // Future mô phỏng bị hủy nếu nhánh timeout được chọn trước.
    tokio::select! {
        response = simulate_service("PaymentService", 100) => {
            println!("{response}");
        }
        _ = sleep(Duration::from_millis(500)) => {
            println!("Đã hết thời gian chờ.");
        }
    }

    let (tx, mut rx) = mpsc::channel(32);
    let mut handles = Vec::new();
    for index in 1..=3 {
        let sender = tx.clone();
        handles.push(tokio::spawn(async move {
            sender.send(format!("Sự kiện #{index}")).await
        }));
    }
    drop(tx); // Không giữ đầu gửi gốc làm kênh mở mãi.

    while let Some(message) = rx.recv().await {
        println!("{message}");
    }
    for handle in handles {
        handle.await.expect("Task bị panic").expect("Đầu nhận đã đóng");
    }
}
```

Chạy `cargo run`; chương trình in hai phản hồi đầu, kết quả cuộc đua với timeout và ba sự kiện. Thứ tự ba sự kiện không được bảo đảm.

- `join!` chờ các nhánh hoàn tất trong một task. Một nhánh chặn luồng sẽ cản nhánh còn lại.
- `select!` chọn một nhánh sẵn sàng; các future do lần gọi sở hữu còn lại bị hủy. Hủy future không hoàn tác mọi hiệu ứng đã xảy ra ở hệ thống ngoài. Với `JoinHandle`, bỏ handle thường tách task chứ không hủy task; phải quản lý việc dừng riêng.
- `tokio::spawn` trên runtime này yêu cầu future có `Send + 'static`; dữ liệu sống qua `.await` phải đáp ứng điều kiện tương ứng. Giữ và chờ handle giúp quan sát kết quả hoặc lỗi của task.
- Kênh có giới hạn dung lượng tạo sức ép ngược (*backpressure*): `send().await` chờ khi kênh đầy, thay vì tăng bộ nhớ vô hạn.

Trong mã chạy trên Tokio, dùng `tokio::time::sleep(...).await` cho việc chờ. Đưa I/O đồng bộ hoặc công việc chặn sang `spawn_blocking` khi phù hợp; giới hạn mức song song cho tác vụ CPU nặng, hoặc dùng một pool tính toán chuyên dụng. Không giữ `std::sync::MutexGuard` qua `.await`. Công việc đã chạy trong `spawn_blocking` thường không thể bị dừng chỉ bằng cách hủy future chờ nó.

Tham khảo [Tokio tutorial](https://tokio.rs/tokio/tutorial), [spawning](https://tokio.rs/tokio/tutorial/spawning) và [select/cancellation](https://tokio.rs/tokio/tutorial/select).

#### 21.4. Async trong trait và async closure

`async fn` trong trait được ổn định từ Rust 1.75; async closure và các trait gọi tương ứng được ổn định từ Rust 1.85. Đây là các mốc phiên bản trình biên dịch, không phải mọi tính năng đều chỉ dùng được trong Edition 2024.

```rust
use std::ops::AsyncFnMut;
use tokio::time::{sleep, Duration};

trait HealthCheck {
    async fn check_status(&self) -> Result<String, &'static str>;
}

struct MockDatabase;

impl HealthCheck for MockDatabase {
    async fn check_status(&self) -> Result<String, &'static str> {
        Ok(String::from("Cơ sở dữ liệu giả lập đang hoạt động"))
    }
}

async fn run_action<F>(mut action: F)
where
    F: AsyncFnMut() -> String,
{
    println!("{}", action().await);
}

#[tokio::main]
async fn main() {
    let database = MockDatabase;
    println!("{:?}", database.check_status().await);

    let prefix = String::from("Yêu cầu #101");
    let task = async || {
        sleep(Duration::from_millis(10)).await;
        format!("{prefix}: đã xử lý")
    };
    run_action(task).await;
}
```

Trait chứa phương thức `async fn` như trên không tự dùng được qua `dyn HealthCheck`. Thiết kế API công khai còn cần quyết định future trả về có `Send` hay không; có thể biểu diễn bằng phương thức trả `impl Future + Send`, hoặc một future đóng hộp nếu cần phân phối động. macro như `async-trait` giải quyết một số nhu cầu này với cách biểu diễn và chi phí riêng.

---

<a id="phan-x"></a>

## Phần X. Chủ đề nâng cao và máy chủ web

---

<a id="chuong-22"></a>

### Chương 22. Unsafe Rust, FFI và kiểu nâng cao

#### 22.1. Ranh giới của unsafe

`unsafe` không tắt borrow checker và không có nghĩa mọi câu lệnh trong khối đều nguy hiểm. Nó đánh dấu nơi người viết phải bảo đảm những điều kiện mà trình biên dịch không chứng minh thay được. Các nhóm thao tác thường gặp gồm:

1. Giải tham chiếu con trỏ thô `*const T` hoặc `*mut T`.
2. Gọi hàm hoặc phương thức `unsafe`.
3. Truy cập biến `static mut` theo các điều kiện an toàn thích hợp.
4. Triển khai một `unsafe trait` bằng `unsafe impl`.
5. Đọc trường của `union` khi thao tác đó đòi hỏi `unsafe`.

Trong Edition 2024, khối khai báo ngoại ngữ phải dùng `unsafe extern`; tạo tham chiếu tới `static mut` bị lint `static_mut_refs` từ chối mặc định. Điều này không cấm mọi thao tác trên biến tĩnh khả biến và cũng không làm con trỏ thô tự trở nên an toàn. Ưu tiên kiểu đồng bộ như `Mutex`, atomics, `OnceLock` hoặc `LazyLock` khi chúng phù hợp.

#### 22.2. Con trỏ thô và FFI

Ví dụ sau dùng thư viện C trên target có C runtime cung cấp `abs` (chẳng hạn các môi trường desktop thông dụng). Việc liên kết thư viện ngoại vi khác có thể cần cấu hình linker và build script riêng.

```rust
use std::ffi::c_int;

unsafe extern "C" {
    fn abs(value: c_int) -> c_int;
}

fn c_abs(value: c_int) -> Option<c_int> {
    if value == c_int::MIN {
        return None; // Trị tuyệt đối không biểu diễn được bằng c_int.
    }
    // SAFETY: Chữ ký và ABI khớp hàm C abs; đã loại trường hợp c_int::MIN.
    Some(unsafe { abs(value) })
}

fn main() {
    let mut number: c_int = 42;
    let pointer = &raw mut number;

    // SAFETY: pointer trỏ tới number còn sống, đúng căn chỉnh, đã khởi tạo;
    // không có truy cập xung đột trong lúc ghi.
    unsafe {
        *pointer = -100;
    }

    assert_eq!(number, -100);
    assert_eq!(c_abs(number), Some(100));
    assert_eq!(c_abs(c_int::MIN), None);
}
```

Hàm C `abs` **không an toàn với mọi `c_int`**: trường hợp kết quả không biểu diễn được có hành vi không xác định. Với mã Rust thuần, thường nên dùng `checked_abs()` để nhận `Option` mà không cần FFI.

Toán tử `&raw const`/`&raw mut` có từ Rust 1.82, không riêng Edition 2024. Tạo con trỏ không phải chứng minh nó được phép giải tham chiếu: phải xét vòng đời, căn chỉnh, khởi tạo, aliasing và quyền truy cập. Cấu trúc trao đổi trực tiếp với C thường cần `#[repr(C)]`; không giả định `String`, `Vec` hoặc `&str` có bố cục ABI giống kiểu C.

Trong một `unsafe fn`, nên dùng khối `unsafe {}` nhỏ cho từng thao tác và ghi rõ lập luận `SAFETY`. Edition 2024 bật cảnh báo `unsafe_op_in_unsafe_fn` mặc định. Một hàm bọc chỉ được công khai là **safe** nếu nó bảo đảm mọi điều kiện an toàn cho mọi cách gọi hợp lệ của API; nếu vẫn phụ thuộc nghĩa vụ của bên gọi, giữ `unsafe fn` và tài liệu hóa mục `# Safety`.

#### 22.3. Bí danh kiểu, kiểu ! và kiểu có kích thước động

**Bí danh kiểu** tạo tên khác cho cùng kiểu, không tạo kiểu mới như newtype:

```rust
type Thunk = Box<dyn Fn() + Send + 'static>;
type IoResult<T> = Result<T, std::io::Error>;
```

**Kiểu `!`** biểu thị tính toán không hoàn tất bình thường. Có thể dùng làm kiểu trả về của hàm không bao giờ trả về:

```rust
fn stop(message: &str) -> ! {
    panic!("{message}")
}
```

`return`, `break`, `continue` và `panic!` là những biểu thức chuyển điều khiển có kiểu `!`. Một biểu thức `loop` có thể có kiểu khác nếu thoát bằng `break value`; không phải mọi `loop` đều có kiểu `!`. Việc dùng `!` ở mọi vị trí kiểu còn tùy phiên bản và trạng thái ổn định của tính năng.

**DST — dynamically sized type:** `str`, `[T]` và `dyn Trait` không có kích thước cố định trong bản thân kiểu. Ta thường dùng qua con trỏ như `&str`, `&[T]` hay `Box<dyn Trait>`. Tham số kiểu generic mặc định có ràng buộc `Sized`; `?Sized` nới ràng buộc đó:

```rust
fn debug_value<T: std::fmt::Debug + ?Sized>(value: &T) {
    println!("{value:?}");
}

fn main() {
    debug_value("Rust"); // T có thể là str, một DST.
}
```

Tham khảo [Rust Reference: unsafe](https://doc.rust-lang.org/reference/unsafe-keyword.html) và [Edition Guide: newly unsafe functions](https://doc.rust-lang.org/edition-guide/rust-2024/newly-unsafe-functions.html). Đặc biệt, `std::env::set_var` và `remove_var` là unsafe trong Edition 2024; nên truyền cấu hình vào hàm hoặc đặt môi trường khi khởi chạy chương trình thay vì sửa môi trường toàn tiến trình trong chương trình đa luồng.

---

<a id="chuong-23"></a>

### Chương 23. Siêu lập trình với macro

**macro** là kỹ thuật viết mã sinh ra mã (*code that writes code*) ngay tại thời điểm biên dịch, giúp mở rộng cú pháp ngôn ngữ và giảm mã lặp lại (*boilerplate*).

#### 23.1. Declarative macros (`macro_rules!`) và các bộ chỉ định mẫu

Declarative macro hoạt động tương tự như biểu thức `match`, nhưng thay vì so khớp giá trị lúc chạy, nó **so khớp cấu trúc cây cú pháp Rust tại thời điểm biên dịch**.

##### Các bộ chỉ định phân mảnh cú pháp (fragment specifiers) quan trọng

- `$x:expr`: Một biểu thức bất kỳ (ví dụ: `1 + 2`, `func()`, `"hello"`).
- `$i:ident`: Một tên định danh biến, hàm hoặc kiểu (ví dụ: `my_var`, `User`).
- `$t:ty`: Một kiểu dữ liệu (ví dụ: `i32`, `Vec<String>`).
- `$p:pat`: Một mẫu pattern matching.
- `$tt:tt`: Một Token Tree đơn lẻ.
- `$( ... ),*` (hoặc `$( ... ),+`): Lặp lại mẫu 0 hoặc nhiều lần (`*`), hoặc 1 hoặc nhiều lần (`+`), phân tách bởi dấu phẩy.

```rust
#[macro_export]
macro_rules! hashmap {
    // Nhánh 1: Gọi hashmap!() rỗng
    () => {
        ::std::collections::HashMap::new()
    };
    // Nhánh 2: Khởi tạo với danh sách các cặp key => value
    // $(,)? ở cuối cho phép có hoặc không có dấu phẩy thừa (trailing comma)
    ( $( $key:expr => $val:expr ),+ $(,)? ) => {
        {
            let mut map = ::std::collections::HashMap::new();
            $(
                map.insert($key, $val);
            )+
            map
        }
    };
}

fn main() {
    let capitals = hashmap! {
        "Việt Nam" => "Hà Nội",
        "Nhật Bản" => "Tokyo",
    };
    println!("Thủ đô: {capitals:?}");
}
```

---

#### 23.2. Procedural macro: một workspace hoàn chỉnh

Procedural macro nhận và sinh `proc_macro::TokenStream` trong quá trình biên dịch. Có ba nhóm: derive macro, attribute macro và function-like macro. Chúng được định nghĩa trong crate có `proc-macro = true`; `syn` và `quote` là các thư viện hỗ trợ phổ biến, không phải yêu cầu bắt buộc của ngôn ngữ.

Ví dụ sau tạo ba package: một thư viện định nghĩa trait, một thư viện procedural macro và một ứng dụng dùng chúng.

##### Thiết lập workspace

Tạo thư mục `macro_demo`, rồi tạo các package bên trong:

```bash
mkdir macro_demo
cd macro_demo
cargo new hello_macro --lib --edition 2024
cargo new hello_macro_derive --lib --edition 2024
cargo new demo --edition 2024
```

Tạo `Cargo.toml` ở gốc `macro_demo`:

```toml
[workspace]
members = ["hello_macro", "hello_macro_derive", "demo"]
resolver = "3"
```

##### Trait: `hello_macro/src/lib.rs`

```rust
pub trait HelloMacro {
    fn hello_macro();
}
```

Giữ manifest do Cargo tạo cho `hello_macro`; thư viện này không cần phụ thuộc ngoài.

##### Manifest: `hello_macro_derive/Cargo.toml`

```toml
[package]
name = "hello_macro_derive"
version = "0.1.0"
edition = "2024"
rust-version = "1.85"

[lib]
proc-macro = true

[dependencies]
syn = "2.0"
quote = "1.0"
```

##### Macro: `hello_macro_derive/src/lib.rs`

```rust
use proc_macro::TokenStream;
use quote::quote;
use syn::{parse_macro_input, DeriveInput};

#[proc_macro_derive(HelloMacro)]
pub fn hello_macro_derive(input: TokenStream) -> TokenStream {
    let ast = parse_macro_input!(input as DeriveInput);
    let name = &ast.ident;
    let (impl_generics, type_generics, where_clause) = ast.generics.split_for_impl();

    quote! {
        impl #impl_generics ::hello_macro::HelloMacro
            for #name #type_generics #where_clause
        {
            fn hello_macro() {
                ::std::println!("Xin chào từ kiểu {}!", ::std::stringify!(#name));
            }
        }
    }
    .into()
}
```

`split_for_impl` giữ tham số generic và mệnh đề `where`; bỏ chúng sẽ khiến derive thất bại trên kiểu generic. Mã sinh ra dùng đường dẫn tuyệt đối đến trait. Bản học tập này yêu cầu bên dùng giữ tên phụ thuộc `hello_macro`; nếu cho phép đổi tên phụ thuộc, thư viện macro cần thêm cơ chế phân giải tên crate phù hợp.

##### Manifest: `demo/Cargo.toml`

```toml
[package]
name = "demo"
version = "0.1.0"
edition = "2024"
rust-version = "1.85"

[dependencies]
hello_macro = { path = "../hello_macro" }
hello_macro_derive = { path = "../hello_macro_derive" }
```

##### Ứng dụng: `demo/src/main.rs`

```rust
use hello_macro::HelloMacro;

#[derive(hello_macro_derive::HelloMacro)]
struct Pancakes;

#[derive(hello_macro_derive::HelloMacro)]
struct Wrapper<T>(T);

fn main() {
    Pancakes::hello_macro();
    Wrapper::<u32>::hello_macro();
}
```

Chạy ở gốc workspace:

```bash
cargo check --workspace
cargo run -p demo
```

Kết quả gồm `Xin chào từ kiểu Pancakes!` và `Xin chào từ kiểu Wrapper!`. Đây là derive macro tối giản; macro dùng cho thư viện lớn cần thông báo lỗi có vị trí, kiểm thử compile-fail và chính sách hỗ trợ kiểu đầu vào rõ ràng.

---

<a id="chuong-24"></a>

### Chương 24. Dự án 3 — Máy chủ web với thread pool

Dự án kết hợp TCP, nhóm luồng (*thread pool*), kênh truyền việc, `Arc<Mutex<T>>` và `Drop`. Máy chủ xử lý một tập con nhỏ của yêu cầu HTTP/1.1 để học cách phối hợp các thành phần; đây không phải triển khai HTTP đầy đủ hay máy chủ dùng trực tiếp cho môi trường vận hành thực tế.

#### 24.1. Tạo dự án

```bash
cargo new web_server --edition 2024
cd web_server
```

Giữ `name = "web_server"` trong manifest. Không cần crate ngoài. Chuẩn bị các tệp sau:

| Tệp | Nội dung |
| :--- | :--- |
| `Cargo.toml` | Manifest do Cargo tạo với Edition 2024 |
| `src/lib.rs` | Thread pool và kiểm thử |
| `src/main.rs` | Lắng nghe TCP và xử lý yêu cầu |
| `hello.html` | Nội dung phản hồi thành công |
| `404.html` | Nội dung khi không tìm thấy đường dẫn |

#### 24.2. Thread pool: `src/lib.rs`

```rust
use std::sync::{mpsc, Arc, Mutex};
use std::thread;

type Job = Box<dyn FnOnce() + Send + 'static>;

pub struct ThreadPool {
    workers: Vec<Worker>,
    sender: Option<mpsc::SyncSender<Job>>,
}

impl ThreadPool {
    /// Tạo nhóm luồng với hàng đợi giới hạn 64 công việc.
    ///
    /// # Panics
    /// Panic nếu size bằng 0 hoặc hệ điều hành không tạo được luồng.
    pub fn new(size: usize) -> Self {
        assert!(size > 0, "ThreadPool cần ít nhất một luồng");
        let (sender, receiver) = mpsc::sync_channel::<Job>(64);
        let receiver = Arc::new(Mutex::new(receiver));
        let workers = (0..size)
            .map(|id| Worker::new(id, Arc::clone(&receiver)))
            .collect();
        Self { workers, sender: Some(sender) }
    }

    /// Gửi một công việc; có thể chờ khi hàng đợi đã đầy.
    pub fn execute<F>(&self, job: F) -> Result<(), &'static str>
    where
        F: FnOnce() + Send + 'static,
    {
        let sender = self.sender.as_ref().ok_or("ThreadPool đã đóng")?;
        sender.send(Box::new(job)).map_err(|_| "Không còn worker nhận việc")
    }
}

impl Drop for ThreadPool {
    fn drop(&mut self) {
        // Đóng đầu gửi trước khi chờ worker, tránh recv() chờ mãi.
        drop(self.sender.take());
        for worker in &mut self.workers {
            if let Some(handle) = worker.thread.take() {
                if handle.join().is_err() {
                    eprintln!("Worker {} đã kết thúc do panic", worker.id);
                }
            }
        }
    }
}

struct Worker {
    id: usize,
    thread: Option<thread::JoinHandle<()>>,
}

impl Worker {
    fn new(id: usize, receiver: Arc<Mutex<mpsc::Receiver<Job>>>) -> Self {
        let thread = thread::spawn(move || loop {
            let message = {
                let guard = match receiver.lock() {
                    Ok(guard) => guard,
                    Err(_) => {
                        eprintln!("Khóa đầu nhận bị poison; worker {id} dừng");
                        break;
                    }
                };
                guard.recv()
            }; // Guard bị hủy trước khi thực thi job.

            match message {
                Ok(job) => job(),
                Err(_) => break, // Kênh đã đóng và không còn công việc.
            }
        });
        Self { id, thread: Some(thread) }
    }
}

#[cfg(test)]
mod tests {
    use super::ThreadPool;
    use std::sync::atomic::{AtomicUsize, Ordering};
    use std::sync::Arc;

    #[test]
    fn drop_waits_for_submitted_jobs() {
        let completed = Arc::new(AtomicUsize::new(0));
        {
            let pool = ThreadPool::new(2);
            for _ in 0..10 {
                let completed = Arc::clone(&completed);
                pool.execute(move || {
                    completed.fetch_add(1, Ordering::SeqCst);
                }).unwrap();
            }
        }
        assert_eq!(completed.load(Ordering::SeqCst), 10);
    }

    #[test]
    #[should_panic(expected = "ít nhất một luồng")]
    fn rejects_zero_workers() {
        let _pool = ThreadPool::new(0);
    }
}
```

Mỗi worker giữ khóa chỉ trong lúc chờ/lấy một công việc; khóa được thả trước khi gọi `job()`. Không viết gộp thành `while let Ok(job) = receiver.lock().unwrap().recv() { job(); }`, vì temporary guard trong điều kiện có thể được giữ suốt thân vòng lặp, làm các job chạy tuần tự.

Đóng sender cho phép các worker xử lý nốt hàng đợi rồi thoát khi `recv` báo kênh đóng. `Drop` chờ chúng bằng `join`. Cơ chế này giả định các job kết thúc; một job bị treo có thể khiến quá trình tắt chờ mãi. Bản đơn giản này không tạo lại worker sau panic, không bảo đảm chạy đủ job nếu toàn bộ worker đã chết và không tự bắt tín hiệu Ctrl+C.

#### 24.3. Nội dung html

`hello.html`:

```html
<!doctype html>
<html lang="vi">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Xin chào Rust</title>
  </head>
  <body>
    <h1>Máy chủ Rust đang hoạt động</h1>
    <p>Phản hồi được xử lý bởi một worker trong thread pool.</p>
  </body>
</html>
```

`404.html`:

```html
<!doctype html>
<html lang="vi">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Không tìm thấy</title>
  </head>
  <body>
    <h1>404 — Không tìm thấy đường dẫn</h1>
    <p><a href="/">Về trang đầu</a></p>
  </body>
</html>
```

#### 24.4. Máy chủ tcp: `src/main.rs`

```rust
use std::io::{self, BufRead, BufReader, Read, Write};
use std::net::{TcpListener, TcpStream};
use std::thread;
use std::time::Duration;
use web_server::ThreadPool;

const MAX_HEADER_BYTES: usize = 8 * 1024;
const HELLO: &str = include_str!("../hello.html");
const NOT_FOUND: &str = include_str!("../404.html");

fn main() -> io::Result<()> {
    let listener = TcpListener::bind("127.0.0.1:7878")?;
    let pool = ThreadPool::new(4);
    println!("Mở http://127.0.0.1:7878; máy chủ sẽ dừng sau 5 kết nối.");

    for _ in 0..5 {
        let (stream, _) = listener.accept()?;
        pool.execute(move || {
            if let Err(error) = handle_connection(stream) {
                eprintln!("Lỗi kết nối: {error}");
            }
        })
        .map_err(io::Error::other)?;
    }

    drop(listener); // Không nhận kết nối mới.
    drop(pool);     // Chờ những job đã gửi hoàn tất.
    println!("Đã dừng máy chủ.");
    Ok(())
}

fn handle_connection(mut stream: TcpStream) -> io::Result<()> {
    stream.set_read_timeout(Some(Duration::from_secs(5)))?;
    stream.set_write_timeout(Some(Duration::from_secs(5)))?;

    let request_line = {
        // Giới hạn tổng số byte có thể đọc trước khi phân tích xong header.
        let limited = (&mut stream).take((MAX_HEADER_BYTES + 1) as u64);
        let mut reader = BufReader::new(limited);
        let mut total = 0;
        let mut first_line = None;
        loop {
            let mut line = String::new();
            let count = reader.read_line(&mut line)?;
            if count == 0 {
                return Err(io::Error::new(io::ErrorKind::UnexpectedEof, "Header chưa hoàn tất"));
            }
            total += count;
            if total > MAX_HEADER_BYTES || !line.ends_with("\r\n") {
                return Err(io::Error::new(io::ErrorKind::InvalidData, "Header quá dài hoặc sai định dạng"));
            }
            if line == "\r\n" {
                break;
            }
            if first_line.is_none() {
                first_line = Some(line.trim_end_matches("\r\n").to_owned());
            }
        }
        first_line.unwrap_or_default()
    }; // Kết thúc mượn stream của reader trước khi ghi phản hồi.

    let parts: Vec<&str> = request_line.split_whitespace().collect();
    let (status, body) = if parts.len() != 3 || parts[2] != "HTTP/1.1" {
        ("400 Bad Request", "Yêu cầu không hợp lệ")
    } else if parts[0] != "GET" {
        ("405 Method Not Allowed", "Ví dụ chỉ hỗ trợ GET")
    } else {
        match parts[1] {
            "/" => ("200 OK", HELLO),
            "/sleep" => {
                // Chờ đồng bộ có chủ đích để quan sát các worker khác tiếp tục chạy.
                thread::sleep(Duration::from_secs(2));
                ("200 OK", HELLO)
            }
            _ => ("404 Not Found", NOT_FOUND),
        }
    };

    let allow = if status.starts_with("405") { "Allow: GET\r\n" } else { "" };
    let response = format!(
        "HTTP/1.1 {status}\r\nContent-Type: text/html; charset=utf-8\r\nContent-Length: {}\r\nConnection: close\r\n{allow}\r\n{body}",
        body.len()
    );
    stream.write_all(response.as_bytes())?;
    Ok(())
}
```

`include_str!` nhúng hai tệp HTML khi biên dịch, nên máy chủ không phụ thuộc thư mục làm việc lúc chạy. Sửa HTML cần biên dịch lại. `Content-Length` tính theo **byte**; `Connection: close` nói rõ mỗi kết nối chỉ phục vụ một yêu cầu.

Bản học tập chưa phân tích và kiểm tra đầy đủ header HTTP, không xử lý request body, keep-alive, TLS hay mọi dạng lỗi giao thức. Timeout ở đây áp dụng cho thao tác I/O, không phải hạn chót tuyệt đối cho toàn bộ yêu cầu. Các giới hạn byte và hàng đợi giúp minh họa quản lý tài nguyên, không biến ví dụ thành máy chủ hoàn chỉnh về bảo mật hoặc tuân thủ giao thức.

#### 24.5. Chạy thử và quan sát quá trình tắt

```bash
cargo test
cargo run
```

Trong terminal khác, chạy lần lượt năm lệnh sau (PowerShell có thể dùng `curl.exe`):

```bash
curl -i http://127.0.0.1:7878/
curl -i http://127.0.0.1:7878/missing
curl -i http://127.0.0.1:7878/sleep
curl -i http://127.0.0.1:7878/
curl -i http://127.0.0.1:7878/
```

Đường dẫn `/missing` trả 404, `/sleep` chờ khoảng hai giây rồi trả 200. Sau năm kết nối, vòng nhận kết thúc và thread pool chờ việc đang chạy hoàn tất. Trình duyệt có thể tạo thêm kết nối, chẳng hạn để lấy favicon; vì vậy dùng các lệnh trên để quan sát số kết nối rõ ràng.

Để quan sát xử lý đồng thời, khởi động lại máy chủ, gọi `/sleep` ở một terminal và ngay sau đó gọi `/` ở terminal khác. Yêu cầu `/` có thể hoàn tất trước yêu cầu đang ngủ nếu còn worker rảnh. Nếu đổi vòng nhận thành `loop`, cần thiết kế thêm cơ chế dừng chủ động; nhấn Ctrl+C mặc định không chứng minh `Drop` sẽ chạy.

**Bài tập:** Thêm giới hạn thời gian cho toàn yêu cầu, kiểm thử lỗi kết nối và cơ chế dừng có tín hiệu. Khi xây dựng dịch vụ thật, dùng thư viện HTTP có bộ phân tích giao thức và chính sách vận hành phù hợp.

---

<a id="phan-xi"></a>

## Phần XI. Phụ lục tra cứu

---

<a id="phu-luc-a"></a>

### Phụ lục A. Từ khóa và định danh thô

#### 1. Các từ khóa đang sử dụng (keywords currently in use)

|  Từ khóa |  Ý nghĩa và Công dụng chính |
| :--- | :--- |
| `as` | Ép kiểu nguyên thủy, giải quyết xung đột tên Trait, hoặc đổi tên định danh trong `use` |
| `async` | Biến một hàm, khối lệnh hoặc closure thành trả về một `Future` |
| `await` | Tạm dừng thực thi hàm `async` cho đến khi kết quả của `Future` sẵn sàng |
| `break` | Thoát khỏi vòng lặp ngay lập tức (có thể trả về giá trị từ `loop`) |
| `const` | Định nghĩa hằng số thời điểm biên dịch, hằng số generic hoặc con trỏ thô hằng |
| `continue` | Bỏ qua phần còn lại của lượt lặp hiện tại và chuyển sang lượt lặp kế tiếp |
| `crate` | Chỉ định gốc của crate hiện tại trong đường dẫn module (`crate::...`) |
| `dyn` | Đánh dấu kiểu phân phối động của một trait Object (`dyn Trait`) |
| `else` | Nhánh rẽ dự phòng cho cấu trúc `if`, `if let`, hoặc `let else` |
| `enum` | Định nghĩa một kiểu dữ liệu liệt kê nhiều biến thể |
| `extern` | Liên kết với các hàm hoặc biến bên ngoài qua FFI (`unsafe extern "C"`) |
| `false` / `true` | Hai giá trị hằng logic của kiểu `bool` |
| `fn` | Khai báo hàm hoặc kiểu con trỏ hàm (`fn(i32) -> i32`) |
| `for` | Vòng lặp duyệt qua iterator, cài đặt trait (`impl Trait for Type`), hoặc `for<'a>` |
| `if` | Biểu thức rẽ nhánh điều kiện |
| `impl` | Khối triển khai phương thức tự thân hoặc cài đặt trait cho một kiểu |
| `in` | Nằm trong cú pháp vòng lặp `for item in iterator` |
| `let` | Khai báo và ràng buộc giá trị cho một biến |
| `loop` | Vòng lặp vô hạn |
| `match` | Biểu thức so khớp mẫu đối sánh toàn diện |
| `mod` | Khai báo hoặc định nghĩa một module |
| `move` | Buộc closure hoặc khối async chiếm quyền sở hữu các biến bị bắt từ môi trường |
| `mut` | Biểu thị tính khả biến cho biến, tham chiếu hoặc con trỏ |
| `pub` | Công khai quyền truy cập cho module bên ngoài (`pub`, `pub(crate)`, `pub(super)`) |
| `ref` | Mượn tham chiếu tới giá trị bên trong mẫu pattern matching |
| `return` | Thoát sớm khỏi hàm và trả về giá trị |
| `Self` / `self` | `Self` là bí danh kiểu đang triển khai; `self` là đối tượng hiện tại của phương thức |
| `static` | Biến toàn cục hoặc vòng đời tồn tại suốt thời gian chạy chương trình (`'static`) |
| `struct` | Định nghĩa cấu trúc dữ liệu tùy chỉnh |
| `super` | Tham chiếu đến module cha của module hiện tại |
| `trait` | Định nghĩa một tập hợp các hành vi trừu tượng |
| `type` | Định nghĩa bí danh kiểu (*type alias*) hoặc kiểu liên kết (*associated type*) |
| `union` | Khai báo kiểu hợp nhất; cần `#[repr(C)]` nếu yêu cầu bố cục tương thích C |
| `unsafe` | Đánh dấu thao tác hoặc hợp đồng an toàn phải được người viết kiểm chứng |
| `use` | Đưa các đường dẫn bên ngoài vào phạm vi hiện tại |
| `where` | Mệnh đề ràng buộc trait Bound ở cuối chữ ký hàm/khối `impl` |
| `while` | Vòng lặp có điều kiện |

`union` là từ khóa yếu: nó có nghĩa đặc biệt trong ngữ cảnh khai báo union. `macro_rules`, `raw` và `safe` cũng có ý nghĩa đặc biệt trong các ngữ cảnh tương ứng; chẳng hạn `safe` dùng cho mục trong khối `unsafe extern`. Không coi mọi từ này là từ khóa cấm dùng ở mọi vị trí.

#### 2. Từ khóa dự phòng (reserved keywords) và định danh thô (`r#`)

- **Từ khóa dự phòng:** `abstract`, `become`, `box`, `do`, `final`, **`gen`** *(mới từ Rust 2024)*, `macro`, `override`, `priv`, `try`, `typeof`, `unsized`, `virtual`, `yield`.
- **Định danh thô (`Raw Identifiers r#`):** Cho phép sử dụng từ khóa làm tên biến hoặc tên hàm (rất hữu ích khi tích hợp với thư viện ngoài hoặc JSON có trường tên `match` hay `type`):
  ```rust
  let r#match = "giá trị hợp lệ";
  ```

---

Định danh thô không áp dụng cho `crate`, `self`, `Self`, `super` hoặc `_`. Danh mục và phân loại chi tiết: [Rust Reference — Keywords](https://doc.rust-lang.org/reference/keywords.html).

<a id="phu-luc-b"></a>

### Phụ lục B. Toán tử và ký hiệu cú pháp

|  Ký hiệu |  Ý nghĩa trong ngữ cảnh Rust |
| :--- | :--- |
| `!` | Gọi macro (`println!`, `vec!`), toán tử phủ định logic NOT, hoặc kiểu Never Type (`!`) |
| `?` | Toán tử lan truyền lỗi sớm trong hàm trả về `Result` hoặc `Option` |
| `&` / `&mut` | Mượn tham chiếu bất biến (`&T`) / Mượn tham chiếu khả biến độc quyền (`&mut T`) |
| `&raw const` / `&raw mut` | Tạo con trỏ thô an toàn không qua tham chiếu trung gian (ổn định từ Rust 1.82) |
| `*` | Toán tử giải tham chiếu (*Dereference*), phép nhân, hoặc khai báo con trỏ thô (`*const T`) |
| `::` | Toán tử phân giải đường dẫn module, biến thể enum hoặc hàm liên kết (`Vec::new()`) |
| `->` | Khai báo kiểu trả về của hàm hoặc closure |
| `=>` | Tách mẫu đối sánh và biểu thức thực thi trong nhánh `match` |
| `..` / `..=` | Dải số nửa mở `a..b` ($[a, b)$) / Dải số đóng `a..=b` ($[a, b]$), hoặc cập nhật/bỏ qua phần tử |
| `@` | Ràng buộc giá trị vào biến khi đang kiểm tra khớp mẫu trong `match` |
| `'a` | Ký hiệu tham số vòng đời (*Lifetime*) hoặc nhãn vòng lặp (`'outer: loop`) |
| `_` | Mẫu giữ chỗ bỏ qua giá trị (*Wildcard pattern*) hoặc dấu phân cách số `1_000_000` |

---

Các toán tử phổ biến khác:

| Nhóm | Ký hiệu |
| :--- | :--- |
| Số học | `+`, `-`, `*`, `/`, `%` |
| So sánh | `==`, `!=`, `<`, `>`, `<=`, `>=` |
| Logic ngắn mạch | `&&`, `\|\|` |
| Bit | `&`, `\|`, `^`, `!`, `<<`, `>>` |
| Gán và gán kết hợp | `=`, `+=`, `-=`, `*=`, `/=`, `%=` và các dạng gán bit |
| Truy cập và gọi | `.`, `[]`, `()` |
| Closure và mẫu thay thế | `\|x\| x + 1`, `A \| B` |

Không nhầm `&&` với `&`: một toán tử logic ngắn mạch, toán tử còn lại phụ thuộc ngữ cảnh mượn hoặc xử lý bit. Số nguyên chia cho số nguyên vẫn cho kết quả nguyên, làm tròn về phía 0. Dùng ngoặc để làm rõ thứ tự tính khi biểu thức có nhiều nhóm toán tử.

<a id="phu-luc-c"></a>

### Phụ lục C. Các trait có thể dẫn xuất

`#[derive(...)]` sinh triển khai trait theo quy tắc xác định. Việc derive chỉ thành công khi kiểu và các trường thỏa những điều kiện cần thiết.

| Trait | Hành vi và điều kiện chính |
| :--- | :--- |
| `Debug` | Định dạng chẩn đoán bằng `{:?}` hoặc `{:#?}`; không phải định dạng dữ liệu ổn định |
| `Clone` | Gọi `clone` của từng trường; không bảo đảm sao chép sâu, ví dụ trường `Rc` vẫn chia sẻ dữ liệu |
| `Copy` | Cho phép sao chép ngầm định; mọi trường phải có `Copy`, kiểu phải có `Clone` và không được có `Drop` |
| `PartialEq`, `Eq` | So sánh bằng/khác; `Eq` cam kết tính phản xạ. `f32`/`f64` không có `Eq` vì `NaN != NaN` |
| `PartialOrd`, `Ord` | So sánh thứ tự từng trường; `Ord` yêu cầu thứ tự toàn phần, không phải mọi kiểu có `PartialOrd` đều có `Ord` |
| `Hash` | Băm các trường; giá trị bằng nhau theo `Eq` phải cho kết quả băm tương thích |
| `Default` | Tạo giá trị từ mặc định của các trường. Với enum, derive cần đánh dấu một biến thể đơn vị bằng `#[default]` |

Ví dụ:

```rust
#[derive(Debug, Clone, Copy, PartialEq, Eq, Hash, Default)]
struct Point {
    x: i32,
    y: i32,
}

#[derive(Debug, Default)]
enum Status {
    #[default]
    Idle,
    Working,
}

fn main() {
    assert_eq!(Point::default(), Point { x: 0, y: 0 });
    println!("{:?}", Status::default());
}
```

`Display` không có derive mặc định trong thư viện chuẩn vì cách trình bày cho người dùng phụ thuộc nghiệp vụ. `Send` và `Sync` là auto trait được suy ra theo cấu trúc kiểu và các quy tắc an toàn, không thêm bằng `#[derive(Send, Sync)]`.

---

<a id="phu-luc-d"></a>

### Phụ lục D. Công cụ phát triển và hệ sinh thái crate

#### 1. Công cụ phát triển

| Công cụ | Mục đích |
| :--- | :--- |
| `cargo fmt` | Định dạng mã bằng rustfmt |
| `cargo clippy` | Phân tích tĩnh và gợi ý sửa các mẫu mã dễ gây lỗi hoặc chưa rõ ràng |
| `rust-analyzer` | Máy chủ ngôn ngữ cho trình soạn thảo hỗ trợ LSP |
| `cargo-audit` | Đối chiếu phụ thuộc với cơ sở dữ liệu cảnh báo RustSec; không phải đánh giá bảo mật toàn diện |
| `cargo-expand` | Xem mã sau khi mở rộng macro; không thuộc bộ lệnh Cargo lõi |
| Miri | Thông dịch MIR để phát hiện nhiều dạng hành vi không xác định trên những đường thực thi được chạy |

Miri không chứng minh chương trình không có lỗi, không hỗ trợ mọi FFI và không thay thế kiểm thử thông thường. Xem [tài liệu Miri](https://github.com/rust-lang/miri).

```bash
rustup component add rustfmt clippy
cargo fmt --all -- --check
cargo clippy --all-targets
cargo test

# Miri dùng toolchain nightly có cung cấp component tương ứng.
rustup +nightly component add miri
cargo +nightly miri test
```

#### 2. Các crate thường gặp

| Nhu cầu | Crate | Vai trò |
| :--- | :--- | :--- |
| Tuần tự hóa | `serde`, `serde_json` | Serde cung cấp mô hình; serde_json xử lý định dạng JSON. Định dạng khác cần crate tương ứng |
| Runtime async | `tokio` | Lập lịch task, I/O mạng, thời gian và đồng bộ hóa bất đồng bộ |
| Lỗi thư viện, ứng dụng | `thiserror`, `anyhow` | Hỗ trợ định nghĩa lỗi cụ thể hoặc bổ sung ngữ cảnh lỗi ở ứng dụng |
| Dòng lệnh | `clap` | Phân tích đối số và tạo trợ giúp |
| Web, gRPC | `axum`, `actix-web`, `tonic` | Xây dựng dịch vụ HTTP hoặc gRPC tùy thư viện |
| Cơ sở dữ liệu | `sqlx`, `sea-orm` | SQLx cung cấp truy vấn SQL; SeaORM cung cấp lớp ORM. Các macro truy vấn SQLx có thể kiểm tra truy vấn khi biên dịch với metadata/schema phù hợp; không phải mọi truy vấn của cả hai thư viện đều được kiểm tra như vậy |
| Song song dữ liệu | `rayon` | Parallel iterator và pool xử lý tính toán; cần kiểm tra chi phí chia việc |
| Quan sát ứng dụng | `tracing` | Sự kiện và span có cấu trúc; xuất dữ liệu hoặc theo dõi phân tán cần cấu hình bổ sung |

Danh sách là điểm bắt đầu để tìm hiểu, không phải xếp hạng. Trước khi chọn phụ thuộc, đọc tài liệu phiên bản định dùng, features, yêu cầu Rust tối thiểu, giấy phép và lịch sử bảo trì. Với dự án có `Cargo.lock`, có thể dùng `cargo test --locked` để phát hiện việc cần thay đổi kết quả phân giải.

---

<a id="phu-luc-e"></a>

### Phụ lục E. Rust editions và chuyển đổi dự án

Edition là tập quy tắc tương thích của ngôn ngữ, được chọn riêng cho từng package bằng `edition` trong `Cargo.toml`. Các crate ở edition khác nhau vẫn có thể phụ thuộc nhau. Phiên bản trình biên dịch mới thường hỗ trợ nhiều edition cũ; edition mới không có nghĩa mọi tính năng phát hành cùng thời điểm chỉ dùng được ở edition đó.

| Edition | Mốc trình biên dịch hỗ trợ ban đầu |
| :--- | :--- |
| 2015 | Rust 1.0 |
| 2018 | Rust 1.31 |
| 2021 | Rust 1.56 |
| 2024 | Rust 1.85.0, phát hành ngày 20/02/2025 |

#### 1. Một số thay đổi riêng của edition 2024

- Quy tắc bắt giữ của return-position `impl Trait` mở rộng đối với các tham số generic trong phạm vi; `use<...>` cho phép điều khiển chính xác trong những ngữ cảnh được hỗ trợ.
- Khối ngoại ngữ cần `unsafe extern`; các thuộc tính như `no_mangle` cần dạng `#[unsafe(no_mangle)]`. Lint `unsafe_op_in_unsafe_fn` cảnh báo mặc định, còn `static_mut_refs` từ chối mặc định.
- `std::env::set_var`, `std::env::remove_var` và phương thức `before_exec` của `std::os::unix::process::CommandExt` trở thành unsafe trong edition này.
- Bảo lưu từ khóa `gen`; bổ sung `Future` và `IntoFuture` vào prelude.
- Điều chỉnh phạm vi hủy temporary của `if let` và biểu thức cuối khối; thắt chặt một số mẫu phụ thuộc match ergonomics; thay đổi cách matcher `expr` của macro nhận các biểu thức mới.

Đây là các điểm cần chú ý, không phải danh sách đầy đủ. Tham khảo [Rust 2024 Edition Guide](https://doc.rust-lang.org/edition-guide/rust-2024/index.html).

#### 2. Phân biệt mốc ổn định tính năng với edition

| Tính năng | Mốc ổn định | Ghi chú |
| :--- | :--- | :--- |
| `OnceLock` | Rust 1.70 | Không phải tính năng chỉ có ở Edition 2024 |
| `async fn` trong trait | Rust 1.75 | Cần chú ý dyn compatibility và ràng buộc của future |
| `LazyLock` | Rust 1.80 | Khởi tạo lười có đồng bộ hóa |
| `&raw const`, `&raw mut` | Rust 1.82 | Tạo con trỏ thô mà không qua tham chiếu trung gian |
| Async closure và `AsyncFn*` | Rust 1.85 | Phát hành cùng Rust 2024 nhưng không chỉ giới hạn trong edition đó |

#### 3. Quy trình chuyển dự án từ edition 2021 sang 2024

Trước hết lưu hoặc commit trạng thái đang làm việc và bảo đảm dự án đang biên dịch được. Khi manifest vẫn ghi edition cũ, chạy:

```bash
cargo fix --edition --all-targets
```

Đọc lại thay đổi, rồi sửa `edition = "2024"` trong các manifest cần chuyển. Nếu là virtual workspace, kiểm tra `resolver = "3"` ở gốc. Sau đó chạy:

```bash
cargo check --all-targets
cargo test
cargo fmt --all -- --check
```

Kiểm tra thêm các tổ hợp features và target thực sự được dự án hỗ trợ. `cargo fix` không tự chứng minh tính an toàn của FFI, mã unsafe hoặc mọi thay đổi thứ tự hủy; những phần này cần rà soát riêng. Với edition cũ hơn, nên chuyển tuần tự theo hướng dẫn của từng edition.

---

<a id="phu-luc-f"></a>

### Phụ lục F. Quy ước đặt tên

|  Thực thể mã nguồn |  Quy ước đặt tên |  Ví dụ chuẩn |
| :--- | :--- | :--- |
| **Package / crate** | Tên package có thể dùng gạch nối; tên crate trong mã dùng dấu gạch dưới | Package `my-tool` thường được tham chiếu là `my_tool` |
|  **Modules & Tệp `.rs`** | `snake_case` | `front_of_house`, `network_io.rs` |
|  **Types (Struct, Enum, Trait)**| `UpperCamelCase` (`PascalCase`) | `Rectangle`, `Option`, `Summary` |
|  **enum Variants** | `UpperCamelCase` (`PascalCase`) | `Ok`, `Err`, `Some`, `None` |
|  **Functions & Methods** | `snake_case` | `add_one`, `calculate_length` |
|  **Local Variables & Params** | `snake_case` | `secret_number`, `user_input` |
|  **Constants & Statics** | `SCREAMING_SNAKE_CASE` | `MAX_POINTS`, `THREE_HOURS_IN_SECONDS` |
|  **Type Parameters (Generics)** | Chữ in hoa ngắn gọn (`UpperCamelCase`) | `T`, `U`, `Item`, `Key`, `Error` |
| **Tham số lifetime** | Chữ thường ngắn có dấu nháy đơn | `'a`, `'b`, `'de`; `'static` là vòng đời đặc biệt, không phải tên tùy chọn |

---

<a id="phu-luc-g"></a>

### Phụ lục G. Thuật ngữ và nguyên tắc thực hành

#### 1. Thuật ngữ anh–việt

| Thuật ngữ | Cách hiểu trong sách |
| :--- | :--- |
| Ownership | Quyền sở hữu; trách nhiệm quản lý giá trị và tài nguyên |
| Borrowing | Mượn dữ liệu qua tham chiếu chia sẻ hoặc độc quyền |
| Borrow checker | Bộ kiểm tra quan hệ mượn và vòng đời ở lúc biên dịch |
| Lifetime | Khoảng hiệu lực mà tham chiếu phải đáp ứng |
| Move | Chuyển một giá trị không có `Copy` sang vị trí mới; vị trí nguồn không còn dùng như trước |
| Dangling reference/pointer | Tham chiếu/con trỏ không còn trỏ tới dữ liệu hợp lệ |
| Data race | Truy cập xung đột giữa các luồng, có ít nhất một phép ghi, thiếu đồng bộ phù hợp và có truy cập không nguyên tử |
| Race condition | Kết quả logic phụ thuộc thứ tự tương tác không được kiểm soát; rộng hơn data race |
| Zero-cost abstraction | Trừu tượng hóa không đòi thêm chi phí so với cách triển khai cấp thấp tương đương; không có nghĩa chương trình không tốn tài nguyên |
| Monomorphization | Đơn hình hóa mã generic theo kiểu cụ thể |
| Trait | Hợp đồng hành vi gồm các mục như phương thức, kiểu hoặc hằng liên kết |
| trait object | Giá trị dùng qua `dyn Trait`, hỗ trợ phân phối động |
| Smart pointer | Kiểu quản lý dữ liệu với giao diện giống con trỏ |
| Interior mutability | Khả biến nội tại: sửa dữ liệu qua API nhận tham chiếu chia sẻ, với các quy tắc an toàn bổ sung |
| RAII | Gắn thời gian giữ tài nguyên với vòng đời đối tượng |
| Soundness | Tính đúng đắn về an toàn: API safe không cho phép gây hành vi không xác định khi được dùng đúng các quy tắc Safe Rust |
| Undefined behavior (UB) | Hành vi không xác định, khiến các giả định bảo đảm của ngôn ngữ không còn áp dụng |
| Concurrency / parallelism | Đồng thời / song song |
| Panic | Cơ chế báo lỗi khiến luồng tháo ngăn xếp hoặc tiến trình abort theo cấu hình |

#### 2. Mười nguyên tắc thực hành

1. Đọc kỹ thông báo lỗi và xem nó chỉ ra ràng buộc nào. Borrow checker có thể từ chối một thiết kế an toàn nhưng chưa được biểu đạt theo cách nó chứng minh được; hãy làm rõ quyền sở hữu.
2. Dùng `let` làm mặc định; thêm `mut` khi cần gán lại hoặc sửa dữ liệu trực tiếp.
3. Ưu tiên mượn khi hàm chỉ cần đọc; dùng `clone` khi quyền sở hữu độc lập là lựa chọn phù hợp, thay vì áp dụng hoặc né tránh nó một cách máy móc.
4. Thiết kế chủ sở hữu rõ ràng. Với đồ thị, cân nhắc chỉ mục, arena hoặc `Rc`/`Arc` kết hợp `Weak`.
5. Dùng `Option`, `Result` và `?` để diễn tả các trường hợp dự kiến. Chỉ dùng `unwrap`/`expect` khi đã hiểu và có thể giải thích điều kiện thành công.
6. Dùng newtype và typestate để đưa những bất biến phù hợp vào hệ thống kiểu; kiểm tra lúc chạy những quy tắc không thể xác định tĩnh.
7. Viết iterator hoặc vòng lặp theo cách rõ ràng, rồi đo hiệu năng khi có yêu cầu cụ thể.
8. Tách logic có thể kiểm thử khỏi I/O và điểm vào ứng dụng. Chọn cấu trúc module phù hợp quy mô, không ép mọi dự án nhỏ thành quá nhiều lớp.
9. Chọn mô hình đồng thời theo công việc: async cho nhiều thao tác chờ, luồng/pool tính toán cho CPU; giới hạn hàng đợi và giữ phạm vi khóa ngắn.
10. Giảm phạm vi `unsafe`, mô tả đầy đủ điều kiện an toàn và kiểm tra phần triển khai. Chỉ cung cấp API safe khi mọi nghĩa vụ an toàn đã được bảo đảm bên trong.

---

<a id="tai-lieu-tham-khao"></a>

## Tài liệu tham khảo

Các nguồn dưới đây phục vụ đối chiếu khái niệm, API và thay đổi phiên bản. Với thông tin phụ thuộc phiên bản, ưu tiên tài liệu đúng phiên bản mà dự án sử dụng.

1. [The Rust Programming Language](https://doc.rust-lang.org/book/) — nền tảng ngôn ngữ và các mô hình thực hành.
2. [The Rust Reference](https://doc.rust-lang.org/reference/) — quy tắc ngôn ngữ, trait, unsafe và FFI.
3. [The Rust Standard Library](https://doc.rust-lang.org/std/) — hợp đồng và đặc điểm của các API chuẩn.
4. [The Cargo Book](https://doc.rust-lang.org/cargo/) — manifest, workspace, phụ thuộc, profile và kiểm thử.
5. [The Rust Edition Guide](https://doc.rust-lang.org/edition-guide/) — thay đổi giữa các edition và hướng dẫn chuyển đổi.
6. [Google Comprehensive Rust](https://google.github.io/comprehensive-rust/) — khóa học thực hành từ nền tảng đến các chủ đề chuyên sâu.
7. [Rust Course](https://course.rs/) — nguồn học bổ sung được giới thiệu trong bản thảo gốc.
8. [The Rust Rand Book: cập nhật lên 0.9](https://rust-random.github.io/book/update-0.9.html) — các đổi tên API dùng trong dự án đoán số.
9. [Tokio tutorial](https://tokio.rs/tokio/tutorial) — runtime, task, kênh và hủy tác vụ.
10. [Miri](https://github.com/rust-lang/miri) — phạm vi và cách sử dụng công cụ kiểm tra hành vi không xác định.
11. [OnceLock](https://doc.rust-lang.org/std/sync/struct.OnceLock.html) và [LazyLock](https://doc.rust-lang.org/std/sync/struct.LazyLock.html) — điều kiện sử dụng và mốc ổn định API.

**Phạm vi kiểm tra bản hiệu đính:** Đã rà soát nội dung, đối chiếu các điểm kỹ thuật dễ nhầm với nguồn chính thức và kiểm tra cấu trúc Markdown, liên kết nội bộ, cấu hình TOML. Môi trường biên tập không có `rustc`/`cargo`, vì vậy chưa biên dịch và chạy trực tiếp toàn bộ ví dụ. Các lệnh cùng kết quả mong đợi trong từng dự án là hướng dẫn kiểm chứng, không phải báo cáo đã chạy thành công.

---

## Liên hệ và đóng góp

Giáo trình do **Thái Việt** biên soạn. Khi báo lỗi, vui lòng nêu chương/mục, phiên bản `rustc`, edition, mã tái hiện và thông báo lỗi đầy đủ.

- **Email:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)
- **GitHub:** [github.com/ozsx](https://github.com/ozsx)
