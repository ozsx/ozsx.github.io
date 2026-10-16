# 🦀 RUST TOÀN TẬP V2 🚀
*📚 Tài liệu học tập lập trình Rust toàn diện, trực quan và chuẩn mực bằng Tiếng Việt*  

---

> ### 👨‍💻 THÔNG TIN TÁC GIẢ & BIÊN SOẠN
> - **✍️ Tác giả:** **Thái Việt**
> - **📧 Email:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)
> - **🐙 GitHub:** [github.com/ozsx](https://github.com/ozsx)
> - **🔖 Phiên bản:** 2024

---

## 🌟 LỜI NÓI ĐẦU: TẠI SAO BẠN NÊN HỌC RUST TRONG KỶ NGUYÊN HIỆN ĐẠI?

Trong suốt hơn $40$ năm qua, thế giới lập trình luôn tồn tại một sự đánh đổi cay đắng giữa hai thái cực:

1. **⚡ Hiệu năng và quyền kiểm soát cấp thấp (C/C++):** Tốc độ thực thi tối đa, kiểm soát trực tiếp phần cứng và bộ nhớ, nhưng lập trình viên phải đối mặt với "cơn ác mộng" về an toàn bộ nhớ: *dangling pointers* (con trỏ lơ lửng), *double free* (giải phóng bộ nhớ hai lần), *buffer overflow* (tràn bộ đệm), và *data races* (xung đột dữ liệu đa luồng). Hơn $70\%$ các lỗ hổng bảo mật nghiêm trọng trong các hệ điều hành lớn (như Windows, Linux kernel, Android, Chromium) đều bắt nguồn từ lỗi quản lý bộ nhớ trong C/C++.
2. **🛡️ Tính an toàn và tiện dụng (Java, Go, Python, C#):** Bộ thu gom rác (*Garbage Collector - GC*) tự động dọn dẹp bộ nhớ giúp tránh được lỗi bộ nhớ kinh điển, nhưng phải trả giá bằng việc tiêu tốn RAM, độ trễ dừng thế giới (*Stop-The-World latency*), và mất đi khả năng kiểm soát phần cứng chi tiết.

**🦀 Rust ra đời để phá vỡ hoàn toàn sự đánh đổi đó!**  
Được khởi xướng bởi Graydon Hoare tại Mozilla và phát triển bởi cộng đồng mã nguồn mở toàn cầu, Rust mang lại 3 trụ cột cốt lõi:
- **💎 Zero-Cost Abstractions (Trừu tượng hóa không tốn phí):** Bạn có thể viết mã nguồn cấp cao, giàu tính biểu đạt (functional programming, generics, pattern matching) nhưng khi biên dịch, trình biên dịch `rustc` sẽ tối ưu hóa thành mã máy có tốc độ ngang ngửa với C/C++ viết tay tỉ mỉ.
- **🔒 Memory Safety Without GC (An toàn bộ nhớ không cần bộ thu gom rác):** Thông qua hệ thống **Quyền sở hữu (Ownership)** và **Bộ kiểm tra mượn (Borrow Checker)** độc nhất vô nhị, Rust phát hiện và ngăn chặn $100\%$ lỗi bộ nhớ ngay trong quá trình biên dịch (*compile-time*).
- **🧵 Fearless Concurrency (Đồng thời không sợ hãi):** Các quy tắc an toàn bộ nhớ của Rust áp dụng trực tiếp cho môi trường đa luồng, triệt tiêu hoàn toàn lỗi xung đột dữ liệu đa luồng (*data races*) trước khi chương trình được phép chạy.

Giáo trình này được biên soạn bởi **Thái Việt** (`ozsx`), lấy cảm hứng từ cấu trúc sư phạm trực quan, tỉ mỉ, "mượt mà như lụa" của **Rust Course (Rust 语言圣经)**, kết hợp cùng tài liệu chuẩn mực *The Rust Programming Language* của Rust Team và khóa đào tạo chuyên sâu *Google Comprehensive Rust*.

---

## 🗺️ MỤC LỤC TỔNG QUAN

- **🏁 PHẦN I: KHỞI ĐỘNG & NỀN TẢNG TRIẾT LÝ RUST**
  - [Chương 1: 🛠️ Bắt đầu với Rust & Hệ sinh thái Cargo](#chương-1-️-bắt-đầu-với-rust--hệ-sinh-thái-cargo)
  - [Chương 2: 🎲 Dự án 1 — Trò chơi Đoán số (Guessing Game)](#chương-2--dự-án-1--trò-chơi-đoán-số-guessing-game)
- **🧱 PHẦN II: NHẬP MÔN CĂN BẢN**
  - [Chương 3: 📦 Biến, Tính khả biến & Phạm vi (Scope)](#chương-3--biến-tính-khả-biến--phạm-vi-scope)
  - [Chương 4: 🔢 Kiểu dữ liệu cơ bản, Hàm & Luồng điều khiển](#chương-4--kiểu-dữ-liệu-cơ-bản-hàm--luồng-điều-khiển)
- **❤️ PHẦN III: TRÁI TIM CỦA RUST — QUYỀN SỞ HỮU & MƯỢN**
  - [Chương 5: 🔑 Hệ thống Quyền sở hữu (Ownership) & Mượn (Borrowing)](#chương-5--hệ-thống-quyền-sở-hữu-ownership--mượn-borrowing)
- **🧩 PHẦN IV: KIỂU PHỨC HỢP & KHỚP MẪU**
  - [Chương 6: 🔤 Chuỗi ký tự chuyên sâu (String & &str)](#chương-6--chuỗi-ký-tự-chuyên-sâu-string--str)
  - [Chương 7: 🏗️ Kiểu dữ liệu tùy chỉnh: Structs & Enums](#chương-7-️-kiểu-dữ-liệu-tùy-chỉnh-structs--enums)
  - [Chương 8: 🎯 Nghệ thuật Khớp mẫu (Pattern Matching)](#chương-8--nghệ-thuật-khớp-mẫu-pattern-matching)
- **⚙️ PHẦN V: PHƯƠNG THỨC, GENERICS & TRAITS**
  - [Chương 9: 🔧 Phương thức & Khối Triển khai (impl Methods)](#chương-9--phương-thức--khối-triển-khai-impl-methods)
  - [Chương 10: 🧬 Kiểu Chung (Generics) & Đặc tính (Traits)](#chương-10--kiểu-chung-generics--đặc-tính-traits)
- **🗂️ PHẦN VI: TẬP HỢP DỮ LIỆU, CHUYỂN ĐỔI KIỂU & XỬ LÝ LỖI**
  - [Chương 11: 📚 Các Cấu trúc Dữ liệu Tập hợp (Collections)](#chương-11--các-cấu-trúc-dữ-liệu-tập-hợp-collections)
  - [Chương 12: 🔄 Chuyển đổi Kiểu dữ liệu (Type Conversions)](#chương-12--chuyển-đổi-kiểu-dữ-liệu-type-conversions)
  - [Chương 13: 🛡️ Chiến lược Xử lý Lỗi (Error Handling)](#chương-13-️-chiến-lược-xử-lý-lỗi-error-handling)
- **🏛️ PHẦN VII: TỔ CHỨC DỰ ÁN, KIỂM THỬ & DỰ ÁN MINIGREP**
  - [Chương 14: 📁 Quản lý Dự án với Packages, Crates, Modules & Workspaces](#chương-14--quản-lý-dự-án-với-packages-crates-modules--workspaces)
  - [Chương 15: 🧪 Kiểm thử Tự động (Automated Testing) & Tài liệu hóa](#chương-15--kiểm-thử-tự-động-automated-testing--tài-liệu-hóa)
  - [Chương 16: 🔍 Dự án 2 — Xây dựng Công cụ Dòng lệnh minigrep](#chương-16--dự-án-2--xây-dựng-công-cụ-dòng-lệnh-minigrep)
- **🧠 PHẦN VIII: VÒNG ĐỜI, LẬP TRÌNH HÀM & CON TRỎ THÔNG MINH**
  - [Chương 17: ⏳ Vòng đời Tham chiếu (Lifetimes 'a)](#chương-17--vòng-đời-tham-chiếu-lifetimes-a)
  - [Chương 18: 🔁 Lập trình Hàm: Closures & Iterators](#chương-18--lập-trình-hàm-closures--iterators)
  - [Chương 19: 🧭 Con trỏ Thông minh (Smart Pointers)](#chương-19--con-trỏ-thông-minh-smart-pointers)
- **⚡ PHẦN IX: LẬP TRÌNH ĐỒNG THỜI & BẤT ĐỒNG BỘ**
  - [Chương 20: 🧵 Lập trình Đa luồng (Multi-threading Concurrency)](#chương-20--lập-trình-đa-luồng-multi-threading-concurrency)
  - [Chương 21: 🚀 Lập trình Bất đồng bộ (Async / Await)](#chương-21--lập-trình-bất-đồng-bộ-async--await)
- **🔥 PHẦN X: NÂNG CAO, MACROS & DỰ ÁN WEB SERVER**
  - [Chương 22: ⚠️ Unsafe Rust & Tương tác Cấp thấp (FFI)](#chương-22-️-unsafe-rust--tương-tác-cấp-thấp-ffi)
  - [Chương 23: 🪄 Lập trình Siêu hình với Macros (Metaprogramming)](#chương-23--lập-trình-siêu-hình-với-macros-metaprogramming)
  - [Chương 24: 🌐 Dự án 3 — Xây dựng Multithreaded Web Server Hoàn chỉnh](#chương-24--dự-án-3--xây-dựng-multithreaded-web-server-hoàn-chỉnh)
- **📖 PHẦN XI: PHỤ LỤC CẨM NANG RUSTACEAN TOÀN DIỆN**
  - [Phụ lục A: 🔑 Bảng Từ khóa & Ký hiệu Cú pháp](#phụ-lục-a--bảng-từ-khóa--ký-hiệu-cú-pháp)
  - [Phụ lục B: 🧰 Bộ Công cụ Hệ sinh thái Rust (Clippy, Rustfmt, Cargo Tools)](#phụ-lục-b--bộ-công-cụ-hệ-sinh-thái-rust-clippy-rustfmt-cargo-tools)
  - [Phụ lục C: 📏 Bảng Quy ước Đặt tên Chuẩn (Idiomatic Naming Conventions)](#phụ-lục-c--bảng-quy-ước-đặt-tên-chuẩn-idiomatic-naming-conventions)
  - [Phụ lục D: 📘 Từ điển Thuật ngữ Anh - Việt Chuyên ngành Rust](#phụ-lục-d--từ-điển-thuật-ngữ-anh---việt-chuyên-ngành-rust)
  - [Phụ lục E: 🏆 Mười Nguyên tắc Vàng Để Làm Chủ Rust](#phụ-lục-e--mười-nguyên-tắc-vàng-để-làm-chủ-rust)

---

# 🏁 PHẦN I: KHỞI ĐỘNG & NỀN TẢNG TRIẾT LÝ RUST

---

## CHƯƠNG 1: 🛠️ BẮT ĐẦU VỚI RUST & HỆ SINH THÁI CARGO

Rust không chỉ là một ngôn ngữ lập trình độc lập mà là một hệ sinh thái công cụ phát triển phần mềm hiện đại, tối ưu và kiểm soát chất lượng cực kỳ chặt chẽ. Để bắt đầu hành trình Rust, bạn cần nắm vững ba công cụ trụ cột: `rustup`, `rustc` và `cargo`.

### 1.1. 📥 Cài đặt Môi trường Rust qua `rustup`

`rustup` là công cụ chính thức quản lý các phiên bản trình biên dịch Rust và các công cụ liên quan. Nó hỗ trợ cài đặt, cập nhật, chuyển đổi linh hoạt giữa các kênh phát hành (*stable*, *beta*, *nightly*), và hỗ trợ biên dịch chéo (*cross-compilation*) cho nhiều hệ điều hành và vi xử lý khác nhau.

#### 💻 Hướng dẫn cài đặt theo từng hệ điều hành:

1. **🐧 Trên Linux hoặc 🍎 macOS:**
   Mở terminal và thực thi lệnh cài đặt từ trang chủ chính thức của ngôn ngữ Rust (`rust-lang.org`):
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
   Bộ cài sẽ tự động thiết lập biến môi trường `PATH` để bạn có thể gọi `rustc` và `cargo` từ bất kỳ đâu.
   - ⚠️ *Yêu cầu bắt buộc:* Cần có sẵn C compiler và Linker (trình liên kết mã):
     - Trên Ubuntu/Debian: `sudo apt update && sudo apt install build-essential`
     - Trên Fedora/RHEL: `sudo dnf groupinstall "Development Tools"`
     - Trên macOS: `xcode-select --install`

2. **🪟 Trên Windows:**
   Truy cập trang web chính thức của Rust, tải về và chạy bộ cài đặt `rustup-init.exe`. Trong quá trình cài đặt, làm theo hướng dẫn để cài đặt công cụ *Visual Studio C++ Build Tools* (yêu cầu gói *"Desktop development with C++"* để có sẵn MSVC Linker).

#### 🔍 Kiểm tra cài đặt và lệnh quản lý thiết yếu:

```bash
# Kiểm tra phiên bản trình biên dịch rustc
rustc --version
# Kết quả mẫu: rustc 1.97.0 (abc12345 2026-07-09)

# Kiểm tra phiên bản trình quản lý gói Cargo
cargo --version
# Kết quả mẫu: cargo 1.97.0 (abc12345 2026-07-09)

# Cập nhật Rust lên phiên bản ổn định mới nhất
rustup update

# Mở tài liệu chính thức ngoại tuyến (offline) trực tiếp trong trình duyệt
rustup doc
```

---

### 1.2. 👋 Chương trình "Hello, World!" đầu tiên

Trong Rust, tập tin mã nguồn luôn có phần mở rộng là `.rs`. Khi tên tập tin gồm nhiều từ, quy ước chuẩn của cộng đồng (*idiomatic Rust*) là sử dụng dấu gạch dưới (`snake_case`), ví dụ: `hello_world.rs` hoặc `main.rs`.

Hãy tạo một tập tin có tên `main.rs` với nội dung như sau:

```rust
// File: main.rs
// Hàm main là điểm bắt đầu (entry point) của mọi chương trình Rust thực thi
fn main() {
    println!("Hello, world! 🦀");
}
```

#### 🔬 Mổ xẻ chi tiết cú pháp:
1. **`fn main() { ... }`:** Khai báo hàm `main`. Trong Rust, từ khóa `fn` dùng để định nghĩa hàm. `main` là hàm đặc biệt nhất — điểm khởi đầu mà hệ điều hành sẽ gọi khi thực thi chương trình. Khối lệnh của thân hàm luôn nằm trong cặp ngoặc nhọn `{}`.
2. **`println!("Hello, world! 🦀");`:** In chuỗi ký tự ra màn hình kèm ký tự xuống dòng. Dấu chấm than `!` ở sau `println` là điểm cực kỳ quan trọng: **💡 đây là việc gọi một Macro, không phải một hàm thông thường!** Macros trong Rust cung cấp khả năng siêu lập trình (*metaprogramming*) tại thời điểm biên dịch, cho phép nhận số lượng tham số linh hoạt và kiểm tra định dạng chuỗi an toàn kiểu dữ liệu ngay lúc biên dịch.
3. **Dấu chấm phẩy `;`:** Đánh dấu sự kết thúc của một câu lệnh (*statement*). Hầu hết các dòng lệnh thực thi trong Rust đều kết thúc bằng `;`.

#### ⚙️ Quy trình Biên dịch và Chạy:
Rust là ngôn ngữ biên dịch trước (**Ahead-Of-Time compiled**). Bạn dùng trình biên dịch `rustc` để dịch trực tiếp mã nguồn thành tập tin nhị phân thực thi độc lập:

```bash
# Biên dịch file main.rs
rustc main.rs

# Chạy tập tin nhị phân vừa sinh ra
# Trên Linux/macOS:
./main

# Trên Windows:
.\main.exe
```
Kết quả hiển thị trên màn hình:
```text
Hello, world! 🦀
```

---

### 1.3. 📦 Hệ thống Quản lý Dự án Cargo

Trong các dự án thực tế, mã nguồn sẽ phân tán trên nhiều tập tin và tích hợp hàng chục thư viện ngoài (trong Rust gọi là **crates**). Bạn sẽ không gọi `rustc` trực tiếp mà luôn sử dụng **Cargo** — trình quản lý gói và hệ sinh thái build chính thức của Rust.

#### 🚀 Tạo dự án mới với Cargo:

```bash
# Tạo một dự án ứng dụng thực thi (binary project)
cargo new hello_cargo
cd hello_cargo
```

Cấu trúc thư mục chuẩn được sinh ra:
```text
hello_cargo/
├── .git/            # Kho lưu trữ Git được khởi tạo tự động
├── .gitignore       # Tập tin bỏ qua thư mục build target/
├── Cargo.toml       # Tập tin cấu hình metadata và thư viện phụ thuộc
└── src/
    └── main.rs      # Tập tin mã nguồn chính của ứng dụng
```

#### 📝 Khám phá tập tin cấu hình `Cargo.toml`:
Tập tin này viết bằng định dạng TOML (*Tom's Obvious, Minimal Language*):

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2024"
authors = ["Thái Việt <ozsxe@icloud.com>"]

# Danh sách các thư viện ngoài (crates) dự án cần dùng
[dependencies]
```

- **`[package]`:** Khối thông tin cấu hình gói (tên, phiên bản theo Semantic Versioning `MAJOR.MINOR.PATCH`, và phiên bản chuẩn ngôn ngữ `edition = "2024"`).
- **`[dependencies]`:** Nơi liệt kê các thư viện ngoài. Khi bạn thêm một crate vào đây, Cargo sẽ tự động tải về từ `crates.io`, kiểm tra checksum, biên dịch và liên kết vào dự án của bạn.

#### 🛠️ Các lệnh Cargo thiết yếu trong công việc hàng ngày:
1. ⚡ **`cargo check`:** Kiểm tra cú pháp và kiểm tra kiểu dữ liệu cực nhanh mà không sinh mã máy thực thi. Đây là lệnh các lập trình viên Rust chạy liên tục trong quá trình code để phát hiện lỗi sớm.
2. 🔨 **`cargo build`:** Biên dịch toàn bộ dự án ở chế độ phát triển (*debug mode*). Kết quả lưu tại `target/debug/hello_cargo`. Quá trình này không tối ưu hóa tối đa tốc độ nhưng giữ lại đầy đủ thông tin gỡ lỗi (*debug symbols*).
3. ▶️ **`cargo run`:** Biên dịch (nếu có thay đổi) và chạy chương trình ngay lập tức. Rất tiện lợi khi phát triển nhanh.
4. 🚀 **`cargo build --release`:** Biên dịch phiên bản phát hành (*release mode*) với mức tối ưu hóa mã cao nhất (`opt-level = 3`), loại bỏ thông tin debug thừa. Tập tin thực thi lưu tại `target/release/hello_cargo`, đạt tốc độ tối đa để đưa lên môi trường thực tế (*production*).
5. 🔒 **`Cargo.lock`:** Tập tin ghi lại chính xác các phiên bản cụ thể (*exact versions*) và mã băm SHA256 của toàn bộ các thư viện phụ thuộc nhằm đảm bảo tính tái lập $100\%$ (*deterministic build*) trên mọi máy tính khác nhau.

---

## CHƯƠNG 2: 🎲 DỰ ÁN 1 — TRÒ CHƠI ĐOÁN SỐ (GUESSING GAME)

Để biến lý thuyết thành kỹ năng thực tế, chúng ta sẽ bắt tay vào xây dựng dự án đầu tiên: **Trò chơi Đoán số (Guessing Game)**. Đây là dự án kinh điển giúp bạn làm quen ngay với:
- ⌨️ Xử lý nhập/xuất dữ liệu từ bàn phím (`std::io`).
- 🔒 Bản chất của biến: Tính bất biến mặc định (*immutable*) và tính khả biến (`mut`).
- 📦 Tích hợp và cấu hình thư viện ngoài từ `crates.io`.
- 🎯 Khớp mẫu đối sánh mạnh mẽ (`match`) và kiểu so sánh `Ordering`.
- 🔁 Kiểm soát luồng lặp vô hạn (`loop`), thoát vòng lặp (`break`), bỏ qua vòng lặp (`continue`).
- 🛡️ Xử lý kết quả trả về an toàn với kiểu `Result` (`Ok` / `Err`).

### 2.1. 📦 Cài đặt Crate `rand` trong `Cargo.toml`

Để trò chơi có tính thử thách, máy tính cần sinh ra một số ngẫu nhiên bí mật. Thư viện chuẩn `std` của Rust không tích hợp sẵn bộ sinh số ngẫu nhiên để giữ cho thư viện chuẩn gọn nhẹ. Chúng ta sẽ sử dụng crate cộng đồng chuẩn mực nhất là `rand`.

Mở tập tin `Cargo.toml` và bổ sung dòng sau vào mục `[dependencies]`:

```toml
[dependencies]
rand = "0.8.5"
```

Khi chạy `cargo build`, Cargo sẽ kết nối đến registry trung tâm `crates.io`, tải crate `rand` cùng các crate phụ thuộc về máy và lưu vào bộ nhớ cache.

> 💡 **Lưu ý quan trọng cho Rust Edition 2024 & `rand 0.9+`:** Trong chuẩn Rust 2024, từ khóa `gen` đã trở thành từ khóa bảo lưu (*reserved keyword*). Nếu bạn giữ `rand = "0.8.5"` như trên thì dùng hàm `rand::thread_rng().gen_range(1..=100)`. Tuy nhiên, nếu bạn chạy lệnh `cargo add rand` và cài đặt bản mới `rand = "0.9"` trở lên, hãy đổi dòng sinh số ngẫu nhiên thành: `let secret_number = rand::rng().random_range(1..=100);`.

---

### 2.2. 💻 Toàn bộ Mã nguồn Dự án `src/main.rs`

Hãy mở tập tin `src/main.rs` và viết toàn bộ mã nguồn có chú thích chi tiết sau:

```rust
use std::io;                      // Đưa module I/O của thư viện chuẩn vào phạm vi
use std::cmp::Ordering;           // Đưa kiểu enum so sánh Ordering vào phạm vi
use rand::Rng;                    // Đưa Trait Rng vào phạm vi để sử dụng hàm gen_range

fn main() {
    println!("🎲 === CHÀO MỪNG ĐẾN VỚI TRÒ CHƠI ĐOÁN SỐ! === 🎲");

    // Sinh số ngẫu nhiên bí mật trong khoảng từ 1 đến 100 (bao gồm cả 1 và 100)
    // Cú pháp 1..=100 là Range Inclusive
    let secret_number = rand::thread_rng().gen_range(1..=100);

    // Vòng lặp vô hạn loop cho phép người chơi đoán nhiều lần cho đến khi trúng
    loop {
        println!("👉 Vui lòng nhập một số dự đoán (từ 1 đến 100):");

        // Biến trong Rust mặc định là bất biến (immutable).
        // Muốn giá trị của biến thay đổi được, BẮT BUỘC phải thêm từ khóa `mut`.
        // String::new() tạo ra một chuỗi rỗng có thể co giãn kích thước trên Heap.
        let mut guess = String::new();

        // Đọc dữ liệu từ bàn phím vào biến guess
        io::stdin()
            .read_line(&mut guess)
            .expect("❌ Không thể đọc dòng dữ liệu từ bàn phím!");

        // Chuyển đổi chuỗi nhập vào thành số nguyên dương 32-bit (u32).
        // Kỹ thuật Shadowing: Cho phép khai báo lại tên biến `guess` cũ để đổi kiểu dữ liệu.
        // Dùng match với Result để xử lý lỗi nhập liệu mà không làm chương trình bị crash:
        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,     // Nếu ép kiểu thành công, lấy giá trị số nguyên
            Err(_) => {         // Nếu người dùng nhập chữ hoặc ký tự không hợp lệ
                println!("⚠️ Giá trị nhập không hợp lệ, vui lòng chỉ nhập số nguyên!");
                continue;       // Bỏ qua phần còn lại của vòng lặp, yêu cầu nhập lại
            }
        };

        println!("🔍 Bạn đã đoán: {guess}");

        // So sánh số dự đoán với số bí mật bằng phương thức .cmp()
        match guess.cmp(&secret_number) {
            Ordering::Less => println!("📉 Số bạn đoán quá nhỏ!"),
            Ordering::Greater => println!("📈 Số bạn đoán quá lớn!"),
            Ordering::Equal => {
                println!("🎉 CHÍNH XÁC! Chúc mừng bạn đã chiến thắng! 🏆");
                break; // Thoát khỏi vòng lặp loop, kết thúc chương trình
            }
        }
    }
}
```

---

### 2.3. 🔬 Phân tích Chuyên sâu Từng Dòng Lệnh

#### 1️⃣ Ràng buộc biến khả biến (`let mut guess = String::new();`):
- `let` dùng để khai báo (*bind*) một biến mới.
- Mặc định trong Rust, mọi biến đều là **bất biến (immutable)**. Nếu bạn viết `let guess = String::new();`, sau đó gọi `io::stdin().read_line(&mut guess);`, trình biên dịch sẽ lập tức báo lỗi: `cannot borrow immutable local variable as mutable`.
- Việc thêm từ khóa `mut` báo hiệu cho Rust biết biến này có thể ghi đè nội dung.
- `String::new()` là một hàm liên kết (*associated function*) của kiểu `String`, trả về một chuỗi UTF-8 rỗng trên bộ nhớ Heap.

#### 2️⃣ Tham chiếu khả biến (`&mut guess`):
- Dấu `&` biểu thị đây là một **tham chiếu (reference)**. Nó cho phép hàm `read_line` đọc và ghi dữ liệu trực tiếp vào vùng nhớ của biến `guess` mà không cần lấy đi quyền sở hữu (*ownership*) của biến.
- Tương tự như biến, tham chiếu cũng mặc định là bất biến (`&guess`). Vì `read_line` cần ghi nội dung người dùng gõ vào chuỗi, ta phải truyền tham chiếu khả biến: `&mut guess`.

#### 3️⃣ Xử lý lỗi với kiểu `Result` và `.expect()`:
- Hàm `read_line` không trả về một chuỗi đơn thuần mà trả về một kiểu liệt kê `Result`. `Result` là một enum có $2$ biến thể:
  - ✅ `Ok(usize)`: Thao tác đọc thành công, kèm theo số lượng byte đã đọc.
  - ❌ `Err(std::io::Error)`: Thao tác thất bại (lỗi I/O từ hệ điều hành).
- Nếu bạn không xử lý giá trị `Result` trả về, trình biên dịch `rustc` sẽ cảnh báo (*warning*): `unused Result that must be used`.
- Phương thức `.expect("msg")` là cách xử lý đơn giản nhất: Nếu là `Ok`, nó giải nén và lấy giá trị bên trong; nếu là `Err`, chương trình sẽ ngay lập tức dừng lại (*panic*) và in ra thông báo lỗi mà bạn đã chỉ định.

#### 4️⃣ Kỹ thuật Che bóng (Shadowing) và Chuyển đổi Kiểu (`let guess: u32 = ...`):
- Khi nhập từ bàn phím, `guess` mang kiểu `String` (ví dụ `"42\n"`).
- Rust cho phép tái sử dụng tên biến `guess` thông qua từ khóa `let`. Biến `guess` mới mang kiểu số nguyên `u32` sẽ "che bóng" (*shadow*) biến `guess` dạng chuỗi ban đầu.
- Phương thức `.trim()` loại bỏ khoảng trắng và ký tự xuống dòng `\r\n`.
- Phương thức `.parse()` phân tích chuỗi thành số nguyên. Ta dùng khối `match` để xử lý kết quả trả về của `.parse()`: Nếu thành công (`Ok(num)`), gán số cho `guess`; nếu thất bại (`Err(_)`), gọi `continue` để bỏ qua lượt lặp và yêu cầu người dùng nhập lại mà không làm sập chương trình.

#### 5️⃣ Khớp mẫu đối sánh (`match guess.cmp(&secret_number)`):
- Phương thức `.cmp()` so sánh hai giá trị và trả về một biến thể của enum `std::cmp::Ordering`: `Ordering::Less`, `Ordering::Greater`, hoặc `Ordering::Equal`.
- Khối lệnh `match` trong Rust bắt buộc phải bao quát toàn bộ mọi trường hợp có thể xảy ra (*exhaustive pattern matching*). Khi đoán đúng (`Equal`), ta in lời chúc mừng và dùng từ khóa `break` để chấm dứt vòng lặp `loop`.

---

# 🧱 PHẦN II: NHẬP MÔN CĂN BẢN

---

## CHƯƠNG 3: 📦 BIẾN, TÍNH KHẢ BIẾN & PHẠM VI (SCOPE)

Trong hầu hết các ngôn ngữ lập trình truyền thống (C/C++, Python, Java, JavaScript), biến được tạo ra mặc định có thể gán lại giá trị tùy ý bất kỳ lúc nào. Tuy nhiên, trong Rust, khái niệm cốt lõi không phải là "gán biến" mà là **ràng buộc biến (Variable Binding)**, và biến mặc định luôn luôn là **bất biến (immutable)**.

### 3.1. 🔒 Ràng buộc Biến & Tính Bất biến Mặc định

> 💡 **Triết lý của Rust:** *Nếu một giá trị không cần thay đổi, đừng cho phép nó thay đổi.* Điều này giúp ngăn chặn hàng loạt lỗi logic tiềm ẩn khi dữ liệu bị thay đổi bất ngờ bởi các hàm khác hoặc trong môi trường đa luồng.

Hãy xem xét đoạn mã sau:

```rust
fn main() {
    let x = 5;
    println!("Giá trị của x là: {x}");
    x = 6; // ❌ LỖI BIÊN DỊCH!
    println!("Giá trị của x là: {x}");
}
```

Khi biên dịch đoạn mã trên bằng `cargo check` hoặc `rustc`, bạn sẽ nhận được thông báo lỗi rõ ràng từ trình biên dịch:

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

### 3.2. 🔓 Tính Khả biến với Từ khóa `mut`

Để cho phép một biến thay đổi giá trị, bạn cần thêm từ khóa `mut` (viết tắt của *mutable*) ngay sau từ khóa `let`:

```rust
fn main() {
    let mut x = 5;
    println!("Giá trị ban đầu của x: {x}");
    x = 6; // ✅ Hoàn toàn hợp lệ!
    println!("Giá trị mới của x: {x}");
}
```

Việc phải viết tường minh `mut` đóng vai trò như một lời nhắc nhở cho chính bạn và những người đọc mã nguồn sau này: *"Vùng nhớ này sẽ thay đổi giá trị trong các dòng lệnh tiếp theo."*

---

### 3.3. ⚖️ So sánh Biến Bất biến (`let`) và Hằng số (`const`)

Nhiều người mới học Rust thường nhầm lẫn giữa biến bất biến (`let x = 5;`) và hằng số (`const`). Dưới đây là bảng so sánh chi tiết:

| 📌 Đặc tính | 🔒 Biến bất biến (`let`) | 💎 Hằng số (`const`) |
| :--- | :--- | :--- |
| **Khai báo cú pháp** | `let x = 5;` | `const MAX_POINTS: u32 = 100_000;` |
| **Bắt buộc chú thích kiểu?** | Không (Rust có thể tự suy luận) | **Bắt buộc $100\%$** phải ghi rõ kiểu dữ liệu |
| **Tính khả biến (`mut`)** | Có thể thêm `mut` để thành biến khả biến | **Tuyệt đối không bao giờ** được dùng `mut` |
| **Thời điểm gán giá trị** | Thời điểm chạy (*runtime*), có thể gán từ kết quả hàm | Thời điểm biên dịch (*compile-time constant expression*) |
| **Phạm vi khai báo** | Trong thân hàm hoặc khối lệnh | Mọi phạm vi, bao gồm cả phạm vi toàn cục (*global scope*) |
| **Quy ước đặt tên** | `snake_case` (ví dụ: `user_count`) | `SCREAMING_SNAKE_CASE` (ví dụ: `MAX_BUFFER_SIZE`) |

Ví dụ khai báo hằng số:
```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

---

### 3.4. 🌑 Kỹ thuật Che bóng (Shadowing)

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

#### 💡 Phân biệt sâu sắc giữa Shadowing (`let`) và Biến khả biến (`let mut`):
1. **Shadowing tạo ra một biến hoàn toàn mới:** Biến mới vẫn mặc định là bất biến (trừ khi bạn thêm `let mut`). Sau phép tính, bạn không thể vô tình sửa đổi biến đó.
2. **Shadowing cho phép thay đổi kiểu dữ liệu (Type):** Đây là ưu điểm vượt trội giúp code ngắn gọn và trong sáng.

Xem ví dụ xử lý chuỗi:
```rust
// ✅ HỢP LỆ VỚI SHADOWING:
let spaces = "   ";          // Kiểu chuỗi &str
let spaces = spaces.len();   // Kiểu số nguyên usize (tên biến giữ nguyên tính gợi nhớ)

// ❌ LỖI NẾU DÙNG MUT:
let mut spaces = "   ";
spaces = spaces.len(); 
// LỖI BIÊN DỊCH: expected `&str`, found `usize`! Biến mut không thể đổi kiểu!
```

---

### 3.5. 🔭 Phạm vi Biến (Scope)

Phạm vi (*scope*) là khoảng không gian mã nguồn mà một biến hoặc định danh có hiệu lực. Trong Rust, scope được giới hạn bởi cặp ngoặc nhọn `{}`:

```rust
fn main() {
    // s chưa tồn tại ở đây
    {
        let s = "hello"; // s bắt đầu có hiệu lực từ dòng này
        println!("{s}"); // sử dụng s bình thường
    } // Khối lệnh kết thúc, phạm vi của s kết thúc tại đây, s bị giải phóng khỏi bộ nhớ

    // println!("{s}"); // ❌ LỖI BIÊN DỊCH: cannot find value `s` in this scope
}
```

---

## CHƯƠNG 4: 🔢 KIỂU DỮ LIỆU CƠ BẢN, HÀM & LUỒNG ĐIỀU KHIỂN

Rust là ngôn ngữ **định kiểu tĩnh (statically typed)**, nghĩa là trình biên dịch phải biết chính xác kiểu dữ liệu của mọi biến tại thời điểm biên dịch. Tuy nhiên, nhờ cơ chế **suy luận kiểu (type inference)** thông minh, bạn hiếm khi phải tự tay viết kiểu dữ liệu cho các trường hợp tường minh.

### 4.1. 🧮 Kiểu Dữ Liệu Vô Hướng (Scalar Types)

Kiểu vô hướng đại diện cho một giá trị đơn lẻ. Rust có $4$ nhóm kiểu vô hướng chính:

#### 1️⃣ Kiểu Số Nguyên (Integers):
Số nguyên là các số không có phần thập phân. Rust hỗ trợ cả số có dấu (`i` - *signed*, lưu được số âm và dương) và số không dấu (`u` - *unsigned*, chỉ lưu số không âm).

| 📏 Kích thước | ➕➖ Có dấu (Signed) | ➕ Không dấu (Unsigned) | 📊 Miền giá trị ($\text{Min} \dots \text{Max}$) |
| :--- | :--- | :--- | :--- |
| **8-bit** | `i8` | `u8` | $-2^7$ đến $2^7 - 1$ ($-128 \dots 127$) / $0$ đến $255$ |
| **16-bit** | `i16` | `u16` | $-2^{15}$ đến $2^{15} - 1$ / $0$ đến $65,535$ |
| **32-bit** | `i32` *(Mặc định)* | `u32` | $-2^{31}$ đến $2^{31} - 1$ / $0$ đến $4.29 \times 10^9$ |
| **64-bit** | `i64` | `u64` | $-2^{63}$ đến $2^{63} - 1$ ($\approx \pm 9.22 \times 10^{18}$) |
| **128-bit**| `i128` | `u128`| $-2^{127}$ đến $2^{127} - 1$ (Dùng trong mật mã học, blockchain) |
| **Arch** | `isize` | `usize` | Phụ thuộc kiến trúc CPU ($32$-bit hoặc $64$-bit). Thường dùng làm chỉ số mảng (*indexing*). |

*✨ Cách viết số nguyên trực quan:*
- Số thập phân có dấu gạch phân cách: `1_000_000` (giá trị là $1000000$).
- Số thập lục phân (Hex): `0xff`.
- Số bát phân (Octal): `0o77`.
- Số nhị phân (Binary): `0b1111_0000`.
- Byte ký tự (chỉ dành cho `u8`): `b'A'`.

*⚠️ Hiện tượng tràn số nguyên (Integer Overflow):*
Nếu bạn có một biến `u8` chứa giá trị $255$, nếu bạn cộng thêm $1$:
- Trong chế độ **Debug**: Rust kích hoạt kiểm tra tràn số và chương trình sẽ lập tức bị **panic** (dừng khẩn cấp).
- Trong chế độ **Release** (`--release`): Rust thực hiện phép quay vòng kiểu số học bù hai (*two's complement wrapping*), giá trị $255 + 1$ sẽ trở thành $0$. Bạn có thể dùng các phương thức tường minh của thư viện chuẩn như `wrapping_add`, `checked_add`, `overflowing_add`, hoặc `saturating_add` để kiểm soát hành vi tràn số an toàn $100\%$.

#### 2️⃣ Kiểu Số Thực (Floating-Point Types):
Rust có hai kiểu số thực cơ bản tuân theo chuẩn IEEE 754:
- `f32`: Số thực độ chính xác đơn (*Single precision* - $32$ bit).
- `f64`: Số thực độ chính xác kép (*Double precision* - $64$ bit). **Đây là kiểu mặc định** trên các CPU hiện đại vì tốc độ tính toán tương đương `f32` nhưng độ chính xác cao hơn vượt trội.

```rust
let x = 2.0;      // f64 (mặc định)
let y: f32 = 3.0; // f32
```

#### 3️⃣ Kiểu Logic (Boolean):
Mang một trong hai giá trị: `true` hoặc `false`. Có kích thước đúng $1$ byte trong bộ nhớ:
```rust
let t = true;
let f: bool = false; // Chú thích kiểu tường minh
```

#### 4️⃣ Kiểu Ký Tự (Character):
Kiểu `char` trong Rust có kích thước **$4$ bytes ($32$-bit)**, biểu diễn một *Unicode Scalar Value* trong dải từ $\text{U+0000}$ đến $\text{U+D7FF}$ và $\text{U+E000}$ đến $\text{U+10FFFF}$. Điều này có nghĩa là kiểu `char` của Rust có thể biểu diễn được chữ cái tiếng Việt có dấu, chữ tượng hình tiếng Trung/Nhật/Hàn, và thậm chí cả các biểu tượng Emoji!

Ký tự được đặt trong cặp nháy đơn `''` (khác với chuỗi đặt trong cặp nháy kép `""`):
```rust
let c = 'z';
let vietnamese_char = 'ệ';
let crab_emoji = '🦀';
```

#### 5️⃣ Kiểu Đơn Vị (Unit Type `()`):
Một tuple không chứa phần tử nào được viết là `()`. Nó chỉ có một giá trị duy nhất là `()` và có kích thước **$0$ byte (Zero-Sized Type - ZST)**. Mọi biểu thức không trả về giá trị cụ thể trong Rust ngầm định trả về `()`.

---

### 4.2. 🧱 Kiểu Dữ Liệu Phức Hợp Cơ Bản (Compound Types)

#### 1️⃣ Kiểu Bộ (Tuple):
Tuple là cách gom nhóm nhiều giá trị có **kiểu dữ liệu khác nhau** thành một đơn vị duy nhất. Tuple có độ dài cố định sau khi khai báo.

```rust
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);

    // Kỹ thuật giải cấu trúc (Destructuring)
    let (x, y, z) = tup;
    println!("Giá trị y là: {y}");

    // Truy cập trực tiếp qua chỉ số (Index) bằng dấu chấm:
    let five_hundred = tup.0;
    let six_point_four = tup.1;
    let one = tup.2;
}
```

#### 2️⃣ Kiểu Mảng (Array `[T; N]`):
Không giống như mảng trong JavaScript hay Python, mảng trong Rust có hai đặc điểm bất biến:
- Mọi phần tử trong mảng phải có **cùng một kiểu dữ liệu `T`**.
- Mảng có **độ dài cố định `N`** được xác định tại thời điểm biên dịch và nằm trên bộ nhớ **Stack**.

```rust
fn main() {
    // Khai báo mảng gồm 5 phần tử kiểu i32
    let a: [i32; 5] = [1, 2, 3, 4, 5];

    // Khởi tạo mảng có 5 phần tử, mỗi phần tử đều mang giá trị ban đầu là 0
    let zeros = [0; 5]; // Tương đương: [0, 0, 0, 0, 0]

    // Truy cập phần tử qua chỉ số (bắt đầu từ 0)
    let first = a[0];
    let second = a[1];

    println!("Phần tử đầu tiên: {first}");
}
```

*🛡️ An toàn kiểm tra biên giới mảng (Bounds Checking):*
Nếu bạn cố truy cập `a[10]`, trình biên dịch sẽ báo lỗi ngay nếu phát hiện được ở compile-time, hoặc chương trình sẽ **panic** khi chạy ở runtime thay vì đọc rác bộ nhớ như trong C/C++.

---

### 4.3. ⚡ Câu Lệnh (Statement) vs. Biểu Thức (Expression)

Đây là nền tảng triết lý quan trọng bậc nhất tạo nên phong cách viết code ngắn gọn của Rust:
- **📌 Câu lệnh (Statement):** Là các chỉ thị thực hiện một hành động nhưng **KHÔNG trả về giá trị**. Ví dụ: `let x = 6;`. Trong Rust, bạn không thể viết `let x = (let y = 6);` như trong C hay Python.
- **⚡ Biểu thức (Expression):** Thực hiện tính toán và **CÓ trả về giá trị**. Hầu hết mọi thứ trong Rust đều là biểu thức: các phép toán (`5 + 6`), lời gọi hàm, gọi macro, và đặc biệt là **khối lệnh `{}`**.

Một khối lệnh `{}` sẽ trả về giá trị của biểu thức cuối cùng trong nó (⚠️ chú ý: **biểu thức cuối cùng KHÔNG có dấu chấm phẩy `;`**):

```rust
fn main() {
    let y = {
        let x = 3;
        x + 1 // ✅ Biểu thức trả về giá trị 4 (KHÔNG CÓ DẤU CHẤM PHẨY Ở CUỐI!)
    };

    println!("Giá trị của y là: {y}"); // In ra 4
}
```
> ⚠️ **Lưu ý cốt tử:** Nếu bạn thêm dấu chấm phẩy `;` vào sau `x + 1;`, nó sẽ biến thành một câu lệnh và trả về kiểu đơn vị `()`, biến `y` sẽ nhận giá trị `()`!

---

### 4.4. 🔧 Định Nghĩa Hàm (Functions)

Hàm trong Rust được khai báo bằng từ khóa `fn`, tên hàm dùng quy ước `snake_case`. Mọi tham số truyền vào hàm **BẮT BUỘC phải chú thích kiểu dữ liệu tường minh**:

```rust
// Hàm nhận hai tham số và trả về số nguyên i32
fn add_numbers(a: i32, b: i32) -> i32 {
    // Trong Rust, giá trị của biểu thức cuối cùng tự động là giá trị trả về của hàm.
    // Viết `a + b` thay vì phải viết `return a + b;`
    a + b
}

fn main() {
    let sum = add_numbers(10, 20);
    println!("Tổng là: {sum}");
}
```

Bạn vẫn có thể dùng từ khóa `return` để thoát sớm khỏi hàm khi cần thiết:
```rust
fn check_even(n: i32) -> bool {
    if n % 2 == 0 {
        return true; // Thoát sớm
    }
    false // Biểu thức cuối
}
```

---

### 4.5. 🔀 Cấu Trúc Luồng Điều Khiển (Control Flow)

#### 1️⃣ Nhánh điều kiện `if`, `else if`, `else`:
Điều kiện sau `if` **bắt buộc phải là kiểu `bool`**. Rust không có khái niệm *"truthy/falsy"* như JavaScript hay Python (không thể viết `if 1 { ... }`).

```rust
fn main() {
    let number = 6;

    if number % 4 == 0 {
        println!("Số chia hết cho 4");
    } else if number % 3 == 0 {
        println!("Số chia hết cho 3");
    } else {
        println!("Số không chia hết cho 4 hoặc 3");
    }
}
```

*✨ Sử dụng `if` như một biểu thức gán giá trị:*
Vì `if` là một biểu thức, bạn có thể dùng nó trực tiếp bên phải của câu lệnh `let`. Lưu ý: Các nhánh phải trả về cùng một kiểu dữ liệu:
```rust
let condition = true;
let number = if condition { 5 } else { 6 };
```

#### 2️⃣ Vòng lặp vô hạn `loop` và Trả về giá trị từ `break`:
Từ khóa `loop` tạo ra một vòng lặp vĩnh viễn cho đến khi gặp lệnh `break`. Đặc biệt, `break` có thể mang theo một giá trị để gán ra ngoài:

```rust
fn main() {
    let mut counter = 0;

    let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2; // ✅ Thoát vòng lặp và trả về giá trị 20!
        }
    };

    println!("Kết quả tính toán: {result}"); // In ra 20
}
```

#### 3️⃣ Nhãn vòng lặp (Loop Labels):
Khi có nhiều vòng lặp lồng nhau, lệnh `break` hoặc `continue` mặc định chỉ tác động lên vòng lặp trong cùng. Để can thiệp vào vòng lặp cha bên ngoài, bạn đặt nhãn với dấu nháy đơn `'label_name:`:

```rust
fn main() {
    let mut count = 0;
    
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break; // Chỉ thoát vòng lặp bên trong
            }
            if count == 2 {
                break 'counting_up; // 🚀 Thoát hẳn vòng lặp ngoài cùng mang nhãn 'counting_up!
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("Kết thúc! Count cuối cùng: {count}");
}
```

#### 4️⃣ Vòng lặp có điều kiện `while`:
```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{number}!");
        number -= 1;
    }

    println!("🚀 PHÓNG TÊN LỬA!!!");
}
```

#### 5️⃣ Vòng lặp duyệt phần tử `for`:
Trong Rust, vòng lặp `for` là cấu trúc lặp an toàn và hiệu quả nhất, tránh hoàn toàn lỗi chỉ số mảng vượt biên (*out-of-bounds*):

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];

    // Duyệt qua từng phần tử của mảng một cách an toàn
    for element in a {
        println!("Giá trị: {element}");
    }

    // Lặp qua một khoảng số nguyên (Range) từ 1 đến 3 đảo ngược
    for number in (1..4).rev() {
        println!("{number}!");
    }
    println!("🎉 HOÀN THÀNH!");
}
```

---

# ❤️ PHẦN III: TRÁI TIM CỦA RUST — QUYỀN SỞ HỮU & MƯỢN

---

## CHƯƠNG 5: 🔑 HỆ THỐNG QUYỀN SỞ HỮU (OWNERSHIP) & MƯỢN (BORROWING)

**Quyền sở hữu (Ownership)** chính là tính năng độc nhất vô nhị làm nên thương hiệu của ngôn ngữ Rust. Nó cho phép Rust cam kết tính an toàn bộ nhớ tuyệt đối mà không cần đến bất kỳ bộ thu gom rác (*Garbage Collector*) nào chạy ngầm làm chậm hệ thống.

Để thực sự làm chủ Rust, bạn không thể chỉ học cú pháp bề mặt mà phải thấu hiểu bản chất cách Rust quản lý bộ nhớ ở tầng vật lý.

---

### 5.1. 🏛️ Ba Trường Phái Quản Lý Bộ Nhớ Trong Khoa Học Máy Tính

1. **🔧 Quản lý thủ công (C, C++):**
   Lập trình viên phải tự xin cấp phát bộ nhớ (`malloc`, `new`) và tự nhớ gọi hàm giải phóng (`free`, `delete`).
   - *✅ Ưu điểm:* Hiệu năng cao nhất, không tốn tài nguyên runtime.
   - *❌ Hiểm họa:* Con người luôn mắc sai lầm. Quên giải phóng gây **rò rỉ bộ nhớ (memory leak)**; giải phóng $2$ lần gây **double free**; tiếp tục truy cập vùng nhớ đã giải phóng gây **use-after-free** hoặc lỗi phân đoạn **Segmentation Fault**.
2. **🗑️ Bộ thu gom rác tự động (Java, Go, Python, C#, JavaScript):**
   Hệ thống có một tiến trình GC chạy ngầm, định kỳ quét toàn bộ đồ thị đối tượng để tìm các vùng nhớ không còn ai tham chiếu tới và thu hồi chúng.
   - *✅ Ưu điểm:* Tiện lợi, loại bỏ hầu hết lỗi bộ nhớ cơ bản.
   - *❌ Nhược điểm:* Tốn thêm RAM để duy trì bảng theo dõi đối tượng; gây ra các khoảng dừng ngẫu nhiên (*Stop-The-World latency*); không phù hợp cho lập trình hệ điều hành, game engine, hệ thống nhúng thời gian thực hoặc vi điều khiển.
3. **🦀 Cách tiếp cận thứ ba của Rust — Quyền sở hữu (Ownership):**
   Bộ nhớ được quản lý thông qua một hệ thống các quy tắc chặt chẽ được **kiểm tra hoàn toàn tại thời điểm biên dịch (Compile-time)**. Nếu vi phạm bất kỳ quy tắc nào, chương trình sẽ không thể biên dịch thành công. Khi chương trình chạy, **chi phí quản lý bộ nhớ bằng đúng $0$ (Zero-cost)**!

---

### 5.2. 🧠 Bản Chất Bộ Nhớ: Ngăn Xếp (Stack) vs. Đống (Heap)

Cả **Stack** và **Heap** đều là các phân vùng bộ nhớ RAM mà mã nguồn của bạn có thể sử dụng tại thời điểm chạy:

```text
+-----------------------------------+-----------------------------------+
|       📚 NGĂN XẾP (STACK)         |           🏗️ ĐỐNG (HEAP)          |
+-----------------------------------+-----------------------------------+
| - Cấu trúc Vào sau Ra trước (LIFO)| - Vùng nhớ tự do, phi cấu trúc    |
| - Kích thước DỮ LIỆU CỐ ĐỊNH      | - Kích thước DỮ LIỆU ĐỘNG         |
|   phải biết lúc biên dịch         |   có thể co giãn lúc chạy         |
| - Tốc độ truy cập CỰC KỲ NHANH    | - Cần tìm ô nhớ trống (Allocating)|
|   (chỉ việc di chuyển con trỏ CPU)|   và truy cập qua con trỏ         |
| - Tự động thu hồi khi ra khỏi hàm | - Phải có cơ chế giải phóng       |
+-----------------------------------+-----------------------------------+
```

#### 🔬 Ví dụ trực quan với kiểu `String`:
Các kiểu dữ liệu cơ bản ta học ở Chương 4 (`i32`, `f64`, `bool`, `char`, mảng cố định) đều có kích thước cố định và được lưu trực tiếp trên **Stack**.
Tuy nhiên, kiểu chuỗi ký tự `String` có thể mở rộng kích thước tùy ý (người dùng nhập văn bản dài bao nhiêu cũng được), do đó dữ liệu thực tế của nó bắt buộc phải nằm trên **Heap**.

Cấu trúc của biến `String` trong bộ nhớ:
- **Trên Stack ($24$ bytes trên CPU $64$-bit):** Gồm $3$ trường:
  1. Con trỏ `ptr` ($8$ bytes): Trỏ đến địa chỉ ô nhớ đầu tiên trên Heap.
  2. Độ dài `len` ($8$ bytes): Số byte dữ liệu hiện có trong chuỗi.
  3. Dung lượng `capacity` ($8$ bytes): Tổng số byte bộ nhớ đã được hệ điều hành cấp phát trên Heap.
- **Trên Heap:** Vùng nhớ đệm liên tục chứa các byte mã hóa UTF-8 thực tế.

Sơ đồ bộ nhớ:
```text
         STACK (Biến s1)                         HEAP
    +--------------+-------+             +---+---+---+---+---+
    |     ptr      |   o---+------------>| h | e | l | l | o |
    +--------------+-------+             +---+---+---+---+---+
    |     len      |   5   |               0   1   2   3   4
    +--------------+-------+
    |   capacity   |   5   |
    +--------------+-------+
```

---

### 5.3. 📜 Ba Quy Tắc Vàng Của Quyền Sở Hữu (Ownership Rules)

Bạn phải ghi nhớ $3$ quy tắc sau như định luật vật lý trong thế giới Rust:
1. 🥇 **Mỗi giá trị trong Rust đều có một biến làm chủ sở hữu của nó (gọi là *owner*).**
2. 🥈 **Tại một thời điểm bất kỳ, mỗi giá trị chỉ có DUY NHẤT một chủ sở hữu.**
3. 🥉 **Khi chủ sở hữu đi ra khỏi phạm vi (*scope*), giá trị đó sẽ tự động bị hủy (*dropped*) và vùng nhớ được giải phóng ngay lập tức.**

---

### 5.4. 🚚 Cơ Chế Di Chuyển (Move Semantics)

Hãy xem chuyện gì xảy ra khi ta gán biến `s1` cho `s2`:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1; // ⚡ ĐIỀU GÌ XẢY RA Ở ĐÂY?

    // println!("{s1}"); // ❌ LỖI BIÊN DỊCH!
    println!("{s2}");    // ✅ Hợp lệ!
}
```

Trong các ngôn ngữ khác:
- Trong C++ hoặc Java, phép gán trên có thể là **Shallow Copy (sao chép nông)**, nghĩa là cả `s1` và `s2` đều trỏ vào cùng một ô nhớ trên Heap.
- **💥 Hiểm họa Double Free:** Khi hàm `main` kết thúc, cả `s1` và `s2` đều ra khỏi scope. Cả hai sẽ cùng cố gắng gọi hàm giải phóng vùng nhớ Heap đó hai lần! Việc giải phóng cùng một vùng nhớ hai lần là nguyên nhân kinh điển dẫn đến phá hoại bộ nhớ và lỗ hổng bảo mật nghiêm trọng.

**🦀 Giải pháp đột phá của Rust:**
Thay vì sao chép nông, Rust thực hiện phép **Di chuyển quyền sở hữu (Move)**:
1. Rust sao chép $24$ bytes trên Stack (con trỏ `ptr`, `len`, `capacity`) từ `s1` sang `s2`.
2. **Ngay lập tức, Rust vô hiệu hóa hoàn toàn biến `s1`!** `s1` không còn được coi là một biến hợp lệ nữa.
3. Khi ra khỏi scope, chỉ có một mình `s2` là chủ sở hữu hợp pháp, do đó hàm `drop` chỉ được gọi **đúng một lần duy nhất** để giải phóng bộ nhớ Heap!

Nếu bạn cố tình truy cập `s1` sau khi đã Move, trình biên dịch `rustc` sẽ ngăn chặn ngay lập tức:

```text
error[E0382]: borrow of moved value: `s1`
 --> src/main.rs:5:16
  |
2 |     let s1 = String::from("hello");
  |         -- move occurs because `s1` has type `String`, which does not implement the `Copy` trait
3 |     let s2 = s1;
  |              -- value moved here
4 | 
5 |     println!("{s1}");
  |                ^^ value borrowed here after move
```

---

### 5.5. 🧬 Sao Chép Sâu Với Phương Thức `clone()`

Nếu bạn thực sự muốn cả `s1` và `s2` đều tồn tại độc lập với dữ liệu chuỗi riêng biệt, bạn phải gọi phương thức `.clone()` để thực hiện **Deep Copy (sao chép sâu)** toàn bộ dữ liệu trên Heap:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1.clone(); // Cấp phát thêm một vùng nhớ mới trên Heap và sao chép từng ký tự sang

    println!("s1 = {s1}, s2 = {s2}"); // ✅ Cả hai đều hợp lệ và độc lập!
}
```

> 💡 **Lời khuyên hiệu năng từ Rust Course:** Phép `.clone()` trên các cấu trúc dữ liệu lớn (như `String`, `Vec`) tiêu tốn thời gian cấp phát bộ nhớ và sao chép dữ liệu với độ phức tạp $O(n)$. Nếu thấy mã nguồn xuất hiện quá nhiều `.clone()`, hãy cân nhắc chuyển sang sử dụng **tham chiếu mượn (borrowing)**.

---

### 5.6. 📋 Dữ Liệu Ngăn Xếp & Đặc Tính `Copy` (The Copy Trait)

Tại sao đoạn mã sau với số nguyên lại hoạt động bình thường mà không bị báo lỗi Move?

```rust
fn main() {
    let x = 5;
    let y = x; // Không bị Move!

    println!("x = {x}, y = {y}"); // ✅ Cả hai biến x và y đều hợp lệ!
}
```

Lý do: Kiểu `i32` là kiểu dữ liệu có kích thước cố định và được lưu trữ hoàn toàn trên **Stack**. Việc sao chép dữ liệu trên Stack diễn ra cực kỳ nhanh chóng (độ phức tạp $O(1)$, chỉ một vài chu kỳ CPU).

Trong Rust, các kiểu dữ liệu chỉ nằm trên Stack và có thể sao chép bit trực tiếp sẽ cài đặt một đặc tính đặc biệt gọi là **Trait `Copy`**. Khi một kiểu có trait `Copy`, phép gán `=` sẽ tự động sao chép giá trị mới mà không vô hiệu hóa biến cũ.

#### ✅ Các kiểu dữ liệu có sẵn Trait `Copy`:
- Toàn bộ các kiểu số nguyên (`i8`, `u8`, `i32`, `usize`,...).
- Toàn bộ các kiểu số thực (`f32`, `f64`).
- Kiểu logic `bool`.
- Kiểu ký tự `char`.
- Tham chiếu bất biến `&T`.
- Kiểu bộ (Tuple) và Mảng `[T; N]`, **nhưng chỉ khi mọi phần tử bên trong nó đều cài đặt `Copy`**. Ví dụ: `(i32, f64)` có `Copy`, nhưng `(i32, String)` thì **KHÔNG** có `Copy`.

---

### 5.7. 🔄 Quyền Sở Hữu Trong Lời Gọi Hàm

Cơ chế truyền tham số vào hàm hoàn toàn tương tự như phép gán biến `=`:
- Nếu truyền một biến kiểu `Copy` (như `i32`): Giá trị được sao chép vào hàm, biến ban đầu ở hàm gọi vẫn dùng bình thường.
- Nếu truyền một biến không có `Copy` (như `String`): **Quyền sở hữu bị Move vào hàm nhận!** Biến ở hàm gọi bị vô hiệu hóa.

```rust
fn main() {
    let s = String::from("hello");
    takes_ownership(s); // 🚚 Quyền sở hữu của s bị di chuyển vào hàm!
    // println!("{s}"); // ❌ LỖI! s không còn hợp lệ ở đây!

    let x = 5;
    makes_copy(x);      // 📋 x có Copy, giá trị được copy sang hàm
    println!("x vẫn tồn tại: {x}"); // ✅ Hợp lệ!
}

fn takes_ownership(some_string: String) {
    println!("{some_string}");
} // some_string ra khỏi scope tại đây, hàm `drop` được gọi, bộ nhớ Heap của chuỗi được giải phóng!

fn makes_copy(some_integer: i32) {
    println!("{some_integer}");
}
```

Nếu muốn lấy lại quyền sở hữu, hàm sẽ phải trả lại giá trị qua tuple return:
```rust
fn calculate_length(s: String) -> (String, usize) {
    let length = s.len();
    (s, length) // Trả lại quyền sở hữu cùng độ dài
}
```
Nhưng cách này quá rườm rà và bất tiện! Đó là lý do Rust giới thiệu cơ chế mượn: **Borrowing**.

---

### 5.8. 🤝 Cơ Chế Mượn (Borrowing) & Tham Chiếu (References)

Thay vì chuyển giao quyền sở hữu, ta có thể tạo ra một **tham chiếu (reference)** đến giá trị đó. Hành động tạo tham chiếu được gọi là **mượn (borrowing)**. Giống như ngoài đời: bạn mượn cuốn sách từ bạn mình, bạn đọc xong thì trả lại chứ không hề sở hữu cuốn sách đó.

Tham chiếu được biểu thị bằng ký tự `&`:

```rust
fn main() {
    let s1 = String::from("hello");

    // Truyền tham chiếu &s1 vào hàm (chỉ cho mượn, không mất quyền sở hữu)
    let len = calculate_length(&s1);

    println!("Độ dài của '{s1}' là {len}."); // ✅ s1 vẫn còn nguyên vẹn ở đây!
}

// Tham số s mang kiểu tham chiếu &String
fn calculate_length(s: &String) -> usize {
    s.len()
} // s ra khỏi scope, nhưng vì s không sở hữu dữ liệu nó trỏ tới, hàm `drop` KHÔNG được gọi!
```

#### 1️⃣ Tham chiếu Bất biến (Immutable Reference `&T`):
Mặc định, tham chiếu là bất biến. Bạn chỉ có quyền đọc dữ liệu chứ không được phép sửa đổi:
```rust
fn change(some_string: &String) {
    // some_string.push_str(", world"); // ❌ LỖI BIÊN DỊCH!
    // cannot borrow `*some_string` as mutable, as it is behind a `&` reference
}
```

#### 2️⃣ Tham chiếu Khả biến (Mutable Reference `&mut T`):
Nếu muốn hàm sửa đổi được dữ liệu đang mượn, bạn phải dùng tham chiếu khả biến:
1. Biến gốc phải được khai báo là khả biến (`let mut s`).
2. Khi mượn phải truyền `&mut s`.
3. Kiểu tham số của hàm phải là `&mut String`.

```rust
fn main() {
    let mut s = String::from("hello");
    change(&mut s);
    println!("{s}"); // In ra: hello, world
}

fn change(some_string: &mut String) {
    some_string.push_str(", world");
}
```

---

### 5.9. 🛡️ Quy Tắc Vàng Của Borrow Checker: Ngăn Chặn Data Race

Để đảm bảo an toàn tuyệt đối, trình biên dịch Rust thực thi quy tắc kiểm tra mượn bất biến sau:

> ### 🚨 QUY TẮC MƯỢN CỐT TỬ CỦA RUST (READ-WRITE LOCK PATTERN)
> Tại một thời điểm bất kỳ trong một phạm vi dữ liệu, bạn chỉ được phép chọn **MỘT TRONG HAI** điều kiện sau:
> 1. 📖 Hoặc có **bất kỳ số lượng tham chiếu bất biến (`&T`) nào** (cho phép nhiều người cùng đọc — *Shared References*).
> 2. ✍️ Hoặc có **DUY NHẤT MỘT tham chiếu khả biến (`&mut T`)** (chỉ cho phép một người ghi độc quyền — *Exclusive Reference*).
> 
> **❌ TUYỆT ĐỐI KHÔNG BAO GIỜ cho phép vừa có người đọc (`&T`) vừa có người ghi (`&mut T`) cùng lúc!**

#### 🧠 Tại sao quy tắc này lại thiên tài?
Nó triệt tiêu tận gốc hiện tượng **Xung đột dữ liệu (Data Race)**. Một Data Race xảy ra khi có $3$ điều kiện đồng thời:
1. Hai hoặc nhiều con trỏ cùng truy cập vào cùng một vùng nhớ.
2. Ít nhất một trong số các con trỏ đang thực hiện ghi dữ liệu.
3. Không có cơ chế đồng bộ hóa giữa các thao tác.

Nhờ quy tắc mượn của Rust, điều kiện trên không bao giờ có thể xảy ra ngay từ lúc biên dịch!

#### ❌ Minh họa vi phạm 1: Nhiều tham chiếu khả biến cùng lúc:
```rust
let mut s = String::from("hello");

let r1 = &mut s;
let r2 = &mut s; // ❌ LỖI BIÊN DỊCH: cannot borrow `s` as mutable more than once at a time!

println!("{r1}, {r2}");
```

#### ❌ Minh họa vi phạm 2: Vừa đọc vừa ghi cùng lúc:
```rust
let mut s = String::from("hello");

let r1 = &s;     // ✅ Hợp lệ: mượn đọc
let r2 = &s;     // ✅ Hợp lệ: mượn đọc tiếp
let r3 = &mut s; // ❌ LỖI BIÊN DỊCH: cannot borrow `s` as mutable because it is also borrowed as immutable!

println!("{r1}, {r2}, and {r3}");
```

#### ✨ Cơ chế Non-Lexical Lifetimes (NLL):
Trong các phiên bản Rust hiện đại, phạm vi của một tham chiếu không kéo dài đến hết dấu ngoặc nhọn `}` mà **kết thúc ngay tại dòng lệnh cuối cùng mà nó được sử dụng**:

```rust
fn main() {
    let mut s = String::from("hello");

    let r1 = &s;
    let r2 = &s;
    println!("{r1} và {r2}"); // 🏁 Lần cuối r1 và r2 được sử dụng! Phạm vi mượn đọc kết thúc ở đây.

    let r3 = &mut s; // ✅ HOÀN TOÀN HỢP LỆ! Vì r1 và r2 không còn được dùng ở bên dưới nữa.
    println!("{r3}");
}
```

---

### 5.10. 🚫 Ngăn Chặn Con Trỏ Lơ Lửng (Dangling References)

Trong C/C++, con trỏ lơ lửng xảy ra khi con trỏ trỏ vào một vùng nhớ đã bị giải phóng. Trong Rust, trình biên dịch đảm bảo mọi tham chiếu đều luôn luôn trỏ đến vùng nhớ hợp lệ:

```rust
fn main() {
    let reference_to_nothing = dangle();
}

// ❌ CỐ TÌNH TRẢ VỀ THAM CHIẾU CỦA MỘT BIẾN CỤC BỘ TRONG HÀM:
fn dangle() -> &String {
    let s = String::from("hello");
    &s // Trả về tham chiếu tới s
} // s ra khỏi scope tại đây và bị giải phóng! Tham chiếu trả về sẽ trỏ vào vùng nhớ rác!
```

Trình biên dịch `rustc` sẽ ngăn chặn ngay lập tức:
```text
error[E0106]: missing lifetime specifier
 --> src/main.rs:5:16
  |
5 | fn dangle() -> &String {
  |                ^ expected named lifetime parameter
  = help: this function's return type contains a borrowed value, but there is no value for it to be borrowed from
help: instead, you are more likely to want to return an owned value
```
✅ Cách khắc phục rất đơn giản: Trả thẳng quyền sở hữu của `String` ra ngoài thay vì trả tham chiếu: `fn no_dangle() -> String { s }`.

---

### 5.11. 🍰 Kiểu Lát Cắt (Slices)

Lát cắt (*Slice*) là một dạng tham chiếu đến một chuỗi các phần tử liên tiếp nằm trong một tập hợp dữ liệu (như mảng hoặc chuỗi) mà không cần sở hữu tập hợp đó.

#### 1️⃣ Lát cắt Chuỗi (`&str`):
```rust
fn main() {
    let s = String::from("hello world");

    // Cú pháp [starting_index..ending_index]
    let hello: &str = &s[0..5];  // Cắt từ byte 0 đến byte 4 (độ dài 5)
    let world: &str = &s[6..11]; // Cắt từ byte 6 đến byte 10

    // Các cú pháp viết tắt tiện lợi:
    let slice1 = &s[..5];  // Bắt đầu từ 0 đến 4
    let slice2 = &s[6..];  // Bắt đầu từ 6 đến hết chuỗi
    let slice3 = &s[..];   // Cắt toàn bộ chuỗi
}
```

*🔬 Cấu trúc của `&str`:* Gồm con trỏ trỏ đến vị trí byte bắt đầu trên Heap và trường `len` độ dài lát cắt ($16$ bytes trên hệ thống $64$-bit).

#### 2️⃣ Ví dụ kinh điển: Hàm `first_word`:
Viết hàm trả về từ đầu tiên trong một chuỗi văn bản:

```rust
// Nhận vào &str (linh hoạt cho cả String và &str) và trả về &str
fn first_word(s: &str) -> &str {
    let bytes = s.as_bytes();

    for (i, &item) in bytes.iter().enumerate() {
        if item == b' ' {
            return &s[0..i]; // Trả về lát cắt của từ đầu tiên
        }
    }

    &s[..] // Nếu không có khoảng trắng, toàn bộ chuỗi là một từ
}

fn main() {
    let mut my_string = String::from("hello world");

    let word = first_word(&my_string); // Mượn bất biến my_string

    // my_string.clear(); // ❌ LỖI BIÊN DỊCH!
    // cannot borrow `my_string` as mutable because it is also borrowed as immutable!

    println!("Từ đầu tiên là: {word}");
}
```
Nhờ cơ chế kiểm tra mượn, nếu ai đó cố tình xóa dữ liệu của chuỗi (`clear()`) trong khi lát cắt `word` vẫn đang được sử dụng, Rust sẽ báo lỗi ngay tại compile-time!

#### 3️⃣ Lát cắt Mảng Số:
Áp dụng tương tự cho mảng:
```rust
let a = [1, 2, 3, 4, 5];
let slice: &[i32] = &a[1..3]; // Tham chiếu đến [2, 3]
assert_eq!(slice, &[2, 3]);
```

---

# 🧩 PHẦN IV: KIỂU PHỨC HỢP & KHỚP MẪU

---

## CHƯƠNG 6: 🔤 CHUỖI KÝ TỰ CHUYÊN SÂU (STRING & &STR)

Chuỗi ký tự trong Rust thường là một trong những rào cản gây bỡ ngỡ nhất cho người mới bắt đầu. Khác với các ngôn ngữ cấp cao nơi chuỗi chỉ đơn giản là một mảng ký tự hoặc một đối tượng duy nhất, Rust phân biệt rõ ràng giữa hai khái niệm: **chuỗi sở hữu (`String`)** và **lát cắt chuỗi (`&str`)**, đồng thời thực thi nghiêm ngặt mã hóa chuẩn **UTF-8**.

### 6.1. 🌐 Bản Chất Mã Hóa UTF-8 & Cạm Bẫy Đánh Chỉ Mục `s[i]`

Tại sao trong Rust bạn **KHÔNG THỂ** viết `s[0]` để lấy ký tự đầu tiên của chuỗi?

```rust
let s = String::from("hello");
// let h = s[0]; // ❌ LỖI BIÊN DỊCH: `String` cannot be indexed by `{integer}`!
```

#### 🔬 Bản chất tầng sâu:
Mã hóa UTF-8 là mã hóa có độ dài thay đổi (*variable-width encoding*). Một ký tự Unicode có thể chiếm từ **$1$ đến $4$ bytes**:
- Các ký tự tiếng Anh trong bảng mã ASCII (như `'a'`, `'b'`, `'1'`) chỉ chiếm đúng $1$ byte.
- Các ký tự tiếng Việt có dấu (như `'ế'`, `'à'`) hoặc tiếng Hy Lạp, Cyrillic chiếm **$2$ đến $3$ bytes**.
- Các biểu tượng cảm xúc Emoji (như `'🦀'`, `'🚀'`) hoặc chữ tượng hình tiếng Hán chiếm tới **$4$ bytes**.

Hãy xem ví dụ:
```rust
let hello = "Здравствуйте";
println!("Độ dài byte: {}", hello.len()); // In ra 24 bytes, dù chỉ có 12 ký tự!

let crab = "🦀";
println!("Độ dài byte: {}", crab.len());  // In ra 4 bytes!
```

Nếu Rust cho phép bạn đánh chỉ mục theo số nguyên `s[0]`, người lập trình sẽ mặc định tin rằng phép toán này có độ phức tạp thời gian $O(1)$. Nhưng để tìm ký tự thứ $n$ trong chuỗi UTF-8, máy tính buộc phải duyệt từ đầu byte số $0$ đến byte đó để xác định ranh giới ký tự (độ phức tạp $O(n)$). Hơn thế nữa, nếu bạn vô tình cắt lát vào giữa byte thứ $2$ của một ký tự $3$-byte, chuỗi sẽ bị hỏng mã hóa Unicode (gây panic)!

Vì vậy, Rust từ chối phép đánh chỉ mục số để bảo vệ tính toàn vẹn của dữ liệu và hiệu năng phần mềm.

---

### 6.2. ⚖️ Phân Biệt Giữa `String` Và `&str`

| 📌 Tiêu chí | 📦 `String` | 🍰 `&str` (String Slice) |
| :--- | :--- | :--- |
| **Bản chất vùng nhớ** | Nằm trên **Heap**, có khả năng mở rộng/co giãn | Là con trỏ mượn trỏ tới dữ liệu có sẵn (trên Stack, Heap, hoặc vùng nhớ tĩnh Binary) |
| **Quyền sở hữu** | Có quyền sở hữu dữ liệu (*Owned type*) | Chỉ mượn dữ liệu (*Borrowed view*) |
| **Kích thước con trỏ** | $24$ bytes (`ptr`, `len`, `capacity`) | $16$ bytes (`ptr`, `len`) — gọi là con trỏ béo (*fat pointer*) |
| **Khả năng thay đổi** | Có thể thêm/sửa/xóa ký tự (khi có `mut`) | Bất biến (chỉ có quyền đọc) |
| **Tình huống sử dụng** | Khi cần tạo mới chuỗi, nhận dữ liệu nhập, ghép chuỗi | Khi làm tham số hàm đọc dữ liệu để tăng tính linh hoạt tối đa |

---

### 6.3. 🛠️ Khởi Tạo & Thao Tác Chuỗi

```rust
fn main() {
    // 1. Khởi tạo chuỗi rỗng
    let mut s1 = String::new();

    // 2. Chuyển đổi từ chuỗi hằng tự vị (&str) thành String
    let s2 = "nội dung ban đầu".to_string();
    let s3 = String::from("nội dung ban đầu");

    // 3. Nối thêm ký tự và chuỗi con
    let mut s = String::from("foo");
    s.push_str("bar"); // Nối chuỗi slice &str
    s.push('!');       // Nối thêm 1 ký tự char
    println!("{s}");   // In ra: foobar!

    // 4. Nối hai chuỗi bằng toán tử `+`
    let str1 = String::from("Hello, ");
    let str2 = String::from("world!");
    // ⚠️ Chú ý: str1 bị Move quyền sở hữu vào str3! str2 chỉ truyền tham chiếu &str2
    let str3 = str1 + &str2; 
    // println!("{str1}"); // ❌ LỖI: str1 đã bị move!
    println!("{str3}");    // In ra: Hello, world!

    // 5. Nối nhiều chuỗi phức tạp bằng macro format! (KHÔNG làm mất quyền sở hữu)
    let s_a = String::from("tic");
    let s_b = String::from("tac");
    let s_c = String::from("toe");
    let game = format!("{s_a}-{s_b}-{s_c}"); // ✅ Rất rõ ràng, không move s_a, s_b, s_c
    println!("{game}"); // In ra: tic-tac-toe
}
```

---

### 6.4. 🔍 Duyệt Chuỗi Đúng Cách

Khi cần xử lý từng phần tử của chuỗi, bạn phải chỉ rõ bạn muốn duyệt theo **Ký tự Unicode (`char`)** hay duyệt theo **Byte nhị phân (`u8`)**:

```rust
fn main() {
    let s = "Việt Nam 🦀";

    // Duyệt theo từng ký tự Unicode (được giải mã đầy đủ):
    println!("--- 🔤 Duyệt theo ký tự (.chars()) ---");
    for c in s.chars() {
        print!("[{c}] ");
    }
    println!();

    // Duyệt theo từng byte thô:
    println!("--- 🔢 Duyệt theo byte (.bytes()) ---");
    for b in s.bytes() {
        print!("{b} ");
    }
    println!();
}
```

---

## CHƯƠNG 7: 🏗️ KIỂU DỮ LIỆU TÙY CHỈNH: STRUCTS & ENUMS

### 7.1. 🧱 Cấu Trúc Dữ Liệu Structs (Structures)

Struct là kiểu dữ liệu tổng hợp tùy chỉnh cho phép bạn đóng gói và đặt tên cho các trường dữ liệu có liên quan lại với nhau thành một đơn vị logic.

#### 1️⃣ Định nghĩa và Khởi tạo Struct:
```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn main() {
    // Khởi tạo một thể hiện (instance) của User
    let mut user1 = User {
        active: true,
        username: String::from("rustacean123"),
        email: String::from("user@example.com"),
        sign_in_count: 1,
    };

    // Truy cập và sửa đổi trường dữ liệu thông qua dấu chấm:
    user1.email = String::from("new_email@example.com");
    println!("📧 Email người dùng: {}", user1.email);
}
```

#### 2️⃣ Cú pháp khởi tạo rút gọn (Field Init Shorthand):
Khi tên tham số truyền vào trùng khớp hoàn toàn với tên trường của struct:
```rust
fn build_user(email: String, username: String) -> User {
    User {
        active: true,
        username, // Tương đương: username: username,
        email,    // Tương đương: email: email,
        sign_in_count: 1,
    }
}
```

#### 3️⃣ Cú pháp Cập nhật Struct (Struct Update Syntax `..`):
Tạo một instance mới kế thừa hầu hết các trường từ một instance cũ:
```rust
let user2 = User {
    email: String::from("another@example.com"),
    ..user1 // Toàn bộ các trường còn lại lấy từ user1!
};
```
> ⚠️ **Cảnh báo Quyền sở hữu:** Do trường `username` kiểu `String` của `user1` bị chuyển sang `user2`, biến `user1` sẽ không thể sử dụng trường `username` được nữa (đã bị Move). Tuy nhiên `user1.active` và `user1.sign_in_count` (kiểu `Copy`) vẫn dùng bình thường!

#### 4️⃣ Tuple Structs & Mẫu hình Newtype (Newtype Pattern):
Khi bạn muốn tạo một kiểu dữ liệu mới nhưng không cần đặt tên cho từng trường:
```rust
struct Color(i32, i32, i32);
struct Point(i32, i32, i32);

fn main() {
    let black = Color(0, 0, 0);
    let origin = Point(0, 0, 0);
    // Dù cùng chứa 3 số i32, nhưng `Color` và `Point` là 2 kiểu dữ liệu hoàn toàn khác biệt!
    // Bạn không thể vô tình truyền black vào một hàm yêu cầu Point!
}
```

#### 5️⃣ In Gỡ lỗi Struct với `#[derive(Debug)]`:
Mặc định struct không thể in bằng `{}`. Bạn phải thêm chỉ thị dẫn xuất `#[derive(Debug)]` để in bằng `{:?}` hoặc `{:#?}` (in đẹp nhiều dòng):

```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

fn main() {
    let rect1 = Rectangle { width: 30, height: 50 };
    println!("rect1 = {rect1:#?}");

    // Hoặc dùng macro dbg! (in ra file, dòng code và trả lại quyền sở hữu)
    let scale = 2;
    let rect2 = Rectangle {
        width: dbg!(30 * scale),
        height: 50,
    };
    dbg!(&rect2);
}
```

---

### 7.2. 🎭 Kiểu Liệt Kê Enums (Enumerations)

Nếu Struct gom các trường lại thành một tổ hợp (kiểu tích Đề-các — dạng *AND*), thì Enum cho phép một giá trị đại diện cho một trong nhiều biến thể có thể có (kiểu tổng đại số *Algebraic Data Type* — dạng *OR*).

#### 1️⃣ Enum Chứa Dữ Liệu Đa Hình:
Điểm vượt trội của Rust so với C/C++ hay Java là mỗi biến thể của Enum có thể chứa bất kỳ kiểu dữ liệu nào với kích thước và cấu trúc khác nhau:

```rust
#[derive(Debug)]
enum Message {
    Quit,                       // Không chứa dữ liệu (tương tự unit struct)
    Move { x: i32, y: i32 },    // Chứa một anonymous struct
    Write(String),              // Chứa một String đơn
    ChangeColor(i32, i32, i32), // Chứa 3 số nguyên (tuple variant)
}

fn main() {
    let msg1 = Message::Move { x: 10, y: 20 };
    let msg2 = Message::Write(String::from("Chào Rust! 🦀"));
    let msg3 = Message::ChangeColor(255, 0, 0);
}
```

#### 2️⃣ Enum `Option<T>` — Vũ Khí Loại Bỏ Triệt Để Lỗi Null:
Cha đẻ của con trỏ Null, ngài Tony Hoare, từng gọi con trỏ Null là *"sai lầm tỷ đô"* (*Billion-Dollar Mistake*) vì nó gây ra vô số lỗi crash phần mềm khi lập trình viên quên kiểm tra null.

**🛡️ Rust KHÔNG CÓ con trỏ Null!** Thay vào đó, thư viện chuẩn Rust cung cấp enum `Option<T>` để biểu thị một giá trị có thể tồn tại hoặc không tồn tại:

```rust
// Được định nghĩa sẵn trong thư viện chuẩn std:
enum Option<T> {
    None,    // Biểu thị giá trị không tồn tại / rỗng
    Some(T), // Biểu thị có giá trị hợp lệ kiểu T
}
```

Do `Option<T>` đã được nạp sẵn vào prelude, bạn có thể dùng trực tiếp `Some` và `None`:
```rust
let some_number = Some(5);            // Kiểu Option<i32>
let some_char = Some('e');            // Kiểu Option<char>
let absent_number: Option<i32> = None; // Biến không có giá trị
```

*💎 Sức mạnh an toàn kiểu:* Bạn **KHÔNG THỂ** lấy `i32` cộng trực tiếp với `Option<i32>`. Trình biên dịch bắt buộc bạn phải kiểm tra và giải nén giá trị ra khỏi `Some` trước khi tính toán. Điều này loại trừ $100\%$ khả năng xảy ra lỗi `NullPointerException`!

---

## CHƯƠNG 8: 🎯 NGHỆ THUẬT KHỚP MẪU (PATTERN MATCHING)

Khớp mẫu là công cụ điều khiển luồng mạnh mẽ nhất trong Rust, cho phép bạn đối sánh cấu trúc dữ liệu phức tạp với các mẫu để rẽ nhánh logic.

### 8.1. 🎛️ Cấu Trúc Khớp Mẫu `match` Toàn Diện (Exhaustive)

`match` trong Rust bắt buộc phải bao quát toàn bộ mọi biến thể có thể xảy ra:

```rust
enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(UsState), // Biến thể chứa dữ liệu con
}

#[derive(Debug)]
enum UsState {
    Alabama,
    Alaska,
}

fn value_in_cents(coin: Coin) -> u8 {
    match coin {
        Coin::Penny => {
            println!("🍀 Đồng 1 xu may mắn!");
            1
        }
        Coin::Nickel => 5,
        Coin::Dime => 10,
        Coin::Quarter(state) => {
            println!("🪙 Đồng 25 xu của bang: {state:?}!");
            25
        }
    }
}
```

#### 🔍 Khớp mẫu với `Option<T>`:
```rust
fn plus_one(x: Option<i32>) -> Option<i32> {
    match x {
        None => None,
        Some(i) => Some(i + 1), // Rút trích giá trị i ra khỏi Some
    }
}
```

#### 🃏 Mẫu Đại diện Bỏ qua (`_` Wildcard):
Khi bạn chỉ quan tâm đến một vài trường hợp và muốn gom toàn bộ các trường hợp còn lại:
```rust
let dice_roll = 9;
match dice_roll {
    3 => add_fancy_hat(),
    7 => remove_fancy_hat(),
    _ => reroll(), // Mọi số khác đều đi vào nhánh này
}
```

---

### 8.2. ⚡ Cú Pháp Rút Gọn: `if let` và `while let`

Khi bạn chỉ muốn xử lý duy nhất **MỘT** trường hợp khớp mẫu và bỏ qua toàn bộ các trường hợp khác, cú pháp `if let` giúp code gọn hơn rất nhiều so với `match`:

```rust
let config_max = Some(3u8);

// DÙNG MATCH TRUYỀN THỐNG:
match config_max {
    Some(max) => println!("Giá trị max được cấu hình là: {max}"),
    _ => (), // Phải viết thêm dòng này cho đủ tính exhaustive
}

// ✅ RÚT GỌN VỚI IF LET:
if let Some(max) = config_max {
    println!("Giá trị max được cấu hình là: {max}");
}
```

Vòng lặp `while let`: Tiếp tục lặp chừng nào mẫu còn khớp:
```rust
let mut stack = Vec::new();
stack.push(1);
stack.push(2);
stack.push(3);

// Lấy phần tử ra khỏi stack cho đến khi stack rỗng (trả về None)
while let Some(top) = stack.pop() {
    println!("{top}");
}
```

---

### 8.3. 🚀 Cú Pháp Hiện Đại: `let else` (Giữ Luồng Code Trên "Happy Path")

Được chuẩn hóa trong các phiên bản Rust hiện đại, `let else` cho phép bạn giải cấu trúc một mẫu; nếu không khớp, khối `else` sẽ bắt buộc phải thoát sớm (`return`, `break`, `continue` hoặc `panic!`). Kỹ thuật này giúp loại bỏ tình trạng code bị thụt lề lồng nhau quá sâu:

```rust
fn process_hex_digit(c: char) -> Result<u32, String> {
    // Nếu to_digit(16) trả về Some(digit), biến digit được tạo ra ngay ở scope ngoài!
    // Nếu là None, nhảy vào khối else và return sớm:
    let Some(digit) = c.to_digit(16) else {
        return Err(format!("❌ '{c}' không phải ký tự hex hợp lệ!"));
    };

    // Dùng trực tiếp digit ở đây mà không cần lồng if:
    Ok(digit * 2)
}
```

---

### 8.4. 🔥 Kỹ Thuật Khớp Mẫu Nâng Cao

#### 1️⃣ Ràng buộc Mẫu với Toán tử `@` (Bindings):
Toán tử `@` cho phép bạn vừa kiểm tra giá trị nằm trong một khoảng, vừa gán giá trị đó vào một biến để sử dụng:

```rust
enum Message {
    Hello { id: i32 },
}

let msg = Message::Hello { id: 5 };

match msg {
    Message::Hello {
        id: id_variable @ 3..=7, // Kiểm tra id trong khoảng 3..=7 và gán vào id_variable
    } => println!("✅ Tìm thấy id trong khoảng: {id_variable}"),
    Message::Hello { id: 10..=12 } => {
        println!("Tìm thấy id trong khoảng khác");
    }
    Message::Hello { id } => println!("Id nào đó: {id}"),
}
```

#### 2️⃣ Điều Kiện Phụ (Match Guards):
Thêm một điều kiện `if` vào nhánh match để lọc chi tiết:
```rust
let num = Some(4);

match num {
    Some(x) if x % 2 == 0 => println!("Số chẵn: {x}"),
    Some(x) => println!("Số lẻ: {x}"),
    None => (),
}
```

---

# ⚙️ PHẦN V: PHƯƠNG THỨC, GENERICS & TRAITS

---

## CHƯƠNG 9: 🔧 PHƯƠNG THỨC & KHỐI TRIỂN KHAI (IMPL METHODS)

Trong Rust, ta không định nghĩa phương thức trực tiếp bên trong khai báo struct hay enum (như class trong Java hay C++). Thay vào đó, dữ liệu và hành vi được tách bạch rõ ràng: dữ liệu nằm trong `struct`/`enum`, còn hành vi được định nghĩa trong khối **triển khai `impl`** (*implementation block*).

### 9.1. 📐 Định Nghĩa Phương Thức với Tham Số `self`

Phương thức là các hàm được liên kết với một kiểu dữ liệu cụ thể. Tham số đầu tiên của phương thức **luôn luôn là `self`**, đại diện cho thể hiện (*instance*) của kiểu dữ liệu mà phương thức đang được gọi trên đó:

```rust
#[derive(Debug)]
struct Rectangle {
    width: u32,
    height: u32,
}

// Khối triển khai các phương thức và hàm liên kết cho Rectangle
impl Rectangle {
    // Phương thức tính diện tích: mượn đọc bất biến (&self)
    fn area(&self) -> u32 {
        self.width * self.height
    }

    // Phương thức kiểm tra có chứa được hình chữ nhật khác không:
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }
}

fn main() {
    let rect1 = Rectangle { width: 30, height: 50 };
    let rect2 = Rectangle { width: 10, height: 40 };

    // Gọi phương thức bằng cú pháp dấu chấm (.):
    println!("📏 Diện tích rect1: {} px", rect1.area());
    println!("📦 rect1 có chứa được rect2? {}", rect1.can_hold(&rect2));
}
```

---

### 9.2. 🎭 Ba Biến Thể Của Tham Số Nhận `self`

Tương tự như việc truyền biến vào hàm, tham số `self` của phương thức có $3$ hình thức chính:

1. **📖 `&self` (Mượn bất biến - Shared Borrow):**
   - Viết tắt của `self: &Self`.
   - Đây là dạng phổ biến nhất (chiếm hơn $80\%$ trường hợp). Phương thức chỉ đọc dữ liệu từ struct mà không sửa đổi và không lấy đi quyền sở hữu. Instance có thể tiếp tục sử dụng sau lời gọi.
2. **✍️ `&mut self` (Mượn khả biến - Exclusive Borrow):**
   - Viết tắt của `self: &mut Self`.
   - Dùng khi phương thức cần thay đổi trạng thái nội bộ của instance.
   ```rust
   impl Rectangle {
       fn scale(&mut self, factor: u32) {
           self.width *= factor;
           self.height *= factor;
       }
   }
   ```
3. **🚚 `self` (Chiếm quyền sở hữu - Value Move):**
   - Viết tắt của `self: Self`.
   - Phương thức tiêu thụ hoàn toàn instance đó. Sau khi gọi phương thức, instance ban đầu bị hủy (*dropped*) và không thể dùng lại được nữa. Thường dùng trong mô hình chuyển đổi trạng thái (*Typestate pattern*) hoặc hàm kết thúc luồng dữ liệu (ví dụ: `into_bytes()`).

> ✨ **Tính năng Tự động Tham chiếu và Giải tham chiếu (Automatic Referencing & Dereferencing):**  
> Trong C/C++, bạn dùng `object.method()` cho đối tượng và `pointer->method()` cho con trỏ. Trong Rust, bạn không cần toán tử `->`. Khi bạn viết `rect1.area()`, Rust sẽ tự động suy luận kiểu và chèn `&`, `&mut`, hoặc `*` cho phù hợp với chữ ký của phương thức!

---

### 9.3. 🏗️ Hàm Liên Kết (Associated Functions)

Hàm nằm trong khối `impl` nhưng **KHÔNG có tham số `self`** được gọi là **hàm liên kết** (*associated function* - tương tự như `static method` trong Java/C++). 

Hàm liên kết thường được sử dụng phổ biến nhất làm hàm khởi tạo (*constructor*), và theo quy ước chuẩn của cộng đồng Rust, nó thường được đặt tên là `new`:

```rust
impl Rectangle {
    // Hàm khởi tạo hình chữ nhật
    fn new(width: u32, height: u32) -> Self {
        Self { width, height } // `Self` là bí danh đại diện cho chính kiểu dữ liệu của khối impl (Rectangle)
    }

    // Hàm khởi tạo hình vuông
    fn square(size: u32) -> Self {
        Self { width: size, height: size }
    }
}

fn main() {
    // Gọi hàm liên kết bằng toán tử phạm vi `::` gắn với tên struct:
    let sq = Rectangle::square(25);
    let rect = Rectangle::new(10, 20);
}
```

---

## CHƯƠNG 10: 🧬 KIỂU CHUNG (GENERICS) & ĐẶC TÍNH (TRAITS)

### 10.1. 🧩 Kiểu Chung (Generics)

Generics là công cụ trừu tượng hóa cho phép bạn viết các hàm, cấu trúc dữ liệu hoặc thuật toán có thể hoạt động trên nhiều kiểu dữ liệu khác nhau mà không cần phải sao chép lặp lại mã nguồn.

#### 1️⃣ Generics trong Định nghĩa Hàm:
Tìm phần tử lớn nhất trong một lát cắt:
```rust
// Hàm tìm số lớn nhất nhận lát cắt kiểu T bất kỳ với điều kiện T phải so sánh được (PartialOrd)
fn largest<T: std::cmp::PartialOrd>(list: &[T]) -> &T {
    let mut largest = &list[0];

    for item in list {
        if item > largest {
            largest = item;
        }
    }

    largest
}

fn main() {
    let number_list = vec![34, 50, 25, 100, 65];
    let result = largest(&number_list);
    println!("🏆 Số lớn nhất: {result}");

    let char_list = vec!['y', 'm', 'a', 'q'];
    let result = largest(&char_list);
    println!("🏆 Ký tự lớn nhất: {result}");
}
```

#### 2️⃣ Generics trong Structs và Enums:
```rust
// Struct Point có tọa độ x và y cùng kiểu T
struct Point<T> {
    x: T,
    y: T,
}

// Struct hỗn hợp: x mang kiểu T, y mang kiểu U
struct MixedPoint<T, U> {
    x: T,
    y: U,
}

fn main() {
    let integer_point = Point { x: 5, y: 10 };       // Point<i32>
    let float_point = Point { x: 1.0, y: 4.0 };      // Point<f64>
    let mixed = MixedPoint { x: 5, y: "hello" };      // MixedPoint<i32, &str>
}
```

#### 3️⃣ Const Generics (Generics theo Hằng số Kích thước):
Rust còn hỗ trợ truyền các hằng số thời điểm biên dịch làm tham số generic (rất hữu ích khi làm việc với mảng cố định `[T; N]` hoặc ma trận toán học):
```rust
fn display_array<T: std::fmt::Debug, const N: usize>(arr: [T; N]) {
    println!("Mảng có kích thước {N}: {arr:?}");
}

fn main() {
    display_array([1, 2, 3]);
    display_array(["Rust", "Course", "Thái", "Việt"]);
}
```

---

### 10.2. ⚡ Cơ Chế Đơn Hình Hóa (Monomorphization): Chi Phí Bằng Không

Một câu hỏi lớn: *Liệu việc dùng Generics có làm chậm tốc độ chạy của chương trình so với việc viết code riêng cho từng kiểu dữ liệu không?*

**💎 Câu trả lời của Rust là: HOÀN TOÀN KHÔNG!**  
Rust thực hiện cơ chế **Đơn hình hóa (Monomorphization)** ngay trong quá trình biên dịch:
1. Trình biên dịch quét toàn bộ mã nguồn để tìm ra các kiểu dữ liệu cụ thể đã được dùng với Generic (ví dụ: `Point<i32>` và `Point<f64>`).
2. Trình biên dịch sẽ tự động sinh ra hai định nghĩa mã máy độc lập riêng biệt: một bản tối ưu hóa cho `i32` và một bản tối ưu hóa cho `f64`.
3. Khi chạy, mã máy thực thi hệt như bạn đã tự tay viết code riêng cho từng kiểu dữ liệu. Đây chính là minh chứng kinh điển cho nguyên lý **Zero-Cost Abstractions (Trừu tượng hóa không tốn phí runtime)** của Rust!

---

### 10.3. 📜 Đặc Tính Traits (Định Nghĩa Hành Vi Chung)

Một **Trait** định nghĩa một tập hợp các phương thức mà một kiểu dữ liệu phải cài đặt để thể hiện một hành vi cụ thể (tương tự khái niệm *Interface* trong Java hay Go, hoặc *Typeclass* trong Haskell).

#### 1️⃣ Khai báo Trait:
```rust
// Định nghĩa Trait Summary thể hiện khả năng tóm tắt thông tin
pub trait Summary {
    fn summarize(&self) -> String;
}
```

#### 2️⃣ Cài đặt Trait cho Kiểu Dữ Liệu:
```rust
pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {
    fn summarize(&self) -> String {
        format!("{}, bởi {} ({})", self.headline, self.author, self.location)
    }
}

pub struct Tweet {
    pub username: String,
    pub content: String,
    pub reply: bool,
    pub retweet: bool,
}

impl Summary for Tweet {
    fn summarize(&self) -> String {
        format!("{}: {}", self.username, self.content)
    }
}
```

> 📌 **Quy tắc Cô Nhi (Orphan Rule / Coherence):**  
> Bạn chỉ được phép cài đặt một Trait `T` cho một kiểu dữ liệu `S` khi **ít nhất một trong hai (`T` hoặc `S`) thuộc về crate hiện tại của bạn**. Bạn không thể cài đặt một Trait của thư viện ngoài (như `Display`) cho một kiểu của thư viện ngoài (như `Vec<T>`) để tránh xung đột mã nguồn toàn cục.

#### 3️⃣ Cài đặt Phương thức Mặc định (Default Implementation):
Trait cho phép cung cấp mã nguồn mặc định cho một số phương thức. Các kiểu cài đặt có thể chọn giữ nguyên phương thức mặc định hoặc ghi đè (*override*):
```rust
pub trait Summary {
    // Phương thức bắt buộc phải cài đặt:
    fn summarize_author(&self) -> String;

    // Phương thức mặc định (gọi phương thức bên trên):
    fn summarize(&self) -> String {
        format!("(Đọc thêm từ tác giả {}...)", self.summarize_author())
    }
}
```

---

### 10.4. 🔗 Ràng Buộc Đặc Tính (Trait Bounds)

Thay vì nhận một kiểu cụ thể, bạn có thể viết hàm nhận bất kỳ kiểu nào **miễn là nó cài đặt Trait tương ứng**.

#### 1️⃣ Cú pháp rút gọn `impl Trait`:
```rust
pub fn notify(item: &impl Summary) {
    println!("📢 Tin mới nhận! {}", item.summarize());
}
```

#### 2️⃣ Cú pháp Trait Bound đầy đủ:
Cú pháp `impl Trait` ở trên thực chất là cú pháp đường mật (*syntactic sugar*) của Trait Bound:
```rust
pub fn notify<T: Summary>(item: &T) {
    println!("📢 Tin mới nhận! {}", item.summarize());
}
```

#### 3️⃣ Đa ràng buộc với toán tử `+`:
Yêu cầu kiểu `T` vừa phải cài đặt `Summary` vừa phải in được định dạng `Display`:
```rust
pub fn notify<T: Summary + std::fmt::Display>(item: &T) {
    println!("{item}");
}
```

#### 4️⃣ Mệnh đề `where` giúp chữ ký hàm trong sáng:
Khi có quá nhiều tham số generic với các ràng buộc phức tạp, cú pháp inline sẽ làm rối chữ ký hàm. Hãy chuyển các ràng buộc xuống mệnh đề `where`:
```rust
fn some_function<T, U>(t: &T, u: &U) -> i32
where
    T: std::fmt::Display + Clone,
    U: Clone + std::fmt::Debug,
{
    // Thân hàm gọn gàng
    42
}
```

---

### 10.5. ⚖️ Đa Hình Tĩnh vs. Đa Hình Động (Static vs. Dynamic Dispatch)

Rust cung cấp cho bạn hai cơ chế đa hình với sự đánh đổi rõ ràng:

#### 1️⃣ Đa hình Tĩnh (Static Dispatch) — `impl Trait` / Generics:
- **⚙️ Cơ chế:** Dùng cơ chế đơn hình hóa tại compile-time. Trình biên dịch biết rõ kiểu cụ thể tại từng điểm gọi và inline mã máy trực tiếp.
- **✅ Ưu điểm:** Tốc độ tối đa, không tốn chi phí tra cứu con trỏ hàm lúc chạy.
- **⚠️ Hạn chế:** Tăng nhẹ kích thước file thực thi; không thể lưu trữ các kiểu dữ liệu khác nhau vào cùng một mảng (ví dụ: không thể tạo `Vec<impl Summary>`).

#### 2️⃣ Đa hình Động (Dynamic Dispatch) — Trait Objects (`dyn Trait`):
Khi bạn thực sự cần lưu trữ nhiều kiểu khác nhau trong cùng một tập hợp (như một danh sách các widget giao diện GUI: `Button`, `TextBox`, `Checkbox`), bạn sử dụng **Đối tượng Đặc tính (Trait Object)**:

```rust
// Định nghĩa Trait vẽ giao diện
pub trait Draw {
    fn draw(&self);
}

pub struct Screen {
    // Vector chứa các con trỏ thông minh Box trỏ tới bất kỳ kiểu nào có Trait Draw:
    pub components: Vec<Box<dyn Draw>>,
}

impl Screen {
    pub fn run(&self) {
        for component in &self.components {
            component.draw(); // Gọi hàm thông qua bảng phương thức ảo (vtable)!
        }
    }
}
```

- **🔬 Cấu trúc Fat Pointer của `&dyn Trait` hoặc `Box<dyn Trait>`:**
  Gồm $2$ con trỏ ($16$ bytes trên hệ $64$-bit):
  1. Con trỏ `data_ptr` trỏ đến vùng dữ liệu thực tế của đối tượng.
  2. Con trỏ `vptr` trỏ đến bảng phương thức ảo (**vtable** - *Virtual Method Table*) chứa địa chỉ các hàm đã được biên dịch của trait đó.

---

# 🗂️ PHẦN VI: TẬP HỢP DỮ LIỆU, CHUYỂN ĐỔI KIỂU & XỬ LÝ LỖI

---

## CHƯƠNG 11: 📚 CÁC CẤU TRÚC DỮ LIỆU TẬP HỢP (COLLECTIONS)

Khác với mảng (`[T; N]`) và bộ (`tuple`) có kích thước cố định và được cấp phát trên Stack, các kiểu dữ liệu tập hợp trong thư viện chuẩn `std::collections` được lưu trữ trên **Heap**. Điều này cho phép chúng có thể co giãn kích thước linh hoạt tùy theo nhu cầu của chương trình tại thời điểm chạy.

### 11.1. 📈 Vector Co Giãn (`Vec<T>`)

Vector là cấu trúc dữ liệu tập hợp phổ biến và quan trọng nhất trong Rust. Nó lưu trữ các phần tử có cùng kiểu `T` nối tiếp nhau trên bộ nhớ Heap, cho phép truy cập ngẫu nhiên với độ phức tạp $O(1)$ và thêm phần tử vào cuối với độ phức tạp trung bình $O(1)$ (*amortized*).

#### 1️⃣ Khởi tạo và Thêm phần tử:
```rust
fn main() {
    // Cách 1: Khởi tạo vector rỗng với kiểu chú thích
    let mut v1: Vec<i32> = Vec::new();

    // Cách 2: Khởi tạo sẵn dung lượng bộ nhớ (tránh cấp phát lại nhiều lần):
    let mut v_cap: Vec<i32> = Vec::with_capacity(10);

    // Cách 3: Dùng macro tiện lợi `vec![]` với giá trị ban đầu (Rust tự suy luận kiểu):
    let mut v2 = vec![1, 2, 3];

    // Thêm phần tử bằng phương thức .push()
    v2.push(4);
    v2.push(5);

    println!("Vector v2: {v2:?}");
}
```

#### 2️⃣ Hai cách đọc phần tử trong Vector:
```rust
fn main() {
    let v = vec![10, 20, 30, 40, 50];

    // Cách 1: Đánh chỉ mục trực tiếp v[i]
    // ✅ Ưu điểm: Ngắn gọn.
    // ⚠️ Nhược điểm: Nếu chỉ mục vượt quá độ dài, chương trình sẽ lập tức PANIC (sập)!
    let third: &i32 = &v[2];
    println!("Phần tử thứ 3 là: {third}");

    // Cách 2: Sử dụng phương thức .get(i) an toàn
    // Trả về Option<&T>: `Some(&element)` nếu hợp lệ, `None` nếu vượt biên
    let index = 100;
    match v.get(index) {
        Some(element) => println!("Phần tử tại vị trí {index} là: {element}"),
        None => println!("⚠️ Chỉ mục {index} không tồn tại trong vector!"),
    }
}
```

#### 3️⃣ Duyệt Vector và Quy tắc Borrow Checker:
```rust
fn main() {
    let mut v = vec![100, 32, 57];

    // Duyệt và sửa đổi giá trị từng phần tử qua tham chiếu khả biến:
    for i in &mut v {
        *i += 50; // Dùng toán tử giải tham chiếu `*` để cộng thêm 50 vào giá trị
    }

    // Duyệt chỉ đọc qua tham chiếu bất biến:
    for i in &v {
        println!("{i}");
    }
}
```

---

### 11.2. 🗺️ Bảng Băm (`HashMap<K, V>`)

`HashMap<K, V>` lưu trữ các cặp khóa - giá trị (**Key - Value**) dựa trên thuật toán băm (*SipHash 1-3* mặc định chống tấn công từ chối dịch vụ HashDoS). Khóa `K` phải là kiểu dữ liệu có thể băm được (cài đặt trait `Eq` và `Hash`). Độ phức tạp tra cứu và chèn trung bình là $O(1)$.

```rust
use std::collections::HashMap;

fn main() {
    let mut scores = HashMap::new();

    // Thêm cặp dữ liệu bằng .insert(key, value)
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Yellow"), 50);

    // Lấy dữ liệu an toàn với .get(&key) trả về Option<&V>:
    let team_name = String::from("Blue");
    let score = scores.get(&team_name).copied().unwrap_or(0);
    println!("🏅 Điểm của đội {team_name}: {score}");

    // Duyệt toàn bộ bảng băm:
    for (key, value) in &scores {
        println!("{key}: {value}");
    }
}
```

#### ✨ Phương thức Thần thánh `.entry().or_insert()`:
Một bài toán cực kỳ kinh điển trong lập trình là đếm tần suất xuất hiện của từ ngữ trong một câu. Phương thức `.entry()` của Rust cho phép bạn kiểm tra khóa có tồn tại hay không và cập nhật giá trị chỉ trong một dòng lệnh:

```rust
use std::collections::HashMap;

fn main() {
    let text = "hello world wonderful world hello rust";
    let mut map = HashMap::new();

    for word in text.split_whitespace() {
        // .entry(word) trả về một Entry enum (Occupied hoặc Vacant).
        // .or_insert(0) sẽ chèn giá trị 0 nếu từ chưa có, và trả về một tham chiếu khả biến (&mut V) tới giá trị đó:
        let count = map.entry(word).or_insert(0);
        *count += 1; // Tăng bộ đếm lên 1
    }

    println!("📊 Tần suất xuất hiện: {map:#?}");
}
```

---

## CHƯƠNG 12: 🔄 CHUYỂN ĐỔI KIỂU DỮ LIỆU (TYPE CONVERSIONS)

Hệ thống kiểu của Rust cực kỳ khắt khe và **hoàn toàn không hỗ trợ ép kiểu ngầm định (implicit coercion)**. Bạn không thể gán một biến `u8` cho một biến `u32` mà không chuyển đổi kiểu tường minh.

### 12.1. 🔨 Ép Kiểu Nguyên Thủy Với Toán Tử `as`

Toán tử `as` dùng để ép kiểu giữa các kiểu số nguyên và số thực nguyên thủy:

```rust
let a: i32 = 10;
let b: u32 = a as u32; // Chuyển từ i32 sang u32
let c: f64 = b as f64; // Chuyển từ u32 sang f64
```

> ⚠️ **Cảnh báo Cắt cụt Byte (Truncation):**  
> Nếu ép kiểu từ một số có kích thước lớn xuống số có kích thước nhỏ hơn (ví dụ: `u32` sang `u8`), Rust sẽ cắt cụt các byte cao phía trước theo phép toán modulo $2^8 = 256$:
> ```rust
> let big: u32 = 300;
> let small: u8 = big as u8; // 300 % 256 = 44! Giá trị bị biến dạng nếu bạn không cẩn thận!
> ```

---

### 12.2. ✅ Chuyển Đổi An Toàn: Trait `From` Và `Into`

`From` và `Into` là cặp trait được thiết kế cho các phép chuyển đổi **luôn luôn thành công (infallible conversions)** và không bao giờ làm mất dữ liệu.

> 💡 **Quy tắc vàng:** **Khi bạn cài đặt `From` cho một kiểu, Rust sẽ tự động cài đặt `Into` cho bạn hoàn toàn miễn phí!**

```rust
use std::convert::From;

#[derive(Debug)]
struct Number {
    value: i32,
}

// Cài đặt chuyển đổi từ i32 sang Number
impl From<i32> for Number {
    fn from(item: i32) -> Self {
        Number { value: item }
    }
}

fn main() {
    // Sử dụng From:
    let num = Number::from(30);
    println!("Khởi tạo với From: {num:?}");

    // Sử dụng Into (tự động có sẵn nhờ cài đặt From):
    let int = 50;
    let num2: Number = int.into();
    println!("Khởi tạo với Into: {num2:?}");
}
```

---

### 12.3. 🛡️ Chuyển Đổi Có Thể Thất Bại: Trait `TryFrom` Và `TryInto`

Đối với các phép chuyển đổi có khả năng thất bại (ví dụ: chuyển từ số nguyên âm sang số nguyên dương, hoặc ép kiểu số lớn thành số nhỏ), Rust cung cấp `TryFrom` và `TryInto`. Chúng trả về một kiểu `Result<T, Error>`:

```rust
use std::convert::TryFrom;
use std::convert::TryInto;

fn main() {
    let big_number: i64 = 100;
    // Chuyển i64 sang u8:
    let small_number: Result<u8, _> = u8::try_from(big_number);
    println!("✅ Kết quả hợp lệ: {small_number:?}"); // Ok(100)

    let invalid_number: i64 = 1000;
    let failed: Result<u8, _> = invalid_number.try_into();
    println!("❌ Kết quả thất bại: {failed:?}"); // Err(TryFromIntError)
}
```

---

## CHƯƠNG 13: 🛡️ CHIẾN LƯỢC XỬ LÝ LỖI (ERROR HANDLING)

Triết lý của Rust về xử lý lỗi rất rõ ràng: **Rust không có ngoại lệ (Exceptions như `try/catch` trong Java hay Python).** Thay vào đó, Rust phân chia lỗi thành hai nhóm rạch ròi:

```text
+--------------------------------------+--------------------------------------+
| 💥 LỖI KHÔNG THỂ PHỤC HỒI (PANIC)    | 🔄 LỖI CÓ THỂ PHỤC HỒI (RESULT)      |
+--------------------------------------+--------------------------------------+
| - Lỗi logic nghiêm trọng, bug code   | - Các sự cố thông thường khi chạy    |
| - Ví dụ: out of bounds, chia cho 0   | - Ví dụ: file không tìm thấy, mất mạng|
| - Biểu diễn bằng: Macro `panic!`     | - Biểu diễn bằng: Kiểu `Result<T, E>`|
| - Hành vi: Dừng chương trình ngay    | - Hành vi: Trả về lỗi để caller xử lý|
+--------------------------------------+--------------------------------------+
```

### 13.1. 💥 Lỗi Không Thể Phục Hồi: `panic!`

Khi macro `panic!` được gọi, chương trình sẽ in thông báo lỗi, thu hồi và giải phóng bộ nhớ Stack (*unwinding*), sau đó thoát:

```rust
fn main() {
    panic!("💥 Lỗi thảm họa xảy ra! Dừng toàn bộ hệ thống!");
}
```

---

### 13.2. 🔄 Lỗi Có Thể Phục Hồi: Kiểu `Result<T, E>`

`Result` là kiểu enum có hai biến thể:
```rust
enum Result<T, E> {
    Ok(T),  // ✅ Thành công, chứa giá trị T
    Err(E), // ❌ Thất bại, chứa thông tin lỗi E
}
```

#### 📂 Ví dụ đọc tập tin từ ổ đĩa:
```rust
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let greeting_file_result = File::open("hello.txt");

    let greeting_file = match greeting_file_result {
        Ok(file) => file,
        Err(error) => match error.kind() {
            // Nếu file chưa tồn tại, tự động tạo mới:
            ErrorKind::NotFound => match File::create("hello.txt") {
                Ok(fc) => fc,
                Err(e) => panic!("❌ Không thể tạo tập tin: {e:?}"),
            },
            other_error => panic!("❌ Lỗi mở tập tin: {other_error:?}"),
        },
    };
}
```

#### 🔧 Các phương thức hỗ trợ mở gói tiện lợi:
- **`.unwrap()`:** Nếu là `Ok`, trả về giá trị bên trong; nếu là `Err`, tự động gọi `panic!`. Chỉ nên dùng khi viết code mẫu nhanh hoặc trong bài kiểm thử.
- **`.expect("Lời nhắn")`:** Tương tự `unwrap()`, nhưng in ra thông báo lỗi chỉ định của bạn khi panic, giúp dễ dàng gỡ lỗi (*debugging*).
- **`.unwrap_or(default)` / `.unwrap_or_else(|err| ...)`:** Trả về giá trị mặc định an toàn nếu gặp lỗi mà không hề gây panic!

---

### 13.3. ❓ Toán Tử Lan Truyền Lỗi Siêu Việt `?` (The `?` Operator)

Viết `match` lồng nhau để xử lý lỗi khiến mã nguồn trở nên dài dòng và khó đọc. Toán tử `?` là một trong những tính năng tiện ích được yêu thích nhất của Rust:

```rust
use std::fs::File;
use std::io::{self, Read};

// Hàm đọc tên người dùng từ tập tin:
fn read_username_from_file() -> Result<String, io::Error> {
    let mut username_file = File::open("username.txt")?; // ⚡ NẾU LỖI, LẬP TỨC RETURN ERR RA KHỎI HÀM!
    let mut username = String::new();
    username_file.read_to_string(&mut username)?;        // ⚡ NẾU LỖI, TIẾP TỤC RETURN ERR!
    Ok(username)                                         // ✅ NẾU MỌI THỨ THÀNH CÔNG, TRẢ VỀ OK
}
```

#### 🔬 Cách hoạt động của toán tử `?`:
1. Nếu giá trị bên trái là `Ok(v)`, toán tử `?` tự động giải nén và trả về giá trị `v` để dòng lệnh tiếp tục chạy bình thường.
2. Nếu giá trị là `Err(e)`, toán tử `?` sẽ **dừng hàm hiện tại ngay lập tức** và trả giá trị `Err(e)` đó về cho hàm cha đã gọi nó (*early return*).
3. **Tự động chuyển đổi kiểu lỗi:** Nếu hàm cha yêu cầu một kiểu lỗi khác, toán tử `?` sẽ tự động gọi phương thức `from` (thông qua trait `From`) để chuyển đổi kiểu lỗi con thành kiểu lỗi của hàm cha!

#### ⛓️ Chuỗi gọi hàm siêu ngắn gọn (Chaining):
```rust
fn read_username_short() -> Result<String, io::Error> {
    let mut username = String::new();
    File::open("username.txt")?.read_to_string(&mut username)?;
    Ok(username)
}

// Hoặc ngắn gọn hơn nữa bằng hàm có sẵn của std:
fn read_username_shortest() -> Result<String, io::Error> {
    std::fs::read_to_string("username.txt")
}
```

---

### 13.4. 🏆 Xử Lý Lỗi Thực Chiến Trong Công Nghiệp: `thiserror` & `anyhow`

Trong các dự án thực tế lớn, cộng đồng Rust sử dụng hai crate chuẩn mực để xử lý lỗi:
1. 📦 **`thiserror` (Dành cho người viết Thư viện - Library Crates):** Giúp bạn tự định nghĩa các kiểu enum lỗi tùy chỉnh rõ ràng với macro `#[derive(Error)]`.
2. 🚀 **`anyhow` (Dành cho người viết Ứng dụng - Binary Applications):** Cung cấp kiểu `anyhow::Result<T>` có thể gom mọi loại lỗi khác nhau và đính kèm ngữ cảnh dễ dàng qua `.context("Mô tả lỗi")`.

```rust
// Ví dụ minh họa phong cách thực chiến với thiserror:
/*
use thiserror::Error;

#[derive(Error, Debug)]
pub enum DataStoreError {
    #[error("Không thể kết nối cơ sở dữ liệu")]
    Disconnect(#[from] std::io::Error),
    #[error("Không tìm thấy dữ liệu cho khóa `{0}`")]
    NotFound(String),
}
*/
```

---

# 🏛️ PHẦN VII: TỔ CHỨC DỰ ÁN, KIỂM THỬ & DỰ ÁN MINIGREP

---

## CHƯƠNG 14: 📁 QUẢN LÝ DỰ ÁN VỚI PACKAGES, CRATES, MODULES & WORKSPACES

Khi quy mô dự án phần mềm lớn dần, việc đặt toàn bộ mã nguồn vào một tập tin duy nhất `src/main.rs` là bất khả thi. Rust cung cấp một hệ thống phân cấp tổ chức mã nguồn cực kỳ mạch lạc và chặt chẽ, gồm $4$ cấp độ: **Workspace**, **Package**, **Crate**, và **Module**.

```text
🏢 WORKSPACE (Tập hợp nhiều Packages dùng chung Cargo.lock và thư mục target/)
 └── 📦 PACKAGE (Dự án được định nghĩa bởi Cargo.toml)
      └── 🧱 CRATE (Đơn vị biên dịch độc lập: Binary crate hoặc Library crate)
           └── 📂 MODULE (Cây thư mục tổ chức phạm vi mã nguồn và quyền riêng tư)
```

### 14.1. 📦 Packages và Crates

- **🧱 Crate:** Là đơn vị mã nguồn nhỏ nhất mà trình biên dịch `rustc` xem xét tại một thời điểm. Crate có thể chứa nhiều module. Có hai loại Crate:
  1. *Binary Crate:* Biên dịch thành tập tin nhị phân thực thi được. Crate root mặc định là `src/main.rs`.
  2. *Library Crate:* Biên dịch thành thư viện dùng chung cho các dự án khác sử dụng (không có hàm `main`). Crate root mặc định là `src/lib.rs`.
- **📦 Package:** Là một tập hợp gồm một hoặc nhiều Crates, được quản lý bởi một tập tin `Cargo.toml`. Một Package có thể chứa **nhiều Binary Crates** (đặt trong thư mục `src/bin/`), nhưng **chỉ được chứa tối đa MỘT Library Crate**.

---

### 14.2. 🌳 Hệ Thống Module & Cây Module (Module Tree)

Module cho phép bạn phân nhóm các hàm, cấu trúc dữ liệu, hằng số lại với nhau theo ngữ cảnh, đồng thời thiết lập ranh giới bảo mật (*privacy boundary*).

Ví dụ mô phỏng hệ thống nhà hàng trong thư viện `src/lib.rs`:

```rust
// Định nghĩa module ngoài cùng front_of_house
mod front_of_house {
    // Module con hosting bên trong
    pub mod hosting {
        pub fn add_to_waitlist() {}
        fn seat_at_table() {} // 🔒 private
    }

    // Module con serving
    mod serving {
        fn take_order() {}
        fn serve_order() {}
        fn take_payment() {}
    }
}
```

Cây module tương ứng được sinh ra:
```text
crate (gốc của thư viện src/lib.rs)
 └── front_of_house
      ├── hosting
      │    ├── add_to_waitlist (🔓 public)
      │    └── seat_at_table   (🔒 private)
      └── serving
           ├── take_order
           ├── serve_order
           └── take_payment
```

---

### 14.3. 🔒 Quy Tắc Quyền Riêng Tư (Privacy Rules)

1. **Mặc định là Riêng tư (Private):** Mọi thứ trong Rust (hàm, struct, enum, module, hằng số) mặc định đều là `private` đối với các module cha bên ngoài.
2. **Quyền truy cập của con đối với cha:** Module con luôn luôn có toàn quyền nhìn thấy và sử dụng mọi thứ thuộc về module cha của nó (kể cả những thứ cha để `private`).
3. **Từ khóa `pub`:** Thêm `pub` trước một định danh để cấp quyền cho module bên ngoài truy cập (hoặc `pub(crate)` để chỉ công khai nội bộ trong crate).
4. **Quyền riêng tư của Struct vs. Enum:**
   - **🧱 Struct:** Nếu struct là `pub`, các trường (*fields*) bên trong nó **vẫn mặc định là `private`**. Bạn phải thêm `pub` trước từng trường bạn muốn công khai!
   - **🎭 Enum:** Nếu enum là `pub`, thì **toàn bộ các biến thể (*variants*) bên trong nó tự động là `pub`**!

---

### 14.4. 🧭 Đường Dẫn, Từ Khóa `use` & Cargo Workspaces

Để gọi một hàm trong module khác, ta có thể dùng đường dẫn tuyệt đối hoặc đường dẫn tương đối:
- Đường dẫn tuyệt đối: Bắt đầu từ gốc `crate::front_of_house::hosting::add_to_waitlist();`.
- Đường dẫn tương đối: Bắt đầu từ module hiện tại hoặc dùng `super::` để nhảy lên module cha.

Để không phải gõ lại đường dẫn dài dòng, ta dùng từ khóa `use`:
```rust
// Đưa hàm hoặc struct vào phạm vi hiện tại:
use crate::front_of_house::hosting;

pub fn eat_at_restaurant() {
    hosting::add_to_waitlist(); // ✅ Ngắn gọn và trong sáng!
}
```

#### 🔄 Tái xuất khẩu (Re-exporting) với `pub use`:
Khi bạn xây dựng một thư viện phức tạp, cấu trúc thư mục bên trong có thể sâu nhiều tầng, nhưng bạn muốn người dùng thư viện có thể truy cập các kiểu cốt lõi ngay ở tầng ngoài cùng:
```rust
// Trong src/lib.rs:
pub use crate::front_of_house::hosting::add_to_waitlist;
// Bây giờ người dùng thư viện có thể gọi trực tiếp: my_library::add_to_waitlist();
```

#### 🏢 Quản lý Dự án Lớn với Cargo Workspaces:
Khi hệ thống gồm nhiều package liên kết nhau (ví dụ: `core_engine`, `api_server`, `cli_tool`), bạn khai báo một tập tin `Cargo.toml` ở thư mục gốc:
```toml
[workspace]
resolver = "2"
members = [
    "core_engine",
    "api_server",
    "cli_tool",
]
```
Toàn bộ các thành viên trong Workspace sẽ chia sẻ chung một thư mục biên dịch `target/` và một tập tin `Cargo.lock`, giúp tiết kiệm tối đa thời gian biên dịch!

---

## CHƯƠNG 15: 🧪 KIỂM THỬ TỰ ĐỘNG (AUTOMATED TESTING) & TÀI LIỆU HÓA

Rust tích hợp sẵn hệ thống kiểm thử tự động trực tiếp ngay trong ngôn ngữ và hệ sinh thái Cargo mà không cần cài đặt thêm bất kỳ framework bên ngoài nào.

### 15.1. ✅ Viết Unit Test Trong Rust

Unit test thường được đặt trong cùng tập tin mã nguồn với logic cần test, nằm trong một module mang chỉ thị `#[cfg(test)]`:

```rust
// Logic nghiệp vụ cần kiểm thử
pub fn add_two(a: i32) -> i32 {
    a + 2
}

pub fn greeting(name: &str) -> String {
    format!("Chào {name}!")
}

// Module kiểm thử: chỉ được biên dịch khi chạy lệnh `cargo test`
#[cfg(test)]
mod tests {
    use super::*; // Đưa toàn bộ các hàm ở module cha vào phạm vi kiểm thử

    #[test]
    fn test_add_two() {
        assert_eq!(add_two(2), 4); // Kiểm tra 2 + 2 == 4
    }

    #[test]
    fn test_greeting() {
        let result = greeting("Rust");
        assert!(
            result.contains("Rust"),
            "❌ Chuỗi chào mừng không chứa tên! Kết quả nhận được: '{result}'"
        );
    }

    #[test]
    #[should_panic(expected = "chia cho 0")]
    fn test_divide_by_zero_should_panic() {
        // Test trường hợp hàm bắt buộc phải panic
        panic!("Lỗi chia cho 0!");
    }
}
```

Chạy toàn bộ bài test:
```bash
cargo test
```

---

### 15.2. 📖 Tài Liệu Hóa Mã Nguồn & Kiểm Thử Tài Liệu (Doctests)

Rust hỗ trợ viết chú thích tài liệu bằng Markdown trực tiếp trong code thông qua ký tự `///` *(Lưu ý: Doctest chỉ hoạt động đối với các hàm công khai đặt trong Library crate `src/lib.rs`)*:

```rust
// File: src/lib.rs
/// Cộng thêm 1 vào số nguyên được cung cấp.
///
/// # Ví dụ minh họa (Doctest):
///
/// ```
/// let arg = 5;
/// let answer = hello_cargo::add_one(arg);
/// assert_eq!(6, answer);
/// ```
pub fn add_one(x: i32) -> i32 {
    x + 1
}
```

> ✨ **Tính năng kỳ diệu của Cargo:** Khi bạn chạy lệnh `cargo test`, Cargo sẽ tự động biên dịch và chạy các đoạn mã nằm trong mục ví dụ của tài liệu! Điều này đảm bảo tài liệu hướng dẫn của bạn không bao giờ bị lỗi thời so với mã nguồn thực tế. Bạn có thể sinh tài liệu HTML tuyệt đẹp bằng lệnh `cargo doc --open`.

---

## CHƯƠNG 16: 🔍 DỰ ÁN 2 — XÂY DỰNG CÔNG CỤ DÒNG LỆNH MINIGREP

Dự án này sẽ tổng hợp toàn bộ các kiến thức ta đã học:
- ⌨️ Xử lý tham số dòng lệnh (`std::env`).
- 📂 Đọc tập tin từ hệ thống tập tin (`std::fs`).
- 🏛️ Thiết kế phân tách kiến trúc chuyên nghiệp: `main.rs` (điều hướng I/O) và `lib.rs` (logic nghiệp vụ).
- 🧪 Lập trình hướng kiểm thử (*TDD - Test-Driven Development*).
- 🌍 Đọc biến môi trường hệ thống (`std::env::var`).
- 🚨 Xuất lỗi chuẩn ra luồng `eprintln!`.

Tạo dự án mới:
```bash
cargo new minigrep
cd minigrep
```

---

### 16.1. 🧠 Logic Nghiệp Vụ & Kiểm Thử Trong `src/lib.rs`

Hãy mở `src/lib.rs` và viết mã nguồn với kiến trúc module hoàn chỉnh:

```rust
// File: src/lib.rs
use std::error::Error;
use std::fs;
use std::env;

/// Cấu trúc chứa cấu hình tham số tìm kiếm
pub struct Config {
    pub query: String,
    pub file_path: String,
    pub ignore_case: bool,
}

impl Config {
    /// Hàm phân tích tham số dòng lệnh
    pub fn build(args: &[String]) -> Result<Config, &'static str> {
        if args.len() < 3 {
            return Err("Không đủ tham số! Cú pháp: minigrep <từ_khóa> <đường_dẫn_file>");
        }

        let query = args[1].clone();
        let file_path = args[2].clone();

        // Kiểm tra biến môi trường IGNORE_CASE (nếu có đặt biến môi trường, bỏ qua phân biệt hoa thường)
        let ignore_case = env::var("IGNORE_CASE").is_ok();

        Ok(Config {
            query,
            file_path,
            ignore_case,
        })
    }
}

/// Hàm điều phối thực thi chính
pub fn run(config: Config) -> Result<(), Box<dyn Error>> {
    // Đọc nội dung file thành chuỗi String
    let contents = fs::read_to_string(config.file_path)?;

    // Lựa chọn hàm tìm kiếm tùy thuộc vào cấu hình ignore_case
    let results = if config.ignore_case {
        search_case_insensitive(&config.query, &contents)
    } else {
        search(&config.query, &contents)
    };

    // In từng dòng kết quả tìm được
    for line in results {
        println!("{line}");
    }

    Ok(())
}

/// Hàm tìm kiếm có phân biệt hoa thường
pub fn search<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let mut results = Vec::new();

    for line in contents.lines() {
        if line.contains(query) {
            results.push(line);
        }
    }

    results
}

/// Hàm tìm kiếm KHÔNG phân biệt hoa thường
pub fn search_case_insensitive<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let query = query.to_lowercase();
    let mut results = Vec::new();

    for line in contents.lines() {
        if line.to_lowercase().contains(&query) {
            results.push(line);
        }
    }

    results
}

// ==========================================
// 🧪 KHỐI KIỂM THỬ TỰ ĐỘNG (UNIT TESTS)
// ==========================================
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn case_sensitive() {
        let query = "duct";
        let contents = "\
Rust:
safe, fast, productive.
Pick three.
Duct tape.";

        assert_eq!(vec!["safe, fast, productive."], search(query, contents));
    }

    #[test]
    fn case_insensitive() {
        let query = "rUsT";
        let contents = "\
Rust:
safe, fast, productive.
Pick three.
Trust me.";

        assert_eq!(
            vec!["Rust:", "Trust me."],
            search_case_insensitive(query, contents)
        );
    }
}
```

---

### 16.2. 🚀 Mã Nguồn Điểm Khởi Đầu Trong `src/main.rs`

Mở `src/main.rs`. Tệp tin này chỉ chịu trách nhiệm thu thập tham số và xử lý lỗi in ra màn hình:

```rust
// File: src/main.rs
use std::env;
use std::process;
use minigrep::Config;

fn main() {
    // Thu thập danh sách tham số dòng lệnh truyền vào chương trình
    let args: Vec<String> = env::args().collect();

    // Khởi tạo cấu hình, nếu lỗi thì in ra stderr và thoát chương trình với mã lỗi 1
    let config = Config::build(&args).unwrap_or_else(|err| {
        eprintln!("❌ Lỗi khởi tạo cấu hình: {err}");
        process::exit(1);
    });

    // Thực thi chương trình minigrep
    if let Err(e) = minigrep::run(config) {
        eprintln!("❌ Lỗi ứng dụng: {e}");
        process::exit(1);
    }
}
```

---

### 16.3. ▶️ Chạy Thử Nghiệm Thực Tế Công Cụ `minigrep`

Tạo một tập tin văn bản mẫu `poem.txt` trong thư mục dự án:
```text
I'm nobody! Who are you?
Are you nobody, too?
Then there's a pair of us - don't tell!
They'd banish us, you know.
```

Thực thi tìm kiếm có phân biệt hoa thường:
```bash
cargo run -- to poem.txt
```
*Kết quả:*
```text
Are you nobody, too?
```

Thực thi tìm kiếm không phân biệt hoa thường bằng cách bật biến môi trường:
```bash
# Trên Linux/macOS:
IGNORE_CASE=1 cargo run -- to poem.txt

# Trên Windows PowerShell:
$env:IGNORE_CASE=1; cargo run -- to poem.txt
```
*Kết quả:*
```text
Are you nobody, too?
Then there's a pair of us - don't tell!
```

---

# 🧠 PHẦN VIII: VÒNG ĐỜI, LẬP TRÌNH HÀM & CON TRỎ THÔNG MINH

---

## CHƯƠNG 17: ⏳ VÒNG ĐỜI THAM CHIẾU (LIFETIMES 'A)

**Vòng đời (Lifetime)** là một dạng đặc biệt của Generics. Thay vì trừu tượng hóa kiểu dữ liệu, Lifetime trừu tượng hóa **thời gian tồn tại hợp lệ của các tham chiếu**. Mục tiêu tối thượng của Lifetime là đảm bảo trình biên dịch không bao giờ cho phép một con trỏ lơ lửng (*dangling reference*) tồn tại.

### 17.1. 🔬 Bản Chất Của Lifetime & Bài Toán Hàm `longest`

Hãy xem xét một hàm so sánh và trả về chuỗi dài hơn giữa hai chuỗi:

```rust
// ❌ HÀM CHƯA CÓ CHÚ THÍCH LIFETIME:
fn longest(x: &str, y: &str) -> &str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

Nếu bạn cố biên dịch hàm trên, Rust sẽ từ chối:

```text
error[E0106]: missing lifetime specifier
 --> src/main.rs:1:33
  |
1 | fn longest(x: &str, y: &str) -> &str {
  |               ----     ----     ^ expected named lifetime parameter
  |
  = help: this function's return type contains a borrowed value, but the signature does not say whether it is borrowed from `x` or `y`
```

#### 🧠 Tại sao Rust lại bắt lỗi ở đây?
Khi nhìn vào chữ ký của hàm `longest`, trình biên dịch không thể biết được tham chiếu trả về sẽ mượn từ `x` hay từ `y`. Nếu `x` và `y` có thời gian sống khác nhau (ví dụ: `x` sống lâu hơn `y`), việc sử dụng giá trị trả về sau khi `y` đã bị hủy sẽ gây ra lỗi truy cập vùng nhớ rác!

Do đó, Rust yêu cầu bạn phải **chú thích vòng đời chung** để ràng buộc mối quan hệ giữa chúng:

```rust
// ✅ Cú pháp khai báo generic lifetime <'a>:
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

> 💡 **Ý nghĩa thực sự của `'a`:**  
> `'a` **KHÔNG LÀM THAY ĐỔI** thời gian sống thực tế của các biến. Nó chỉ là một bản hợp đồng toán học cam kết với trình biên dịch:  
> *"Tham chiếu trả về sẽ có thời gian sống hợp lệ bằng với phần giao thời gian sống $\min(\text{lifetime}(x), \text{lifetime}(y))$ của $x$ và $y$!"*

```rust
fn main() {
    let string1 = String::from("chuỗi rất dài");

    {
        let string2 = String::from("xyz");
        let result = longest(string1.as_str(), string2.as_str());
        println!("Chuỗi dài nhất là: {result}"); // ✅ Hợp lệ, string2 vẫn còn sống
    } // string2 bị drop tại đây!

    // println!("{result}"); // ❌ LỖI BIÊN DỊCH nếu bạn dùng result ở đây!
}
```

---

### 17.2. 📜 Ba Quy Tắc Suy Đoán Vòng Đời Tự Động (Lifetime Elision Rules)

Tại sao trong các chương trước, khi viết hàm `first_word(s: &str) -> &str`, ta không hề phải viết `'a` mà Rust vẫn biên dịch được?

Đó là nhờ **$3$ Quy tắc Suy đoán Vòng đời (Elision Rules)** được tích hợp sẵn trong trình biên dịch:
1. **1️⃣ Quy tắc 1 (Input Lifetimes):** Mỗi tham số là một tham chiếu sẽ tự động được trình biên dịch gán cho một tham số vòng đời độc lập. Ví dụ: `fn foo(x: &i32)` trở thành `fn foo<'a>(x: &'a i32)`; `fn foo(x: &i32, y: &i32)` trở thành `fn foo<'a, 'b>(x: &'a i32, y: &'b i32)`.
2. **2️⃣ Quy tắc 2 (Output Lifetime với 1 Input):** Nếu chỉ có **đúng $1$ tham số vòng đời đầu vào**, vòng đời đó sẽ tự động được gán cho toàn bộ các tham chiếu đầu ra. Ví dụ: `fn first_word(s: &str) -> &str` trở thành `fn first_word<'a>(s: &'a str) -> &'a str`.
3. **3️⃣ Quy tắc 3 (Output Lifetime với Phương thức `&self`):** Nếu có nhiều tham số đầu vào, nhưng một trong số đó là `&self` hoặc `&mut self` (phương thức của struct), thì vòng đời của `self` sẽ tự động được gán cho tất cả các tham chiếu đầu ra.

Nếu sau khi áp dụng cả $3$ quy tắc mà trình biên dịch vẫn chưa xác định được vòng đời của tham chiếu trả về (như trường hợp hàm `longest` có $2$ tham số đầu vào), Rust sẽ dừng lại và yêu cầu lập trình viên chú thích tường minh.

---

### 17.3. 🧱 Lifetime Trong Định Nghĩa Struct & Vòng Đời `'static`

Nếu một Struct lưu trữ một tham chiếu thay vì sở hữu dữ liệu trực tiếp, Struct đó bắt buộc phải có chú thích Lifetime để đảm bảo Struct không thể sống lâu hơn dữ liệu mà nó đang mượn:

```rust
struct ImportantExcerpt<'a> {
    part: &'a str, // Tham chiếu part phải sống ít nhất bằng struct này!
}

fn main() {
    let novel = String::from("Gọi tôi là Ishmael. Nhiều năm trước...");
    let first_sentence = novel.split('.').next().expect("Không tìm thấy dấu chấm");

    let i = ImportantExcerpt {
        part: first_sentence,
    };
    println!("📖 Trích đoạn: {}", i.part);
}
```

#### ♾️ Vòng đời tĩnh `'static`:
Vòng đời đặc biệt `'static` biểu thị tham chiếu có thể sống trong **toàn bộ thời gian chạy của chương trình**. Toàn bộ các chuỗi hằng tự vị (`&str`) đều mang vòng đời `'static` vì chúng được nhúng trực tiếp vào phân vùng dữ liệu tĩnh (*rodata segment*) của file nhị phân:
```rust
let s: &'static str = "Tôi có vòng đời tĩnh vĩnh cửu.";
```

---

## CHƯƠNG 18: 🔁 LẬP TRÌNH HÀM: CLOSURES & ITERATORS

Rust chịu ảnh hưởng sâu sắc từ các ngôn ngữ lập trình hàm (*Functional Programming*). Hai vũ khí mạnh mẽ nhất đại diện cho phong cách này là **Closures** và **Iterators**.

### 18.1. 🎭 Closures (Hàm Ẩn Danh)

Closure là một hàm ẩn danh mà bạn có thể lưu vào một biến hoặc truyền làm tham số cho các hàm khác. Khác với hàm thông thường, **Closure có khả năng bắt giữ (capture) các biến từ môi trường bên ngoài** nơi nó được định nghĩa.

Cú pháp Closure sử dụng cặp dấu gạch đứng `|...|`:

```rust
fn main() {
    let x = 4;

    // Closure bắt giữ biến x từ scope ngoài:
    let equal_to_x = |z| z == x;

    let y = 4;
    assert!(equal_to_x(y));
}
```

---

### 18.2. 🧲 Ba Cách Bắt Giữ Môi Trường: `Fn`, `FnMut`, `FnOnce`

Cách Closure bắt giữ biến ánh xạ trực tiếp tới $3$ hình thức truyền tham số của Rust:

1. **🚚 `FnOnce` (Bắt giữ bằng cách lấy Quyền sở hữu - Move):**
   - Closure tiêu thụ các biến bị bắt giữ. Do chỉ có thể chuyển quyền sở hữu một lần duy nhất, Closure này **chỉ có thể được gọi đúng $1$ lần**.
   - Mọi Closure đều tự động cài đặt `FnOnce`.
2. **✍️ `FnMut` (Bắt giữ bằng Tham chiếu khả biến `&mut`):**
   - Closure có thể thay đổi giá trị của các biến trong môi trường ngoài.
   - Có thể được gọi nhiều lần.
3. **📖 `Fn` (Bắt giữ bằng Tham chiếu bất biến `&`):**
   - Closure chỉ đọc dữ liệu từ môi trường ngoài, không sửa đổi và không tiêu thụ.
   - Có thể được gọi nhiều lần và an toàn khi chia sẻ giữa các luồng.

#### 🚀 Từ khóa `move` trong Closure:
Thêm từ khóa `move` trước dấu `|` để ép Closure phải chiếm đoạt toàn bộ quyền sở hữu của các biến mà nó sử dụng (thường dùng khi truyền Closure sang một luồng mới):
```rust
use std::thread;

fn main() {
    let list = vec![1, 2, 3];

    // Bắt buộc chuyển quyền sở hữu của `list` vào bên trong luồng con:
    thread::spawn(move || println!("🧵 Từ luồng con: {list:?}"))
        .join()
        .unwrap();
}
```

---

### 18.3. ⚡ Bộ Lặp Iterators & Tính Lười Biếng (Lazy Evaluation)

Trong Rust, **Iterator có tính chất lười biếng (lazy)**: Việc tạo ra một iterator không hề thực hiện bất kỳ phép tính nào cho đến khi bạn gọi một phương thức tiêu thụ nó!

```rust
fn main() {
    let v1 = vec![1, 2, 3];

    // Tạo iterator (chưa có phép tính nào xảy ra):
    let v1_iter = v1.iter();

    // Vòng lặp for tiêu thụ iterator:
    for val in v1_iter {
        println!("Giá trị: {val}");
    }
}
```

#### 🔧 Ba phương thức tạo Iterator từ một Collection:
- **`.iter()`:** Tạo iterator sinh ra các tham chiếu bất biến `&T`.
- **`.iter_mut()`:** Tạo iterator sinh ra các tham chiếu khả biến `&mut T`.
- **`.into_iter()`:** Tiêu thụ collection và sinh ra các giá trị sở hữu `T`.

#### 🔄 Hai nhóm phương thức chính của Iterator:
1. **🍽️ Phương thức Tiêu thụ (Consuming Adaptors):** Gọi phương thức `.next()` bên dưới và tính ra kết quả cuối cùng:
   - `.sum()`: Tính tổng.
   - `.fold()`: Gộp phần tử với bộ tích lũy.
   - `.collect()`: Thu gom các phần tử vào một cấu trúc dữ liệu mới (như `Vec`, `HashMap`).
2. **⛓️ Phương thức Điều hợp (Iterator Adaptors):** Biến đổi iterator ban đầu thành một iterator mới:
   - `.map()`: Biến đổi từng phần tử qua một Closure.
   - `.filter()`: Giữ lại các phần tử thỏa mãn điều kiện.
   - `.enumerate()`, `.zip()`, `.take()`, `.skip()`.

#### ✨ Chuỗi biến đổi tối ưu tuyệt đẹp (Method Chaining):
```rust
fn main() {
    let v: Vec<i32> = vec![1, 2, 3, 4, 5, 6];

    // Lấy các số chẵn, nhân đôi chúng, và thu gom vào vector mới:
    let result: Vec<i32> = v.into_iter()
        .filter(|x| x % 2 == 0)
        .map(|x| x * 2)
        .collect();

    println!("🎯 Kết quả: {result:?}"); // [4, 8, 12]
}
```
> 🚀 **Hiệu năng thực thi:** Nhờ cơ chế tối ưu hóa vòng lặp (*Loop Unrolling & Vectorization*) của trình biên dịch LLVM, chuỗi lặp `.filter().map()` ở trên biên dịch ra mã máy chạy nhanh ngang ngửa (thậm chí nhanh hơn do bỏ qua kiểm tra biên) so với một vòng lặp `for` viết tay bằng ngôn ngữ C!

---

## CHƯƠNG 19: 🧭 CON TRỎ THÔNG MINH (SMART POINTERS)

Con trỏ thông minh là các cấu trúc dữ liệu hoạt động giống như một con trỏ nhưng chứa thêm metadata và các tính năng bổ sung. Trong Rust, con trỏ thông minh thường cài đặt hai Trait quan trọng: **`Deref`** và **`Drop`**.

### 19.1. 📦 Con Trỏ `Box<T>` (Cấp Phát Trên Heap)

`Box<T>` là con trỏ thông minh cơ bản nhất, dùng để cấp phát một giá trị có kiểu `T` lên bộ nhớ **Heap**. Con trỏ `Box` nằm trên Stack sẽ trỏ tới ô nhớ Heap đó:

```rust
fn main() {
    let b = Box::new(5); // Số 5 được lưu trên Heap
    println!("b = {}", *b); // Giải tham chiếu bằng toán tử `*`
} // b ra khỏi scope tại đây, bộ nhớ Heap của số 5 được giải phóng tự động!
```

#### 🌲 Ứng dụng quan trọng nhất: Xây dựng Cấu trúc Dữ liệu Đệ quy (Recursive Types):
Tại thời điểm biên dịch, Rust cần biết kích thước chính xác của mọi kiểu dữ liệu. Nếu bạn định nghĩa một kiểu danh sách liên kết đệ quy:
```rust
// ❌ LỖI BIÊN DỊCH: recursive type has infinite size!
enum List {
    Cons(i32, List),
    Nil,
}
```
Trình biên dịch không thể xác định được `List` chiếm bao nhiêu byte bộ nhớ vì nó lồng nhau vô tận.

**✅ Giải pháp:** Bọc kiểu đệ quy vào trong `Box<T>`:
```rust
// HỢP LỆ VÌ CON TRỎ BOX CÓ KÍCH THƯỚC CỐ ĐỊNH (8 BYTES TRÊN CPU 64-BIT):
enum List {
    Cons(i32, Box<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let list = Cons(1, Box::new(Cons(2, Box::new(Cons(3, Box::new(Nil))))));
}
```

---

### 19.2. 🎯 Trait `Deref` & Ép Kiểu Giải Tham Chiếu (Deref Coercion)

Cài đặt trait `Deref` cho phép bạn tùy chỉnh hành vi của toán tử giải tham chiếu `*`.

Đặc biệt, Rust hỗ trợ tính năng **Deref Coercion**: Tự động chuyển đổi một tham chiếu của một kiểu có cài đặt `Deref` thành tham chiếu của kiểu đích.
Ví dụ: `&String` tự động chuyển thành `&str` vì `String` cài đặt `Deref<Target = str>`; `&Box<T>` tự động chuyển thành `&T`.

---

### 19.3. 🧹 Trait `Drop` (Mô Hình Quản Lý Tài Nguyên RAII)

Trait `Drop` cho phép bạn định nghĩa mã nguồn dọn dẹp tài nguyên (đóng file, ngắt kết nối mạng, trả lại vùng nhớ) khi một đối tượng đi ra khỏi phạm vi (*scope*):

```rust
struct CustomSmartPointer {
    data: String,
}

impl Drop for CustomSmartPointer {
    fn drop(&mut self) {
        println!("🧹 Giải phóng CustomSmartPointer chứa dữ liệu: `{}`!", self.data);
    }
}

fn main() {
    let c = CustomSmartPointer { data: String::from("dữ liệu của tôi") };
    println!("Khởi tạo con trỏ xong.");

    // Muốn giải phóng sớm trước khi hết hàm? Dùng hàm `std::mem::drop`:
    drop(c);
    println!("Đã chủ động gọi drop.");
}
```

---

### 19.4. 🤝 `Rc<T>` — Đa Sở Hữu Đơn Luồng (Reference Counting)

Quy tắc của Rust: Mỗi giá trị chỉ có DUY NHẤT một chủ sở hữu. Nhưng có những bài toán (như đồ thị - *Graph*, hoặc cây - *Tree*) nơi nhiều nút cùng chia sẻ quyền sở hữu một nút chung.

`Rc<T>` (*Reference Counted*) đếm số lượng tham chiếu đến một vùng nhớ trên Heap. Khi số lượng tham chiếu giảm về đúng $0$, vùng nhớ đó mới bị giải phóng:

```rust
use std::rc::Rc;

enum List {
    Cons(i32, Rc<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let a = Rc::new(Cons(5, Rc::new(Cons(10, Rc::new(Nil)))));
    println!("🔢 Số lượng chủ sở hữu của a ban đầu: {}", Rc::strong_count(&a)); // 1

    let b = Cons(3, Rc::clone(&a)); // Rc::clone chỉ tăng bộ đếm tham chiếu lên 1 (O(1)), KHÔNG copy dữ liệu!
    println!("🔢 Số lượng sau khi b tạo: {}", Rc::strong_count(&a)); // 2

    {
        let c = Cons(4, Rc::clone(&a));
        println!("🔢 Số lượng khi có c: {}", Rc::strong_count(&a)); // 3
    } // c ra khỏi scope tại đây, bộ đếm tự động giảm 1!

    println!("🔢 Số lượng sau khi c bị hủy: {}", Rc::strong_count(&a)); // 2
}
```
> ⚠️ **Lưu ý cốt tử:** `Rc<T>` **CHỈ DÙNG TRONG MÔI TRƯỜNG ĐƠN LUỒNG**. Nếu dùng trong môi trường đa luồng, bạn bắt buộc phải dùng `Arc<T>`!

---

### 19.5. 🔓 `Cell<T>` & `RefCell<T>` — Mẫu Hình Khả Biến Nội Tại (Interior Mutability)

Mẫu hình **Khả biến nội tại** cho phép bạn thay đổi dữ liệu bên trong ngay cả khi bạn chỉ đang giữ một tham chiếu bất biến đến đối tượng đó.

- **`Cell<T>`:** Dành cho các kiểu có `Copy`. Thay đổi giá trị bằng cách di chuyển giá trị ra/vào (`.get()`, `.set()`) mà không cần mượn tham chiếu, chi phí bằng $0$.
- **`RefCell<T>`:** Chuyển việc kiểm tra các quy tắc mượn từ **thời điểm biên dịch (Compile-time)** sang **thời điểm chạy (Runtime)**. Tại runtime, nếu bạn vi phạm quy tắc mượn (vừa đọc vừa ghi cùng lúc), chương trình sẽ bị `panic!`.

Kết hợp `Rc<T>` và `RefCell<T>` để có thể **vừa đa sở hữu vừa thay đổi được dữ liệu**:
```rust
use std::rc::Rc;
use std::cell::RefCell;

fn main() {
    // Biến value được bọc trong Rc và RefCell
    let value = Rc::new(RefCell::new(5));

    let a = Rc::clone(&value);
    let b = Rc::clone(&value);

    // Mượn khả biến tại runtime qua phương thức .borrow_mut() và cộng thêm 10:
    *value.borrow_mut() += 10;

    println!("Giá trị a: {:?}", a.borrow()); // 15
    println!("Giá trị b: {:?}", b.borrow()); // 15
}
```

---

### 19.6. 🛡️ Giải Quyết Vòng Lặp Tham Chiếu với `Weak<T>` & Tối Ưu Hóa Với `Cow<'a, B>`

#### 1️⃣ Chống rò rỉ bộ nhớ với `Weak<T>`:
Nếu hai đối tượng `Rc` trỏ chéo vào nhau, bộ đếm tham chiếu `strong_count` sẽ không bao giờ về $0$, dẫn đến rò rỉ bộ nhớ vĩnh viễn!
Để khắc phục, Rust cung cấp con trỏ yếu **`Weak<T>`** qua phương thức `Rc::downgrade(&rc)`. `Weak<T>` không tăng `strong_count` mà chỉ tăng `weak_count`, do đó không ngăn cản việc thu hồi bộ nhớ. Khi cần đọc dữ liệu từ `Weak<T>`, bạn gọi `.upgrade()` trả về `Option<Rc<T>>`.

#### 2️⃣ Con trỏ Thông minh `Cow<'a, B>` (Clone-On-Write):
`std::borrow::Cow` là con trỏ thông minh cực kỳ hữu ích khi bạn muốn **chỉ mượn dữ liệu nếu không cần sửa đổi, và chỉ cấp phát bộ nhớ mới (Clone) khi thực sự cần sửa đổi**:

```rust
use std::borrow::Cow;

fn sanitize_input(input: &str) -> Cow<'_, str> {
    if input.contains("bad_word") {
        // Chỉ cấp phát String mới trên Heap khi cần thay thế từ xấu:
        Cow::Owned(input.replace("bad_word", "***"))
    } else {
        // Nếu chuỗi sạch, chỉ mượn nguyên bản (Zero allocation!):
        Cow::Borrowed(input)
    }
}
```

---

# ⚡ PHẦN IX: LẬP TRÌNH ĐỒNG THỜI & BẤT ĐỒNG BỘ

---

## CHƯƠNG 20: 🧵 LẬP TRÌNH ĐA LUỒNG (MULTI-THREADING CONCURRENCY)

Lập trình đồng thời (*Concurrent Programming*) và lập trình song song (*Parallel Programming*) luôn là bài toán phức tạp đối với hầu hết các kỹ sư phần mềm vì các lỗi nguy hiểm như **Data Race**, **Deadlock**, và **Race Condition** cực kỳ khó tái hiện và gỡ lỗi.

Triết lý của Rust là **Fearless Concurrency (Đồng thời không sợ hãi)**: Nhờ có hệ thống Ownership và Type System mạnh mẽ, toàn bộ các lỗi vi phạm an toàn luồng sẽ bị chặn đứng ngay từ thời điểm biên dịch!

### 20.1. 🚀 Tạo Luồng Mới Với `thread::spawn` và `JoinHandle`

Để tạo một luồng hệ điều hành ($1:1$ OS Thread) mới, ta dùng hàm `std::thread::spawn` và truyền vào một Closure chứa công việc cần thực thi:

```rust
use std::thread;
use std::time::Duration;

fn main() {
    // Khởi tạo một luồng phụ mới:
    let handle = thread::spawn(|| {
        for i in 1..10 {
            println!("🧵 Luồng phụ đếm số: {i}");
            thread::sleep(Duration::from_millis(1));
        }
    });

    // Luồng chính tiếp tục chạy song song:
    for i in 1..5 {
        println!("👑 Luồng chính đếm số: {i}");
        thread::sleep(Duration::from_millis(1));
    }

    // Chờ luồng phụ thực thi xong hoàn toàn trước khi kết thúc chương trình:
    handle.join().unwrap();
}
```

> ⚠️ **Lưu ý quan trọng:** Nếu không gọi `handle.join()`, khi luồng chính `main` kết thúc, toàn bộ các luồng phụ sẽ bị hệ điều hành tắt ngang ngay lập tức dù chúng chưa chạy xong!

---

### 20.2. 🚚 Chuyển Quyền Sở Hữu Vào Luồng Bằng Từ Khóa `move`

Khi luồng phụ cần sử dụng dữ liệu từ luồng chính, Rust bắt buộc bạn phải thêm từ khóa `move` trước Closure để **chuyển giao hoàn toàn quyền sở hữu** dữ liệu đó vào luồng phụ. Điều này đảm bảo dữ liệu không bao giờ bị luồng chính hủy trước khi luồng phụ chạy xong:

```rust
use std::thread;

fn main() {
    let v = vec![1, 2, 3];

    // Bắt buộc dùng từ khóa `move` để chuyển quyền sở hữu của `v` vào luồng con:
    let handle = thread::spawn(move || {
        println!("📦 Vector bên trong luồng con: {v:?}");
    });

    // println!("{v:?}"); // ❌ LỖI BIÊN DỊCH! v đã bị move sang luồng con!

    handle.join().unwrap();
}
```

> ✨ **Mẹo nâng cao — `thread::scope` (Scoped Threads):**  
> Nếu bạn muốn các luồng con **mượn dữ liệu cục bộ (`&T`)** mà không cần `move` hay `Arc`, Rust cung cấp `std::thread::scope`. Trình biên dịch đảm bảo tất cả các luồng trong `scope` đều tự động `join` trước khi `scope` kết thúc!
> ```rust
> use std::thread;
> 
> fn main() {
>     let mut a = vec![1, 2, 3];
>     let mut x = 0;
> 
>     thread::scope(|s| {
>         s.spawn(|| {
>             println!("Luồng 1 mượn đọc a: {a:?}");
>         });
>         s.spawn(|| {
>             x += a[0] + a[2]; // Luồng 2 mượn khả biến x!
>         });
>     }); // Tự động join tất cả các luồng tại đây!
> 
>     println!("Sau scope: a = {a:?}, x = {x}");
> }
> ```

---

### 20.3. 📨 Truyền Thông Điệp Qua Kênh (Message Passing với `mpsc`)

Khẩu hiệu nổi tiếng của ngôn ngữ Go cũng là triết lý được Rust áp dụng triệt để:
> 💬 *"Đừng giao tiếp bằng cách chia sẻ bộ nhớ; hãy chia sẻ bộ nhớ bằng cách giao tiếp."*

Rust cung cấp kênh giao tiếp **`mpsc` (Multiple Producer, Single Consumer — Đa đầu gửi, Đơn đầu nhận)** trong thư viện chuẩn `std::sync::mpsc`:

```rust
use std::sync::mpsc;
use std::thread;
use std::time::Duration;

fn main() {
    // Khởi tạo kênh: tx (transmitter - đầu gửi), rx (receiver - đầu nhận)
    let (tx, rx) = mpsc::channel();

    // Nhân bản thêm một đầu gửi thứ hai (Multiple Producers):
    let tx2 = tx.clone();

    thread::spawn(move || {
        let vals = vec![
            String::from("Xin chào"),
            String::from("từ"),
            String::from("luồng 1"),
        ];

        for val in vals {
            tx.send(val).unwrap(); // Gửi từng chuỗi qua kênh
            thread::sleep(Duration::from_millis(200));
        }
    });

    thread::spawn(move || {
        let vals = vec![
            String::from("Thêm dữ liệu"),
            String::from("từ luồng 2"),
        ];

        for val in vals {
            tx2.send(val).unwrap();
            thread::sleep(Duration::from_millis(200));
        }
    });

    // Luồng chính lắng nghe và nhận toàn bộ thông điệp cho đến khi các đầu gửi đóng lại:
    for received in rx {
        println!("📩 Đã nhận: {received}");
    }
}
```

*🔒 An toàn tuyệt đối:* Sau khi gọi `tx.send(val)`, biến `val` lập tức bị Move quyền sở hữu vào kênh và chuyển sang luồng nhận. Bạn không thể vô tình sửa đổi hay đọc `val` ở luồng gửi được nữa!

---

### 20.4. 🔐 Chia Sẻ Trạng Thái An Toàn Với `Arc<Mutex<T>>`

Khi bạn bắt buộc phải cho nhiều luồng cùng truy cập và sửa đổi một vùng nhớ chung, bạn cần kết hợp hai công cụ:
1. 🔒 **`Mutex<T>` (Mutual Exclusion):** Khóa tương hỗ. Tại một thời điểm, chỉ cho phép **DUY NHẤT một luồng** được giữ khóa (`MutexGuard`) để đọc/ghi dữ liệu. Khi `MutexGuard` ra khỏi scope, khóa tự động được mở (*auto-unlock*)!
2. ⚛️ **`Arc<T>` (Atomic Reference Counting):** Con trỏ đếm tham chiếu nguyên tử an toàn luồng (*thread-safe*), cho phép nhiều luồng cùng chia sẻ quyền sở hữu `Mutex<T>`.

```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    // Bọc bộ đếm số 0 trong Mutex và Arc:
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];

    for _ in 0..10 {
        let counter = Arc::clone(&counter); // Tăng bộ đếm tham chiếu nguyên tử
        let handle = thread::spawn(move || {
            // Yêu cầu lấy khóa Mutex (chặn luồng cho đến khi đến lượt):
            let mut num = counter.lock().unwrap();
            *num += 1; // Cộng thêm 1 một cách an toàn
        }); // `num` (MutexGuard) ra khỏi scope tại đây -> Tự động mở khóa Mutex!
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    println!("🎯 Kết quả bộ đếm cuối cùng: {}", *counter.lock().unwrap()); // Luôn luôn bằng 10!
}
```

---

### 20.5. 🧬 Hai Marker Traits Nền Tảng: `Send` Và `Sync`

Toàn bộ các tính năng an toàn đa luồng của Rust đều được trình biên dịch kiểm chứng dựa trên $2$ marker traits đặc biệt trong `std::marker`:

1. **🚚 `Send`:** Biểu thị kiểu dữ liệu có thể **chuyển giao quyền sở hữu (Move) một cách an toàn sang một luồng khác**. Hầu hết mọi kiểu trong Rust đều là `Send`, ngoại trừ con trỏ thô (*raw pointers*) và `Rc<T>`.
2. **🤝 `Sync`:** Biểu thị kiểu dữ liệu có thể **chia sẻ tham chiếu bất biến (`&T`) an toàn giữa nhiều luồng cùng lúc**. Một kiểu `T` là `Sync` khi và chỉ khi `&T` là `Send`. `Arc<T>` và `Mutex<T>` đều là `Send + Sync`, trong khi `RefCell<T>` và `Cell<T>` thì **KHÔNG phải là `Sync`**.

---

## CHƯƠNG 21: 🚀 LẬP TRÌNH BẤT ĐỒNG BỘ (ASYNC / AWAIT)

Trong khi lập trình đa luồng (Threads) tối ưu cho các tác vụ nặng về tính toán (*CPU-bound*), thì lập trình bất đồng bộ (**Async / Await**) là giải pháp tối thượng cho các tác vụ nghẽn I/O (*I/O-bound*) như mạng Internet, Web server, Microservices, Database. Một luồng OS có thể quản lý đồng thời hàng triệu tác vụ bất đồng bộ (*Tasks*) với chi phí bộ nhớ cực thấp.

### 21.1. ⚙️ Mô Hình Thăm Dò Của Rust (The Polling Model & Future Trait)

Khác với JavaScript hay C# nơi `Promise`/`Task` chạy ngầm ngay khi được tạo ra (*eager*), **trong Rust, một `Future` hoàn toàn bất động và lười biếng (inert/lazy) cho đến khi nó được một bộ điều phối (Executor) thăm dò (`poll`)**!

Trait `Future` cốt lõi trong thư viện chuẩn `std::future::Future`:

```rust
use std::pin::Pin;
use std::task::{Context, Poll};

pub trait Future {
    type Output;

    // Phương thức thăm dò trạng thái của Future
    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output>;
}

pub enum Poll<T> {
    Ready(T), // ✅ Tác vụ đã hoàn tất, trả về kết quả T
    Pending,  // ⏳ Tác vụ vẫn đang đợi I/O, sẽ đánh thức lại qua Waker trong Context
}
```

---

### 21.2. ✨ Cú Pháp `async fn` Và Hậu Tố `.await`

- Từ khóa `async` biến một hàm hoặc khối lệnh thành một đối tượng cài đặt `Future<Output = T>`.
- Hậu tố `.await` (đặt sau biểu thức bằng dấu chấm, cực kỳ thuận tiện khi nối chuỗi phương thức `fetch().await?.json().await?`) tạm dừng hàm hiện tại, nhường quyền điều khiển CPU lại cho Async Runtime để làm việc khác trong khi đợi I/O:

```rust
async fn fetch_user_name(user_id: u32) -> String {
    format!("Rustacean_{user_id}")
}

async fn greet_user(user_id: u32) {
    // Tạm dừng không chặn luồng (non-blocking) cho đến khi có kết quả:
    let name = fetch_user_name(user_id).await;
    println!("👋 Xin chào {name}!");
}
```

---

### 21.3. ⚡ Hệ Sinh Thái Async Runtime `Tokio`

Rust chuẩn không tích hợp sẵn bộ điều phối (*Async Executor/Runtime*) trong thư viện chuẩn để giữ cho ngôn ngữ gọn nhẹ (phù hợp cho cả vi điều khiển nhúng). Thay vào đó, cộng đồng sử dụng runtime chuẩn công nghiệp là **`Tokio`**.

Cấu hình trong `Cargo.toml`:
```toml
[dependencies]
tokio = { version = "1.40", features = ["full"] }
```

Ví dụ chạy đa tác vụ bất đồng bộ với `Tokio`:

```rust
use tokio::time::{sleep, Duration};

async fn download_file(file_name: &str, delay_ms: u64) -> String {
    println!("⬇️ Bắt đầu tải: {file_name}...");
    sleep(Duration::from_millis(delay_ms)).await;
    println!("✅ Hoàn tất tải: {file_name}!");
    format!("Nội dung của {file_name}")
}

#[tokio::main]
async fn main() {
    // 1. Chạy đồng thời hai tác vụ trên cùng 1 luồng với `tokio::join!`:
    let (res1, res2) = tokio::join!(
        download_file("rust_book.pdf", 500),
        download_file("cargo_guide.pdf", 300),
    );
    println!("📦 Kết quả nhận được: '{res1}' & '{res2}'");

    // 2. Tạo tác vụ chạy nền độc lập trên hồ luồng của Tokio với `tokio::spawn`:
    let task_handle = tokio::spawn(async {
        download_file("background_data.zip", 200).await
    });

    let bg_result = task_handle.await.unwrap();
    println!("🚀 Tác vụ nền trả về: {bg_result}");
}
```

#### 🏁 Chạy đua tác vụ với `tokio::select!`:
Chờ tác vụ nào hoàn thành trước thì lấy kết quả đó và tự động hủy (*cancel*) tác vụ còn lại (rất hữu ích khi cài đặt cơ chế **Timeout**):

```rust
use tokio::time::{sleep, Duration};

#[tokio::main]
async fn main() {
    tokio::select! {
        val = async {
            sleep(Duration::from_millis(100)).await;
            "Tác vụ mạng hoàn thành"
        } => {
            println!("🎉 Thành công: {val}");
        }
        _ = sleep(Duration::from_millis(500)) => {
            println!("⏰ Hết thời gian chờ (Timeout)!");
        }
    }
}
```

> ⚠️ **Quy tắc vàng trong Async Rust:** Tuyệt đối không gọi các hàm chặn luồng hệ điều hành (như `std::thread::sleep`, `std::sync::mpsc`) hoặc giữ khóa `std::sync::MutexGuard` băng qua điểm chờ `.await` bên trong hàm `async` vì nó sẽ làm đóng băng toàn bộ luồng điều phối của Async Executor! Hãy luôn sử dụng phiên bản bất đồng bộ tương ứng từ runtime như `tokio::time::sleep`, `tokio::sync::mpsc`, hoặc `tokio::sync::Mutex`.

---

### 21.4. 📌 Khái Niệm `Pin<P>` Và `Unpin`

Tại sao ta lại thấy `self: Pin<&mut Self>` trong hàm `poll` của Trait `Future`?

Khi một hàm `async` được biên dịch, trình biên dịch Rust chuyển đổi toàn bộ hàm đó thành một **Máy trạng thái (State Machine)**. Nếu hàm có các biến cục bộ tham chiếu chéo lẫn nhau qua điểm `.await`, nó sẽ tạo ra **cấu trúc tự tham chiếu (Self-referential struct)**: Một trường bên trong struct trỏ trực tiếp vào một trường khác trong chính struct đó!

```text
TRƯỚC KHI MOVE:                     SAU KHI BỊ MOVE SANG ĐỊA CHỈ MỚI:
+-------------------+               +-------------------+
| x: "hello" (0x01) | <---+         | x: "hello" (0x99) |
| ptr_to_x: 0x01    | ----+         | ptr_to_x: 0x01    | ---> 💥 Trỏ vào địa chỉ cũ 0x01 (Dangling!)
+-------------------+               +-------------------+
```

Nếu struct tự tham chiếu này bị di chuyển (*move*) sang vị trí ô nhớ khác, con trỏ nội bộ sẽ trỏ vào vùng nhớ cũ (gây *dangling pointer* và lỗi bộ nhớ)!

**📌 `Pin<P>` (Ghim)** là một kiểu bọc con trỏ thông minh, cam kết với trình biên dịch rằng: **Đối tượng nằm bên trong nó (nếu không cài đặt `Unpin`) sẽ bị ghim cố định tại một địa chỉ bộ nhớ và tuyệt đối không bao giờ bị di chuyển cho đến khi nó bị hủy (`Drop`)!** Điều này đảm bảo an toàn tuyệt đối $100\%$ cho các máy trạng thái bất đồng bộ mà không tốn chi phí runtime.

---

# 🔥 PHẦN X: NÂNG CAO, MACROS & DỰ ÁN WEB SERVER

---

## CHƯƠNG 22: ⚠️ UNSAFE RUST & TƯƠNG TÁC CẤP THẤP (FFI)

Mọi quy tắc an toàn bộ nhớ mà chúng ta đã học từ đầu giáo trình đến giờ đều thuộc về **Safe Rust**. Trình biên dịch Rust cực kỳ nghiêm khắc và thận trọng: nếu nó không thể chứng minh $100\%$ toán học rằng đoạn mã an toàn, nó sẽ từ chối biên dịch.

Tuy nhiên, phần cứng máy tính về bản chất là không an toàn. Để có thể viết hệ điều hành, trình điều khiển thiết bị (*driver*), hoặc xây dựng các thư viện cốt lõi hiệu năng cao (như chính `Vec` hay `String`), Rust cung cấp một khu vực được kiểm soát chặt chẽ gọi là **Unsafe Rust**.

### 22.1. ⚡ Năm Siêu Năng Lực Của Unsafe (5 Superpowers)

Khi bạn mở một khối lệnh với từ khóa `unsafe { ... }`, trình biên dịch **không hề tắt bộ kiểm tra kiểu hay tắt Borrow Checker**. `unsafe` chỉ cấp cho bạn đúng **$5$ siêu năng lực** mà Safe Rust không cho phép:

1. **🎯 Giải tham chiếu con trỏ thô (Dereference raw pointers `*const T` và `*mut T`):**
   - Con trỏ thô có thể là null, không cần tuân theo quy tắc mượn, và không được Rust quản lý thời gian sống.
2. **⚠️ Gọi một hàm hoặc phương thức không an toàn (`unsafe fn`):**
3. **🌐 Truy cập hoặc sửa đổi một biến tĩnh khả biến (`static mut`):** *(Lưu ý: Trong Rust hiện đại, hãy ưu tiên dùng `std::sync::OnceLock`, `LazyLock` hoặc `Atomic` thay cho `static mut`)*.
4. **📜 Cài đặt một đặc tính không an toàn (`unsafe trait`):**
5. **🧱 Truy cập các trường của kiểu `union` (tương thích C union):**

#### 🔬 Ví dụ giải tham chiếu con trỏ thô:
```rust
fn main() {
    let mut num = 5;

    // Tạo con trỏ thô hoàn toàn an toàn (không cần unsafe):
    let r1 = &raw const num; // *const i32
    let r2 = &raw mut num;   // *mut i32

    // ⚠️ GIẢI THAM CHIẾU CON TRỎ THÔ BẮT BUỘC PHẢI TRONG KHỐI UNSAFE:
    unsafe {
        println!("r1 trỏ tới: {}", *r1);
        *r2 = 10;
        println!("r2 sửa thành: {}", *r2);
    }
}
```

---

### 22.2. 🛡️ Nguyên Lý Đóng Gói An Toàn (Soundness Principle)

Khẩu hiệu của các kỹ sư Rust là: **Đóng gói mã Unsafe bên trong một API an toàn (Safe Abstraction)**.
Người dùng bên ngoài không cần biết bên trong bạn dùng con trỏ thô hay mã máy gì, họ chỉ cần gọi hàm an toàn và trình biên dịch đảm bảo họ không thể gây ra lỗi bộ nhớ.

Ví dụ hàm `split_at_mut` trong thư viện chuẩn: Chia một lát cắt mảng thành $2$ nửa khả biến độc lập:
```rust
use std::slice;

fn split_at_mut(values: &mut [i32], mid: usize) -> (&mut [i32], &mut [i32]) {
    let len = values.len();
    let ptr = values.as_mut_ptr();

    assert!(mid <= len); // ✅ Đảm bảo an toàn không vượt biên!

    // SAFETY: `mid` đã được kiểm tra nằm trong giới hạn `0..=len`,
    // và hai lát cắt `[0..mid]` cùng `[mid..len]` hoàn toàn tách biệt, không chồng lấn vùng nhớ!
    unsafe {
        (
            slice::from_raw_parts_mut(ptr, mid),
            slice::from_raw_parts_mut(ptr.add(mid), len - mid),
        )
    }
}
```

---

### 22.3. 🔌 Tương Tác Cấp Thấp Với C/C++ Qua FFI (Foreign Function Interface)

Rust có thể gọi trực tiếp các hàm từ thư viện C (hoặc xuất hàm Rust cho C/Python/Node.js gọi) mà không tốn bất kỳ chi phí trung gian nào (*Zero-overhead FFI*):

```rust
use std::ffi::c_int;

// Khai báo chữ ký hàm bên ngoài của C (chuẩn Rust 2024 `unsafe extern`)
unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn main() {
    // Gọi hàm C abs() trong khối unsafe:
    let result = unsafe { abs(-42) };
    println!("🔌 Giá trị tuyệt đối từ thư viện chuẩn C: {result}");
}
```

---

## CHƯƠNG 23: 🪄 LẬP TRÌNH SIÊU HÌNH VỚI MACROS (METAPROGRAMMING)

Macros là cách viết mã nguồn để tự động sinh ra mã nguồn khác (*Code that writes code*). Khác với hàm thực thi tại runtime, Macros được mở rộng (*expanded*) hoàn toàn tại compile-time.

### 23.1. 📜 Declarative Macros Với `macro_rules!`

Đây là dạng macro phổ biến nhất (như `vec!`, `println!`), sử dụng khớp mẫu trên Cây cú pháp trừu tượng (*AST - Abstract Syntax Tree*):

```rust
// Định nghĩa macro tạo vector đơn giản my_vec!
#[macro_export]
macro_rules! my_vec {
    // Khớp mẫu: lặp lại biểu thức $x phân cách bởi dấu phẩy
    ( $( $x:expr ),* ) => {
        {
            let mut temp_vec = Vec::new();
            $(
                temp_vec.push($x);
            )*
            temp_vec
        }
    };
}

fn main() {
    let v = my_vec![10, 20, 30];
    println!("🪄 Vector từ macro tự chế: {v:?}");
}
```

---

### 23.2. ⚙️ Procedural Macros (Macro Thủ Tục)

Procedural Macros hoạt động như một plugin của trình biên dịch: nhận vào một luồng token (`TokenStream`), phân tích cú pháp, và trả về một luồng token mới:
1. **🏷️ Custom Derive (`#[derive(CustomTrait)]`):** Tự động sinh mã cài đặt trait (ví dụ nổi tiếng: `serde::Serialize`, `serde::Deserialize`).
2. **🔖 Attribute-like Macros (`#[route(GET, "/")]`):** Thêm thuộc tính tùy biến lên hàm hoặc struct (thường dùng trong web framework như Actix-web, Axum, Rocket).
3. **⚡ Function-like Macros (`sql!(SELECT * FROM users)`):** Trông giống macro thường nhưng có thể phân tích cú pháp SQL phức tạp và kiểm tra bảng cơ sở dữ liệu ngay lúc biên dịch (như crate `sqlx`)!

---

## CHƯƠNG 24: 🌐 DỰ ÁN 3 — XÂY DỰNG MULTITHREADED WEB SERVER HOÀN CHỈNH

Trong dự án đỉnh cao này, chúng ta sẽ tự tay xây dựng một **Web Server Đa luồng** chuẩn HTTP/1.1 có khả năng xử lý đồng thời nhiều kết nối và tắt máy an toàn (*Graceful Shutdown*) mà không cần dùng bất kỳ thư viện framework bên ngoài nào, chỉ sử dụng thư viện chuẩn `std`.

Khởi tạo dự án mới và thiết lập thư mục `src/bin`:
```bash
cargo new web_server
cd web_server
mkdir -p src/bin
mv src/main.rs src/bin/main.rs
```

Cấu trúc dự án:
```text
web_server/
├── Cargo.toml
├── hello.html
└── src/
    ├── bin/
    │    └── main.rs    # Khởi tạo TCP listener và điều hướng kết nối HTTP
    └── lib.rs         # Tự cài đặt ThreadPool, Worker, Job queue & Graceful Shutdown
```

---

### 24.1. 🏗️ Kiến Trúc `ThreadPool` Trong `src/lib.rs`

Để tránh việc mỗi request lại tạo một thread OS mới (sẽ làm kiệt quệ tài nguyên máy chủ khi bị tấn công DoS), ta xây dựng một hồ chứa luồng (**ThreadPool**) gồm số lượng luồng cố định (ví dụ $4$ luồng). Các luồng này sẽ đợi việc từ một kênh `mpsc`:

```rust
// File: src/lib.rs
use std::{
    sync::{mpsc, Arc, Mutex},
    thread,
};

/// Kiểu định nghĩa công việc: một Closure có thể chạy trên luồng khác và chạy một lần
type Job = Box<dyn FnOnce() + Send + 'static>;

pub struct ThreadPool {
    workers: Vec<Worker>,
    sender: Option<mpsc::Sender<Job>>,
}

impl ThreadPool {
    /// Khởi tạo ThreadPool với số lượng luồng xác định
    ///
    /// # Panics
    /// Hàm sẽ panic nếu `size` bằng 0.
    pub fn new(size: usize) -> ThreadPool {
        assert!(size > 0, "Kích thước ThreadPool phải lớn hơn 0!");

        let (sender, receiver) = mpsc::channel();

        // Đưa receiver vào Arc và Mutex để các Worker có thể an toàn cùng nhận việc
        let receiver = Arc::new(Mutex::new(receiver));

        let mut workers = Vec::with_capacity(size);

        for id in 0..size {
            workers.push(Worker::new(id, Arc::clone(&receiver)));
        }

        ThreadPool {
            workers,
            sender: Some(sender),
        }
    }

    /// Đưa một tác vụ vào hàng đợi để các luồng thực thi
    pub fn execute<F>(&self, f: F)
    where
        F: FnOnce() + Send + 'static,
    {
        let job = Box::new(f);
        self.sender.as_ref().unwrap().send(job).unwrap();
    }
}

/// Đảm bảo tắt server an toàn (Graceful Shutdown)
impl Drop for ThreadPool {
    fn drop(&mut self) {
        // Hủy sender để ngắt kênh, khiến vòng lặp của các Worker tự động kết thúc
        drop(self.sender.take());

        for worker in &mut self.workers {
            println!("🛑 Đang dừng Worker {}...", worker.id);

            if let Some(thread) = worker.thread.take() {
                thread.join().unwrap();
            }
        }
    }
}

/// Cấu trúc đại diện cho một luồng công nhân
struct Worker {
    id: usize,
    thread: Option<thread::JoinHandle<()>>,
}

impl Worker {
    fn new(id: usize, receiver: Arc<Mutex<mpsc::Receiver<Job>>>) -> Worker {
        let thread = thread::spawn(move || loop {
            // Lấy khóa Mutex và đợi nhận công việc từ kênh:
            let message = receiver.lock().unwrap().recv();

            match message {
                Ok(job) => {
                    println!("⚙️ Worker {id} nhận được tác vụ, bắt đầu xử lý...");
                    job(); // Thực thi closure!
                }
                Err(_) => {
                    println!("💤 Kênh đã đóng, Worker {id} kết thúc phiên làm việc.");
                    break; // Thoát vòng lặp luồng
                }
            }
        });

        Worker {
            id,
            thread: Some(thread),
        }
    }
}
```

---

### 24.2. 🌐 Xử Lý Giao Thức HTTP Trong `src/bin/main.rs`

```rust
// File: src/bin/main.rs
use std::{
    fs,
    io::{prelude::*, BufReader},
    net::{TcpListener, TcpStream},
    thread,
    time::Duration,
};
use web_server::ThreadPool;

fn main() {
    // Lắng nghe kết nối TCP tại cổng 7878 trên localhost:
    let listener = TcpListener::bind("127.0.0.1:7878").unwrap();
    println!("🚀 Web Server đang chạy tại địa chỉ http://localhost:7878");

    // Khởi tạo ThreadPool với 4 luồng xử lý
    let pool = ThreadPool::new(4);

    // Lặp và chấp nhận các kết nối gửi tới
    for stream in listener.incoming().take(5) { // Lấy thử 5 kết nối để demo Graceful Shutdown
        let stream = stream.unwrap();

        pool.execute(|| {
            handle_connection(stream);
        });
    }

    println!("🛑 Server đang tắt một cách an toàn (Graceful Shutdown)...");
}

fn handle_connection(mut stream: TcpStream) {
    let buf_reader = BufReader::new(&stream);

    // Đọc dòng đầu tiên của HTTP Request (Request Line):
    let request_line = buf_reader.lines().next().unwrap().unwrap();

    // Rẽ nhánh logic xử lý theo Endpoint:
    let (status_line, filename) = match &request_line[..] {
        "GET / HTTP/1.1" => ("HTTP/1.1 200 OK", "hello.html"),
        "GET /sleep HTTP/1.1" => {
            // Giả lập tác vụ chậm chạp (ngủ 5 giây)
            thread::sleep(Duration::from_secs(5));
            ("HTTP/1.1 200 OK", "hello.html")
        }
        _ => ("HTTP/1.1 404 NOT FOUND", "404.html"),
    };

    let contents = fs::read_to_string(filename).unwrap_or_else(|_| {
        String::from("<h1>🦀 Phản hồi mặc định từ Rust Server</h1>")
    });
    let length = contents.len();

    let response = format!("{status_line}\r\nContent-Length: {length}\r\n\r\n{contents}");

    // Gửi phản hồi HTTP về lại cho trình duyệt:
    stream.write_all(response.as_bytes()).unwrap();
}
```

Tạo tập tin giao diện `hello.html`:
```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="utf-8">
    <title>Xin chào Rust! 🦀</title>
  </head>
  <body>
    <h1>🦀 Xin chào từ Rust Multithreaded Web Server! 🚀</h1>
    <p>Hệ thống xử lý đa luồng hoạt động an toàn và cực nhanh.</p>
  </body>
</html>
```

Khi mở trình duyệt tới `http://localhost:7878`, bạn sẽ thấy trang web phản hồi ngay lập tức, và dù có một yêu cầu truy cập vào `/sleep` gây nghẽn $5$ giây, các yêu cầu khác vẫn được các Worker còn lại trong hồ xử lý tức thì!

---

# 📖 PHẦN XI: PHỤ LỤC CẨM NANG RUSTACEAN TOÀN DIỆN

---

## PHỤ LỤC A: 🔑 BẢNG TỪ KHÓA & KÝ HIỆU CÚ PHÁP

### 1️⃣ Bảng Từ Khóa Đang Sử Dụng (Keywords Currently in Use)

| 🔑 Từ khóa | 📌 Ý nghĩa và Công dụng chính |
| :--- | :--- |
| `as` | Ép kiểu nguyên thủy, giải quyết xung đột trait, hoặc đặt bí danh trong `use` |
| `async` | Định nghĩa hàm hoặc khối lệnh trả về một `Future` thay vì chặn luồng |
| `await` | Tạm dừng thực thi cho đến khi kết quả của `Future` sẵn sàng (*postfix*) |
| `break` | Thoát khỏi vòng lặp ngay lập tức (có thể kèm giá trị trả về trong `loop`) |
| `const` | Định nghĩa hằng số thời điểm biên dịch hoặc con trỏ thô hằng |
| `continue` | Bỏ qua phần còn lại, chuyển ngay sang lượt lặp tiếp theo |
| `crate` | Đại diện cho gốc của crate hiện tại trong đường dẫn module |
| `dyn` | Đa hình động, điều phối phương thức qua con trỏ béo và vtable |
| `else` | Nhánh rẽ dự phòng cho cấu trúc `if`, `if let`, hoặc `let else` |
| `enum` | Định nghĩa kiểu liệt kê đa hình |
| `extern` | Khai báo liên kết với các hàm hoặc biến bên ngoài (FFI C ABI) |
| `false` / `true` | Giá trị logic boolean |
| `fn` | Định nghĩa hàm hoặc kiểu con trỏ hàm (`fn() -> T`) |
| `for` | Vòng lặp duyệt iterator, hoặc khai báo Higher-Ranked Lifetime Bounds (`for<'a>`) |
| `gen` | Từ khóa mới trong Rust Edition 2024 dành cho khối sinh (*generator blocks*) |
| `if` | Rẽ nhánh điều kiện |
| `impl` | Khối triển khai phương thức tự thân hoặc cài đặt Trait |
| `in` | Một phần của cú pháp vòng lặp `for item in collection` |
| `let` | Ràng buộc một biến mới |
| `loop` | Vòng lặp vô hạn |
| `match` | Khớp mẫu đối sánh toàn diện |
| `mod` | Khai báo hoặc định nghĩa một module |
| `move` | Ép Closure phải chiếm đoạt toàn bộ quyền sở hữu biến môi trường |
| `mut` | Biểu thị tính khả biến cho biến, tham chiếu hoặc con trỏ |
| `pub` | Công khai tầm nhìn của phần tử ra ngoài module |
| `ref` | Ràng buộc bằng tham chiếu trong mẫu đối sánh (ít dùng ở Rust hiện đại) |
| `return` | Thoát sớm khỏi hàm và trả về giá trị |
| `self` / `Self` | `self` là thể hiện đối tượng hiện tại; `Self` là bí danh kiểu dữ liệu hiện tại |
| `static` | Khai báo biến tĩnh tồn tại suốt vòng đời chương trình (`'static`) |
| `struct` | Định nghĩa cấu trúc dữ liệu tùy chỉnh |
| `super` | Trỏ tới module cha trong cây module |
| `trait` | Định nghĩa đặc tính trừu tượng hóa hành vi |
| `type` | Định nghĩa bí danh kiểu dữ liệu (*type alias*) hoặc kiểu liên kết |
| `union` | Định nghĩa kiểu hợp nhất (tương thích C union) |
| `unsafe` | Mở khối mã, định nghĩa hàm hoặc trait không an toàn |
| `use` | Đưa các định danh trong module vào phạm vi hiện tại |
| `where` | Khai báo mệnh đề ràng buộc trait cho generics |
| `while` | Vòng lặp có điều kiện |

---

### 2️⃣ Các Toán Tử & Ký Hiệu Cú Pháp Đặc Trưng

| ⚡ Ký hiệu | 📌 Ý nghĩa trong ngữ cảnh Rust |
| :--- | :--- |
| `!` | Ký tự nhận diện Macro (ví dụ: `println!`, `vec!`, `panic!`) hoặc kiểu Never `!` |
| `?` | Toán tử lan truyền lỗi trong `Result` và `Option` |
| `&` | Mượn bất biến (tham chiếu đọc) hoặc phép toán bit AND |
| `&mut` | Mượn khả biến (tham chiếu ghi độc quyền) |
| `*` | Toán tử giải tham chiếu (*dereference*) hoặc phép nhân |
| `::` | Toán tử phân giải phạm vi đường dẫn module hoặc hàm liên kết |
| `->` | Chỉ định kiểu trả về của hàm hoặc closure |
| `=>` | Tách nhánh mẫu đối sánh và khối lệnh trong `match` |
| `..` | Khoảng nửa mở (`start..end`) hoặc bỏ qua phần tử còn lại trong struct/pattern |
| `..=` | Khoảng đóng (`start..=end`, bao gồm cả `end`) |
| `@` | Ràng buộc giá trị trong mẫu khớp đối sánh |
| `'a` | Tham số vòng đời tham chiếu (*lifetime parameter*) |
| `_` | Ký tự đại diện bỏ qua (wildcard pattern) hoặc phân cách số `1_000_000` |

---

## PHỤ LỤC B: 🧰 BỘ CÔNG CỤ HỆ SINH THÁI RUST (CLIPPY, RUSTFMT, CARGO TOOLS)

1. 🎨 **`cargo fmt` (`rustfmt`):**
   - Công cụ tự động định dạng mã nguồn chuẩn hóa theo phong cách toàn cầu của cộng đồng Rust.
   - Chạy lệnh: `cargo fmt` trước khi commit code để đảm bảo sự thống nhất trong toàn đội ngũ.
2. 🔍 **`cargo clippy`:**
   - Trình phân tích tĩnh (*Linter*) cực kỳ thông minh của Rust. Clippy phát hiện hàng trăm lỗi logic tiềm ẩn, cảnh báo các đoạn code chưa tối ưu và gợi ý cách viết chuẩn mực *idiomatic* nhất.
   - Chạy lệnh: `cargo clippy`.
3. ⚡ **`cargo check`:**
   - Biên dịch kiểm tra lỗi siêu tốc không sinh mã thực thi.
4. 🧪 **`cargo test`:**
   - Chạy toàn bộ Unit Tests, Integration Tests và Documentation Tests.
5. 📚 **`cargo doc --open`:**
   - Tự động quét toàn bộ mã nguồn và các crate phụ thuộc để sinh ra website tài liệu kỹ thuật offline tuyệt đẹp và mở trên trình duyệt.
6. ➕ **`cargo add <crate_name>`:**
   - Tự động tìm phiên bản mới nhất của thư viện trên `crates.io` và thêm vào `Cargo.toml`.

---

## PHỤ LỤC C: 📏 BẢNG QUY ƯỚC ĐẶT TÊN CHUẨN (IDIOMATIC NAMING CONVENTIONS)

| 🧩 Phần tử mã nguồn | 📐 Quy ước chuẩn | 💡 Ví dụ mẫu |
| :--- | :--- | :--- |
| **Packages / Crates** | `snake_case` (thường dùng) | `serde_json`, `tokio` |
| **Modules** | `snake_case` | `front_of_house`, `network_io` |
| **Types (Struct, Enum, Trait)** | `UpperCamelCase` | `Rectangle`, `Option`, `Summary` |
| **Functions & Methods** | `snake_case` | `add_numbers`, `can_hold` |
| **Variables & Parameters** | `snake_case` | `user_id`, `is_active` |
| **Constants & Static** | `SCREAMING_SNAKE_CASE` | `MAX_POINTS`, `HTTP_TIMEOUT` |
| **Enum Variants** | `UpperCamelCase` | `Ok`, `Err`, `Some`, `None` |
| **Lifetimes** | `'snake_case` ngắn gọn | `'a`, `'b`, `'de`, `'static` |

---

## PHỤ LỤC D: 📘 TỪ ĐIỂN THUẬT NGỮ ANH - VIỆT CHUYÊN NGÀNH RUST

- 🔑 **Ownership:** Quyền sở hữu bộ nhớ.
- 🤝 **Borrowing:** Cơ chế mượn (truy cập dữ liệu qua tham chiếu).
- 🛡️ **Borrow Checker:** Bộ kiểm tra mượn (tiến trình tĩnh của trình biên dịch kiểm soát an toàn bộ nhớ).
- ⏳ **Lifetime:** Vòng đời / Thời gian sống hợp lệ của tham chiếu.
- 🚚 **Move Semantics:** Cơ chế di chuyển quyền sở hữu (vô hiệu hóa biến cũ).
- 🧬 **Deep Copy / Shallow Copy:** Sao chép sâu (toàn bộ dữ liệu) / Sao chép nông (chỉ sao chép con trỏ).
- 📜 **Trait:** Đặc tính / Hành vi trừu tượng (tương tự Interface).
- 🎭 **Trait Object:** Đối tượng đặc tính (`dyn Trait`), cơ chế đa hình động qua bảng vtable.
- ⚡ **Monomorphization:** Quá trình đơn hình hóa (sinh mã máy tối ưu cho từng kiểu generic).
- 🎯 **Pattern Matching:** Khớp mẫu đối sánh cấu trúc dữ liệu.
- 🌑 **Shadowing:** Kỹ thuật che bóng biến cũ bằng biến mới cùng tên.
- 🧭 **Smart Pointer:** Con trỏ thông minh (cấu trúc dữ liệu có metadata và tự động dọn dẹp).
- 🔓 **Interior Mutability:** Mẫu hình khả biến nội tại (cho phép sửa đổi dữ liệu qua tham chiếu bất biến).
- 💥 **Data Race:** Xung đột dữ liệu đa luồng (xảy ra khi nhiều luồng cùng truy cập và ít nhất một luồng ghi).
- 💎 **Zero-Cost Abstraction:** Trừu tượng hóa không tốn phí thời gian chạy.
- 🧹 **Unwinding:** Quá trình dọn dẹp ngăn xếp khi xảy ra `panic!`.
- 🚫 **Dangling Reference / Pointer:** Tham chiếu / con trỏ lơ lửng trỏ vào vùng nhớ rác đã bị giải phóng.
- ✅ **Soundness:** Tính chuẩn xác / an toàn toán học của mã nguồn Unsafe được đóng gói an toàn.

---

## PHỤ LỤC E: 🏆 MƯỜI NGUYÊN TẮC VÀNG ĐỂ LÀM CHỦ RUST

1. 🤝 **Đừng chiến đấu với Borrow Checker — hãy lắng nghe nó:** Thông báo lỗi của `rustc` là tài liệu sư phạm xuất sắc nhất thế giới. Trình biên dịch không gây khó dễ cho bạn; nó đang bảo vệ bạn khỏi các thảm họa sập hệ thống trong tương lai.
2. ⚡ **Ưu tiên tham chiếu mượn (`&T`, `&str`) hơn là sao chép (`.clone()`):** Chỉ gọi `.clone()` khi bạn thực sự cần hai bản sao dữ liệu hoàn toàn độc lập.
3. 🌳 **Thiết kế cấu trúc dữ liệu theo dạng Cây (Tree-like Ownership):** Tránh các cấu trúc tham chiếu vòng tròn. Hãy để mỗi vùng nhớ có một chủ nhân rõ ràng, hoặc sử dụng chỉ mục mảng (*Arena Allocation*).
4. 🛡️ **Tận dụng tối đa kiểu `Option` và `Result`:** Tuyệt đối không lạm dụng `.unwrap()` trong code production. Luôn xử lý lỗi một cách duyên dáng bằng toán tử `?`, `match`, hoặc `unwrap_or_else()`.
5. 🔒 **Biến mọi trạng thái bất hợp lệ thành lỗi biên dịch:** Sử dụng hệ thống kiểu (*Newtype pattern*, *Typestate pattern*) để các trạng thái sai không bao giờ có thể tồn tại.
6. 🧪 **Viết kiểm thử tự động ngay từ ngày đầu:** Tận dụng `#[test]` và doctest để biến mã nguồn của bạn thành tài liệu sống đáng tin cậy.
7. 📨 **Chia sẻ bộ nhớ bằng cách gửi thông điệp:** Trong lập trình đồng thời, ưu tiên dùng Channels (`mpsc`) hơn là chia sẻ bộ nhớ dùng chung với Mutex.
8. 🚀 **Hiểu rõ sự khác biệt giữa Concurrency và Parallelism:** Dùng `async/await` (`Tokio`) cho bài toán I/O mạng nghẽn; dùng `thread` và `rayon` cho bài toán tính toán CPU nặng.
9. ⚠️ **Hạn chế tối đa `unsafe`:** Chỉ mở khối `unsafe` khi thực sự cần thiết (FFI, low-level driver) và luôn đóng gói nó bên trong một Safe API với lời chú thích an toàn `// SAFETY: ...`.
10. 🦀 **Tận hưởng niềm vui lập trình:** Khi chương trình Rust của bạn biên dịch thành công, bạn có thể tự tin $100\%$ rằng nó sẽ chạy mượt mà, ổn định và bền bỉ suốt nhiều năm tháng!

---

> ### 📬 LIÊN HỆ & ĐÓNG GÓP
> Tài liệu được biên soạn và hoàn thiện bởi **Thái Việt**.  
> - **📧 Email:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)  
> - **🐙 GitHub:** [https://github.com/ozsx](https://github.com/ozsx)
> 
> *🎉 CHÚC BẠN THÀNH CÔNG RỰC RỠ TRÊN CON ĐƯỜNG CHINH PHỤC NGÔN NGỮ LẬP TRÌNH RUST! 🦀🚀*