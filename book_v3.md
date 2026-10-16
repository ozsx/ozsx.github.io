# 🦀 GIÁO TRÌNH RUST TOÀN TẬP — TỪ CƠ BẢN ĐẾN CHUYÊN SÂU (RUST COURSE) 🚀
*📚 Tài liệu học tập lập trình Rust toàn diện, trực quan và chuẩn mực bằng Tiếng Việt*  
*🏛️ Nguồn tham chiếu: The Rust Programming Language (TRPL) & Google Comprehensive Rust*

---

> ### 👨‍💻 THÔNG TIN TÁC GIẢ & BIÊN SOẠN
> - **✍️ Tác giả:** **Thái Việt**
> - **📧 Email:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)
> - **🐙 GitHub:** [github.com/ozsx](https://github.com/ozsx)
> - **🔖 Phiên bản:** 2024

---

## 🌟 LỜI NÓI ĐẦU: TẠI SAO BẠN NÊN HỌC RUST TRONG KỶ NGUYÊN HIỆN ĐẠI?

Trong suốt hơn $40$ năm qua, thế giới khoa học máy tính luôn tồn tại một sự đánh đổi cay đắng giữa hai thái cực:

1. **⚡ Hiệu năng và quyền kiểm soát cấp thấp (C/C++):** Tốc độ thực thi tối đa, kiểm soát trực tiếp phần cứng và bộ nhớ, nhưng lập trình viên phải đối mặt với "cơn ác mộng" về an toàn bộ nhớ: *Null Pointer Dereference* (giải tham chiếu con trỏ rỗng), *Dangling Pointers / Use-After-Free* (con trỏ lơ lửng / truy cập vùng nhớ đã giải phóng), *Double Free* (giải phóng bộ nhớ hai lần), *Buffer Overflow* (tràn bộ đệm), và *Data Races* (xung đột dữ liệu đa luồng). Thống kê từ Microsoft, Google và NSA chỉ ra rằng hơn $70\%$ các lỗ hổng bảo mật nghiêm trọng trong các hệ điều hành lớn (Windows, Linux Kernel, Android, Chromium) đều bắt nguồn từ lỗi quản lý bộ nhớ trong C/C++.
2. **🛡️ Tính an toàn và tiện dụng (Java, Go, Python, C#, JavaScript):** Bộ thu gom rác (*Garbage Collector - GC*) tự động dọn dẹp bộ nhớ giúp tránh được các lỗi bộ nhớ kinh điển, nhưng phải trả giá bằng việc tiêu tốn dung lượng RAM lớn, độ trễ tạm dừng chương trình (*Stop-The-World latency*), và mất đi khả năng kiểm soát phần cứng chi tiết.

**🦀 Rust ra đời để phá vỡ hoàn toàn sự đánh đổi đó!**  
Được khởi xướng bởi Graydon Hoare tại Mozilla Research và ra mắt phiên bản $1.0$ ổn định vào năm $2015$, Rust mang lại **Tam Trụ Cốt Lõi**:

1. **🛡️ An toàn bộ nhớ tại thời điểm biên dịch (Compile-time Memory Safety Without GC):** Thông qua hệ thống **Quyền sở hữu (Ownership)**, **Mượn (Borrowing)** và **Bộ kiểm tra mượn (Borrow Checker)** độc nhất vô nhị, Rust phát hiện và ngăn chặn $100\%$ lỗi bộ nhớ ngay trong quá trình biên dịch (*compile-time*) mà không cần bất kỳ bộ thu gom rác nào.
2. **💎 Trừu tượng hóa không chi phí (Zero-Cost Abstractions):** Bạn có thể viết mã nguồn cấp cao giàu tính biểu đạt (Generics, Traits, Closures, Iterators, Pattern Matching) nhưng khi biên dịch, trình biên dịch `rustc` sẽ tối ưu hóa thành mã máy có tốc độ ngang ngửa hoặc vượt trội so với C/C++ viết tay tỉ mỉ. *"Những gì bạn không dùng thì không phải trả phí; những gì bạn dùng thì bạn không thể tự viết tốt hơn"* (Bjarne Stroustrup).
3. **🧵 Lập trình đồng thời không sợ hãi (Fearless Concurrency):** Hệ thống kiểu dữ liệu và quyền sở hữu của Rust áp dụng trực tiếp cho môi trường đa luồng, triệt tiêu hoàn toàn lỗi xung đột dữ liệu đa luồng (*data races*) ngay từ lúc biên dịch. Nếu mã nguồn của bạn biên dịch thành công, nó được đảm bảo không xảy ra data race.

Giáo trình này được biên soạn và chuẩn hóa bởi **Thái Việt** (`@ozsx`), kết hợp cấu trúc sư phạm trực quan, tỉ mỉ của **Rust Course (Rust 语言圣经)**, tài liệu chuẩn mực *The Rust Programming Language* của Rust Team và khóa đào tạo chuyên sâu *Google Comprehensive Rust*.

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
- **⚙️ PHẦN V: PHƯƠNG THỨC, GENERICS, TRAITS & OOP**
  - [Chương 9: 🔧 Phương thức, Khối Triển khai (impl) & Thiết kế Hướng đối tượng (OOP)](#chương-9--phương-thức-khối-triển-khai-impl--thiết-kế-hướng-đối-tượng-oop)
  - [Chương 10: 🧬 Kiểu Chung (Generics) & Đặc tính (Traits) Toàn diện](#chương-10--kiểu-chung-generics--đặc-tính-traits-toàn-diện)
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
  - [Chương 22: ⚠️ Unsafe Rust, Kiểu Nâng cao & Tương tác Cấp thấp (FFI)](#chương-22-️-unsafe-rust-kiểu-nâng-cao--tương-tác-cấp-thấp-ffi)
  - [Chương 23: 🪄 Lập trình Siêu hình với Macros (Metaprogramming)](#chương-23--lập-trình-siêu-hình-với-macros-metaprogramming)
  - [Chương 24: 🌐 Dự án 3 — Xây dựng Multithreaded Web Server Hoàn chỉnh](#chương-24--dự-án-3--xây-dựng-multithreaded-web-server-hoàn-chỉnh)
- **📖 PHẦN XI: PHỤ LỤC CẨM NANG RUSTACEAN TOÀN DIỆN**
  - [Phụ lục A: 🔑 Bảng Từ khóa Trong Rust (Keywords & Raw Identifiers)](#phụ-lục-a--bảng-từ-khóa-trong-rust-keywords--raw-identifiers)
  - [Phụ lục B: 🔣 Bảng Toán tử & Ký hiệu Cú pháp](#phụ-lục-b--bảng-toán-tử--ký-hiệu-cú-pháp)
  - [Phụ lục C: ⚙️ Các Trait Có thể Tự động Dẫn xuất (Derivable Traits)](#phụ-lục-c-️-các-trait-có-thể-tự-động-dẫn-xuất-derivable-traits)
  - [Phụ lục D: 🧰 Bộ Công cụ Phát triển & Hệ sinh thái Production Crates](#phụ-lục-d--bộ-công-cụ-phát-triển--hệ-sinh-thái-production-crates)
  - [Phụ lục E: 📅 Các Phiên bản Rust Editions (2015, 2018, 2021, 2024)](#phụ-lục-e--các-phiên-bản-rust-editions-2015-2018-2021-2024)
  - [Phụ lục F: 📏 Bảng Quy ước Đặt tên Chuẩn (Idiomatic Naming Conventions)](#phụ-lục-f--bảng-quy-ước-đặt-tên-chuẩn-idiomatic-naming-conventions)
  - [Phụ lục G: 📘 Từ điển Thuật ngữ Anh - Việt & 10 Nguyên tắc Vàng Rustacean](#phụ-lục-g--từ-điển-thuật-ngữ-anh---việt--10-nguyên-tắc-vàng-rustacean)

---

# 🏁 PHẦN I: KHỞI ĐỘNG & NỀN TẢNG TRIẾT LÝ RUST

---

## CHƯƠNG 1: 🛠️ BẮT ĐẦU VỚI RUST & HỆ SINH THÁI CARGO

Rust không chỉ là một ngôn ngữ lập trình độc lập mà là một hệ sinh thái công cụ phát triển phần mềm hiện đại, tối ưu và kiểm soát chất lượng cực kỳ chặt chẽ. Để bắt đầu hành trình Rust, bạn cần nắm vững ba công cụ trụ cột: `rustup`, `rustc` và `cargo`.

### 1.1. 📥 Cài đặt Môi trường Rust qua `rustup`

`rustup` là công cụ chính thức quản lý các phiên bản trình biên dịch Rust và các công cụ liên quan. Nó hỗ trợ cài đặt, cập nhật, chuyển đổi linh hoạt giữa các kênh phát hành (*stable*, *beta*, *nightly*), và hỗ trợ biên dịch chéo (*cross-compilation*) cho nhiều hệ điều hành và kiến trúc vi xử lý khác nhau (x86_64, ARM64, WebAssembly, RISC-V).

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
   Truy cập trang web chính thức của Rust, tải về và chạy bộ cài đặt `rustup-init.exe`. Trong quá trình cài đặt, làm theo hướng dẫn để cài đặt công cụ *Microsoft Visual Studio C++ Build Tools* (chọn gói *"Desktop development with C++"* để cung cấp MSVC Linker cần thiết cho môi trường Windows).

#### 🔍 Kiểm tra cài đặt và lệnh quản trị thiết yếu:

```bash
# Kiểm tra phiên bản trình biên dịch rustc
rustc --version
# Kết quả mẫu: rustc 1.85.0+ (...)

# Kiểm tra phiên bản trình quản lý gói Cargo
cargo --version
# Kết quả mẫu: cargo 1.85.0+ (...)

# Cập nhật toàn bộ toolchain Rust lên phiên bản ổn định mới nhất
rustup update

# Mở toàn bộ tài liệu chính thức ngoại tuyến (offline) trực tiếp trên trình duyệt
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
1. **`fn main() { ... }`:** Khai báo hàm `main`. Trong Rust, từ khóa `fn` dùng để định nghĩa hàm. `main` là hàm đặc biệt nhất — điểm khởi đầu mà hệ điều hành sẽ gọi đầu tiên khi thực thi chương trình. Cặp ngoặc đơn `()` chứa danh sách tham số (ở đây không có tham số nào). Khối lệnh của thân hàm luôn nằm trong cặp ngoặc nhọn `{}`.
2. **`println!("Hello, world! 🦀");`:** In chuỗi ký tự ra màn hình kèm ký tự xuống dòng. Dấu chấm than `!` ở sau `println` là điểm cực kỳ quan trọng: **💡 đây là việc gọi một Macro, không phải một hàm thông thường!** Macros trong Rust cung cấp khả năng siêu lập trình (*metaprogramming*) tại thời điểm biên dịch, cho phép nhận số lượng tham số linh hoạt và kiểm tra định dạng chuỗi an toàn kiểu dữ liệu ngay lúc biên dịch.
3. **Dấu chấm phẩy `;`:** Đánh dấu sự kết thúc của một câu lệnh (*statement*).

#### ⚙️ Quy trình Biên dịch và Chạy:
Rust là ngôn ngữ biên dịch trước (**Ahead-Of-Time compiled**). Bạn dùng trình biên dịch `rustc` để dịch trực tiếp mã nguồn thành tập tin nhị phân thực thi độc lập (*standalone executable binary*):

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

### 1.3. 📦 Hệ thống Quản lý Dự án Cargo Chuyên Sâu

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
├── .gitignore       # Tập tin cấu hình bỏ qua thư mục build /target
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

# Danh sách các thư viện ngoài (crates) từ Crates.io mà dự án phụ thuộc
[dependencies]
```

- **`[package]`:** Khối thông tin cấu hình gói gồm tên dự án (`name`), phiên bản phát hành theo chuẩn Semantic Versioning `MAJOR.MINOR.PATCH` (`version`), và phiên bản ấn bản ngôn ngữ (`edition = "2024"`).
- **`[dependencies]`:** Nơi liệt kê các thư viện ngoài. Khi bạn thêm một crate vào đây, Cargo sẽ tự động tải về từ `crates.io`, kiểm tra mã băm checksum, biên dịch và liên kết vào dự án của bạn.

#### 🛠️ Vòng đời các lệnh Cargo thiết yếu trong công việc hàng ngày:
1. ⚡ **`cargo check`:** Quét cú pháp và kiểm tra kiểu dữ liệu cực nhanh mà không tốn thời gian sinh mã máy thực thi. Đây là lệnh các lập trình viên Rust chạy liên tục trong quá trình viết code để phát hiện lỗi sớm.
2. 🔨 **`cargo build`:** Biên dịch toàn bộ dự án ở chế độ phát triển (*debug mode*). Kết quả lưu tại `target/debug/hello_cargo`. Quá trình này tắt tối ưu hóa sâu (`opt-level = 0`) để tăng tốc độ biên dịch và giữ lại đầy đủ thông tin gỡ lỗi (*debug symbols*).
3. ▶️ **`cargo run`:** Tự động kiểm tra thay đổi, biên dịch (nếu cần) và thực thi chương trình ngay lập tức.
4. 🚀 **`cargo build --release`:** Biên dịch phiên bản xuất bản thương mại (*release mode*) với mức tối ưu hóa mã máy cao nhất (`opt-level = 3`), thực hiện inline hàm và vector hóa để đạt tốc độ thực thi tối đa. Tập tin thực thi lưu tại `target/release/hello_cargo`.
5. 🔒 **`Cargo.lock`:** Khi biên dịch lần đầu, Cargo tự động sinh ra tập tin `Cargo.lock` ghi lại chính xác phiên bản cụ thể và mã băm SHA256 của toàn bộ cây thư viện phụ thuộc, đảm bảo tính tái lập $100\%$ (**Reproducible Builds**) trên mọi máy tính khác nhau.

---

## CHƯƠNG 2: 🎲 DỰ ÁN 1 — TRÒ CHƠI ĐOÁN SỐ (GUESSING GAME)

Để biến lý thuyết thành kỹ năng thực tế, chúng ta sẽ bắt tay vào xây dựng dự án đầu tiên: **Trò chơi Đoán số (Guessing Game)**. Chương trình sẽ sinh ra một số nguyên ngẫu nhiên bí mật từ $1$ đến $100$, và người chơi sẽ nhập số dự đoán từ bàn phím cho đến khi đoán trúng.

Dự án này giúp bạn làm quen ngay với:
- ⌨️ Xử lý nhập/xuất dữ liệu từ bàn phím (`std::io`).
- 🔒 Bản chất của biến: Tính bất biến mặc định (*immutable*) và tính khả biến (`mut`).
- 📦 Tích hợp và cấu hình thư viện ngoài từ `crates.io`.
- 🎯 Khớp mẫu đối sánh mạnh mẽ (`match`) và kiểu so sánh `Ordering`.
- 🔁 Kiểm soát luồng lặp vô hạn (`loop`), thoát vòng lặp (`break`), bỏ qua lượt lặp (`continue`).
- 🛡️ Xử lý lỗi phục hồi được với kiểu `Result` (`Ok` / `Err`).

### 2.1. 📦 Cài đặt Crate `rand` trong `Cargo.toml`

Để sinh số ngẫu nhiên, chúng ta sử dụng crate chuẩn mực của cộng đồng là `rand`. Mở tập tin `Cargo.toml` và bổ sung dòng sau vào mục `[dependencies]`:

```toml
[dependencies]
rand = "0.8.5"
```

Khi chạy `cargo build`, Cargo sẽ kết nối đến registry trung tâm `crates.io`, tự động tải crate `rand` cùng toàn bộ cây phụ thuộc của nó về máy.

> 💡 **Lưu ý quan trọng cho Rust Edition 2024 & `rand 0.9+`:** Trong chuẩn Rust 2024, từ khóa `gen` đã trở thành từ khóa bảo lưu (*reserved keyword*) phục vụ cho Generator blocks. Nếu bạn khai báo `rand = "0.8.5"` như trên thì dùng hàm `rand::thread_rng().gen_range(1..=100)`. Nếu bạn dùng lệnh `cargo add rand` và cài bản `rand = "0.9"` trở lên, hãy đổi dòng sinh số ngẫu nhiên thành: `let secret_number = rand::rng().random_range(1..=100);`.

---

### 2.2. 💻 Toàn bộ Mã nguồn Dự án Hoàn chỉnh (`src/main.rs`)

```rust
use std::io;                      // Nạp module nhập/xuất chuẩn từ thư viện std
use std::cmp::Ordering;           // Nạp enum so sánh: Less, Greater, Equal
use rand::Rng;                    // Nạp Trait Rng để sử dụng phương thức gen_range

fn main() {
    println!("========================================");
    println!("  🎲 TRÒ CHƠI ĐOÁN SỐ BÍ MẬT (RUST) 🎲  ");
    println!("========================================");

    // Sinh số ngẫu nhiên bí mật trong khoảng [1, 100]
    // thread_rng() tạo bộ sinh số cục bộ trên luồng hiện tại
    // gen_range(1..=100) sử dụng cú pháp Inclusive Range (bao gồm cả 1 và 100)
    let secret_number = rand::thread_rng().gen_range(1..=100);

    // Vòng lặp vô hạn loop cho phép người chơi đoán liên tục cho đến khi trúng
    loop {
        println!("\n👉 Vui lòng nhập một số dự đoán của bạn (từ 1 đến 100):");

        // Biến trong Rust mặc định là bất biến (immutable).
        // Muốn giá trị của biến thay đổi được, BẮT BUỘC phải thêm từ khóa `mut`.
        // String::new() tạo ra một chuỗi UTF-8 rỗng có thể co giãn trên Heap.
        let mut guess = String::new();

        // Đọc dữ liệu từ bàn phím vào biến guess
        // &mut guess truyền vào một tham chiếu khả biến để hàm ghi đè dữ liệu
        io::stdin()
            .read_line(&mut guess)
            .expect("❌ Lỗi: Không thể đọc dòng dữ liệu từ bàn phím!");

        // Kỹ thuật Shadowing: Tái sử dụng tên biến `guess` để ép kiểu từ String sang u32
        // trim() loại bỏ khoảng trắng và ký tự xuống dòng (\n hoặc \r\n)
        // parse() chuyển chuỗi ký tự thành kiểu số
        // Dùng match để xử lý enum Result trả về từ parse():
        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,     // Nếu ép kiểu thành công, trả về số hợp lệ
            Err(_) => {         // Nếu người dùng nhập chữ hoặc ký tự không hợp lệ
                println!(">> ⚠️ Cảnh báo: Vui lòng chỉ nhập một số nguyên dương hợp lệ!");
                continue;       // Bỏ qua phần còn lại, chuyển sang vòng lặp tiếp theo
            }
        };

        println!("🎯 Bạn đã đoán: {guess}");

        // So sánh số người chơi đoán với số bí mật bằng phương thức .cmp()
        // match bắt buộc phải kiểm tra vét cạn (exhaustive) mọi khả năng của Ordering
        match guess.cmp(&secret_number) {
            Ordering::Less => println!(">> 📉 Kết quả: Quá nhỏ! Hãy thử số lớn hơn."),
            Ordering::Greater => println!(">> 📈 Kết quả: Quá lớn! Hãy thử số nhỏ hơn."),
            Ordering::Equal => {
                println!("========================================");
                println!(" 🎉 CHÚC MỪNG! BẠN ĐÃ ĐOÁN CHÍNH XÁC: {secret_number} 🏆");
                println!("========================================");
                break; // Thoát khỏi vòng lặp loop, kết thúc chương trình
            }
        }
    }
}
```

---

### 2.3. 🔬 Phân tích Chuyên sâu Từng Khái niệm Trong Dự án 1

#### 1️⃣ Ràng buộc biến khả biến (`let mut guess = String::new();`):
- Mặc định trong Rust, mọi biến đều là **bất biến (immutable)**. Nếu bạn viết `let guess = String::new();` và truyền `&mut guess` vào `read_line`, trình biên dịch sẽ từ chối dịch với lỗi: `cannot borrow immutable local variable guess as mutable`.
- Triết lý của Rust là: *Bất biến là mặc định, khả biến phải tường minh*. Bạn chỉ thêm `mut` khi thực sự cần thay đổi giá trị.

#### 2️⃣ Tham chiếu khả biến (`&mut guess`):
- Ký tự `&` biểu thị đây là một **Tham chiếu (Reference)** — cho phép hàm `read_line` truy cập và chỉnh sửa vùng nhớ của `guess` mà không cần chiếm quyền sở hữu (*ownership*) của biến.
- Ký tự `mut` sau dấu `&` chỉ rõ đây là tham chiếu có quyền ghi.

#### 3️⃣ Xử lý lỗi với kiểu `Result` và `.expect()`:
- `read_line` trả về một kiểu dữ liệu đặc biệt là `Result<usize, std::io::Error>`. `Result` là một enum có hai nhánh:
  - ✅ `Ok(value)`: Tác vụ I/O thành công, chứa số lượng byte đã đọc.
  - ❌ `Err(error)`: Tác vụ thất bại, chứa thông tin lỗi hệ thống.
- Nếu bạn không gọi `.expect()` hoặc không xử lý `Result`, trình biên dịch `rustc` sẽ cảnh báo: `unused std::result::Result that must be used`. Rust buộc lập trình viên phải chủ động đối mặt với lỗi tiềm ẩn ngay lúc viết code.

#### 4️⃣ Kỹ thuật Che bóng biến (Shadowing):
- Thay vì phải tạo hai biến với tên rời rạc như `guess_str` và `guess_number`, Rust cho phép khai báo lại biến `guess` bằng từ khóa `let`. Biến mới sẽ che bóng biến cũ và được phép chuyển đổi sang kiểu dữ liệu hoàn toàn khác (`u32`).

---

# 🧱 PHẦN II: NHẬP MÔN CĂN BẢN

---

## CHƯƠNG 3: 📦 BIẾN, TÍNH KHẢ BIẾN & PHẠM VI (SCOPE)

Trong hầu hết các ngôn ngữ lập trình truyền thống, biến được tạo ra mặc định có thể gán lại giá trị tùy ý. Tuy nhiên, trong Rust, khái niệm cốt lõi là **ràng buộc biến (Variable Binding)**, và biến mặc định luôn luôn là **bất biến (immutable)**.

### 3.1. 🔒 Ràng buộc Biến & Tính Bất biến Mặc định

> 💡 **Triết lý của Rust:** *Nếu một giá trị không cần thay đổi, đừng cho phép nó thay đổi.* Điều này giúp ngăn chặn hàng loạt lỗi logic tiềm ẩn khi dữ liệu bị thay đổi bất ngờ bởi các hàm khác hoặc trong môi trường đa luồng.

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

### 3.2. 🔓 Tính Khả biến với Từ khóa `mut`

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

### 3.3. ⚖️ So sánh Biến Bất biến (`let`) và Hằng số (`const`)

| 📌 Đặc tính | 🔒 Biến bất biến (`let`) | 💎 Hằng số (`const`) |
| :--- | :--- | :--- |
| **Khai báo cú pháp** | `let x = 5;` | `const MAX_POINTS: u32 = 100_000;` |
| **Bắt buộc chú thích kiểu?** | Không (Rust có thể tự suy luận) | **Bắt buộc $100\%$** phải ghi rõ kiểu dữ liệu |
| **Tính khả biến (`mut`)** | Có thể thêm `mut` để thành biến khả biến | **Tuyệt đối không bao giờ** được dùng `mut` |
| **Thời điểm tính giá trị** | Thời điểm chạy (*runtime*), có thể gán từ kết quả hàm | Thời điểm biên dịch (*compile-time constant expression*) |
| **Phạm vi khai báo** | Trong thân hàm hoặc khối lệnh | Mọi phạm vi, bao gồm cả phạm vi toàn cục (*global scope*) |
| **Quy ước đặt tên** | `snake_case` (ví dụ: `user_count`) | `SCREAMING_SNAKE_CASE` (ví dụ: `THREE_HOURS_IN_SECONDS`) |

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

#### ⚖️ Bảng đối chiếu Shadowing (`let`) vs Khả biến (`let mut`):

| Tiêu chí | Khả biến (`let mut x`) | Che bóng biến (`let x = ...; let x = ...;`) |
| :--- | :--- | :--- |
| **Đổi giá trị** | ✅ Được | ✅ Được |
| **Đổi kiểu dữ liệu** | ❌ **Không được** (giữ nguyên kiểu ban đầu) | ✅ **Được phép** (tạo biến hoàn toàn mới) |
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

### 3.5. 🔭 Phạm vi Biến (Scope)

Phạm vi (*scope*) là vùng không gian mã nguồn mà một biến có hiệu lực, được giới hạn bởi cặp ngoặc nhọn `{}`:

```rust
fn main() {
    // s chưa xuất hiện ở đây
    {
        let s = "hello"; // s bắt đầu hợp lệ từ dòng này
        println!("{s}"); // sử dụng s bình thường
    } // Khối lệnh kết thúc, phạm vi của s kết thúc tại đây, s bị giải phóng ngay lập tức!
}
```

---

## CHƯƠNG 4: 🔢 KIỂU DỮ LIỆU CƠ BẢN, HÀM & LUỒNG ĐIỀU KHIỂN

Rust là ngôn ngữ **định kiểu tĩnh (statically typed)**: mọi biến đều phải xác định được kiểu dữ liệu tại thời điểm biên dịch. Nhờ cơ chế **suy luận kiểu (type inference)** thông minh, trình biên dịch tự động nhận biết kiểu của hầu hết các biến, và chỉ yêu cầu chú thích tường minh khi có nhiều kiểu khả dĩ (như `.parse()`).

### 4.1. 🧮 Kiểu Dữ Liệu Vô Hướng (Scalar Types)

Kiểu vô hướng đại diện cho một giá trị đơn lẻ. Rust có $4$ nhóm kiểu vô hướng chính (cùng kiểu đơn vị `()`):

#### 1️⃣ Kiểu Số Nguyên (Integers):
Số nguyên gồm số có dấu (`i` - *signed*, lưu được số âm và dương) và số không dấu (`u` - *unsigned*, chỉ lưu số không âm).

| 📏 Kích thước | ➕➖ Có dấu (Signed) | ➕ Không dấu (Unsigned) | 📊 Miền giá trị ($\text{Min} \dots \text{Max}$) |
| :--- | :--- | :--- | :--- |
| **8-bit** | `i8` | `u8` | $-2^7$ đến $2^7 - 1$ ($-128 \dots 127$) / $0$ đến $255$ |
| **16-bit** | `i16` | `u16` | $-2^{15}$ đến $2^{15} - 1$ ($-32,768 \dots 32,767$) / $0$ đến $65,535$ |
| **32-bit** | `i32` *(Mặc định)* | `u32` | $-2^{31}$ đến $2^{31} - 1$ / $0$ đến $4.29 \times 10^9$ |
| **64-bit** | `i64` | `u64` | $-2^{63}$ đến $2^{63} - 1$ ($\approx \pm 9.22 \times 10^{18}$) |
| **128-bit**| `i128` | `u128`| $-2^{127}$ đến $2^{127} - 1$ (Dùng trong mật mã học, tài chính, blockchain) |
| **Arch** | `isize` | `usize` | Phụ thuộc kiến trúc CPU ($32$-bit hoặc $64$-bit). Dùng để đánh chỉ mục mảng/collection. |

*✨ Các dạng biểu diễn hằng số nguyên (Integer Literals):*
- Số thập phân (Decimal): `98_222` (dấu `_` giúp dễ đọc, giá trị là $98222$).
- Số thập lục phân (Hex): `0xff`.
- Số bát phân (Octal): `0o77`.
- Số nhị phân (Binary): `0b1111_0000`.
- Byte ký tự (chỉ dành cho `u8`): `b'A'`.

*⚠️ Hiện tượng tràn số nguyên (Integer Overflow):*
Giả sử một biến kiểu `u8` (miền giá trị từ $0$ đến $255$) đang mang giá trị $255$ và được cộng thêm $1$:
- **Trong chế độ Debug:** Rust chèn mã kiểm tra tràn số và làm chương trình dừng khẩn cấp (**panic**) tại runtime.
- **Trong chế độ Release (`--release`):** Để tối ưu tốc độ, Rust thực hiện phép quay vòng số học bù hai (*two's complement wrapping*): giá trị $256$ quay vòng về $0$, $257$ thành $1$.
- **Xử lý tràn số tường minh an toàn:** Thư viện chuẩn cung cấp $4$ nhóm phương thức cho số nguyên:
  - `wrapping_*` (ví dụ `255u8.wrapping_add(1)` $\rightarrow 0$).
  - `checked_*` (ví dụ `255u8.checked_add(1)` $\rightarrow$ trả về `None` nếu tràn).
  - `overflowing_*` (ví dụ `255u8.overflowing_add(1)` $\rightarrow$ trả về tuple `(0, true)`).
  - `saturating_*` (ví dụ `255u8.saturating_add(10)` $\rightarrow$ chạm trần tại giá trị cực đại $255$).

#### 2️⃣ Kiểu Số Thực Dấu Phẩy Động (Floating-Point Types):
Tuân theo chuẩn IEEE 754:
- `f32`: Độ chính xác đơn (*Single precision* - $32$-bit).
- `f64`: Độ chính xác kép (*Double precision* - $64$-bit). **Mặc định là `f64`** vì trên các CPU hiện đại tốc độ gần như tương đương `f32` nhưng độ chính xác cao hơn vượt trội.

```rust
let x = 2.0;      // f64 (mặc định)
let y: f32 = 3.0; // f32
```

#### 3️⃣ Kiểu Logic (Boolean):
Từ khóa `bool`, nhận hai giá trị `true` hoặc `false`, chiếm đúng $1$ byte bộ nhớ.

#### 4️⃣ Kiểu Ký Tự (Character):
Từ khóa `char`, đặt trong dấu nháy đơn `'a'`, chiếm **$4$ bytes ($32$-bit)** bộ nhớ. Đại diện cho một *Unicode Scalar Value* trong dải từ $\text{U+0000}$ đến $\text{U+D7FF}$ và $\text{U+E000}$ đến $\text{U+10FFFF}$. Nhờ đó, `char` biểu diễn được mọi chữ cái tiếng Việt có dấu, ký tự Trung/Nhật/Hàn, và cả biểu tượng Emoji:
```rust
let c = 'z';
let vietnamese_char = 'ệ';
let crab_emoji = '🦀';
```

#### 5️⃣ Kiểu Đơn Vị (Unit Type `()`):
Tuple rỗng `()` chỉ có một giá trị duy nhất là `()` và có kích thước **$0$ byte (Zero-Sized Type - ZST)**. Mọi hàm hoặc biểu thức không trả về giá trị cụ thể trong Rust đều ngầm định trả về `()`.

---

### 4.2. 🧱 Kiểu Dữ Liệu Phức Hợp Cơ Bản (Compound Types)

#### 1️⃣ Bộ giá trị (Tuple):
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

#### 2️⃣ Mảng tĩnh (Array `[T; N]`):
- Mọi phần tử trong mảng phải có **cùng một kiểu dữ liệu `T`**.
- Mảng có **độ dài cố định `N`** biết trước lúc biên dịch và được cấp phát trực tiếp trên **Ngăn xếp (Stack)**.

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

*🛡️ An toàn bộ nhớ kiểm tra biên (Bounds Checking):*
Nếu bạn truy xuất chỉ mục vượt quá độ dài mảng (như `a[10]`), Rust sẽ kiểm tra và dừng chương trình an toàn (**panic**) thay vì cho phép đọc vùng nhớ rác bất hợp pháp như trong C/C++!

---

### 4.3. ⚡ Câu Lệnh (Statement) vs. Biểu Thức (Expression)

Đây là một trong những đặc điểm thiết kế cốt lõi nhất của Rust:
- **📌 Câu lệnh (Statement):** Thực hiện một hành động nhưng **KHÔNG trả về giá trị** (ví dụ: `let x = 6;`). Do đó, bạn không thể viết `let x = (let y = 6);`.
- **⚡ Biểu thức (Expression):** Luôn tính toán và **trả về một giá trị**. Các phép toán, lời gọi hàm, biểu thức `if`, `match`, `loop` và **khối lệnh `{}`** đều là biểu thức!

```rust
fn main() {
    let y = {
        let x = 3;
        x + 1 // 💡 Biểu thức trả về giá trị 4 (KHÔNG có dấu chấm phẩy ở cuối!)
    };

    println!("Giá trị của y là: {y}"); // In ra 4
}
```
> ⚠️ **Quy tắc vàng:** Nếu bạn thêm dấu chấm phẩy `;` vào cuối dòng `x + 1;`, nó sẽ biến thành một câu lệnh và trả về kiểu đơn vị `()`, làm thay đổi hoàn toàn kết quả phép gán!

---

### 4.4. 🔧 Định Nghĩa Hàm (Functions)

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

### 4.5. 🔀 Cấu Trúc Luồng Điều Khiển (Control Flow)

#### 1️⃣ Biểu thức điều kiện `if`:
Điều kiện trong `if` bắt buộc phải là kiểu `bool`. Vì `if` là một biểu thức, bạn có thể dùng nó ngay bên phải câu lệnh `let` (hai nhánh `if` và `else` phải trả về cùng một kiểu dữ liệu):

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

#### 2️⃣ Vòng lặp `loop`, trả về giá trị từ `break` và Nhãn vòng lặp (`'label`):
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

#### 3️⃣ Vòng lặp điều kiện `while` và Vòng lặp tập hợp `for`:
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

# ❤️ PHẦN III: TRÁI TIM CỦA RUST — QUYỀN SỞ HỮU & MƯỢN

---

## CHƯƠNG 5: 🔑 HỆ THỐNG QUYỀN SỞ HỮU (OWNERSHIP) & MƯỢN (BORROWING)

**Quyền sở hữu (Ownership)** chính là tính năng đột phá nhất làm nên thương hiệu của ngôn ngữ Rust. Nó cho phép Rust đảm bảo an toàn bộ nhớ tuyệt đối tại thời điểm biên dịch mà không cần đến bộ thu gom rác (*Garbage Collector - GC*) chạy ngầm làm chậm hệ thống, cũng không đòi hỏi lập trình viên phải cấp phát và giải phóng bộ nhớ thủ công như C/C++.

### 5.1. 🏛️ Ba Trường Phái Quản Lý Bộ Nhớ Trong Khoa Học Máy Tính

1. **🔧 Quản lý thủ công (C, C++):**
   Lập trình viên phải tự xin cấp phát bộ nhớ (`malloc`, `new`) và tự nhớ gọi hàm giải phóng (`free`, `delete`).
   - *✅ Ưu điểm:* Hiệu năng tối đa, không tốn tài nguyên runtime.
   - *❌ Hiểm họa:* Quên giải phóng gây **rò rỉ bộ nhớ (memory leak)**; giải phóng $2$ lần gây **double free**; tiếp tục truy cập vùng nhớ đã giải phóng gây **use-after-free** hoặc lỗi **Segmentation Fault**.
2. **🗑️ Bộ thu gom rác tự động (Java, Go, Python, C#, JavaScript):**
   Hệ thống có tiến trình GC chạy ngầm, định kỳ quét đồ thị đối tượng để thu hồi vùng nhớ không còn tham chiếu.
   - *✅ Ưu điểm:* Tiện lợi, tránh được lỗi bộ nhớ cơ bản.
   - *❌ Nhược điểm:* Tiêu tốn RAM lớn, gây độ trễ ngẫu nhiên (*Stop-The-World latency*), không thể dùng cho lập trình hệ điều hành, nhân kernel hay hệ thống thời gian thực.
3. **🦀 Cách tiếp cận thứ ba của Rust — Quyền sở hữu (Ownership):**
   Bộ nhớ được quản lý thông qua một hệ thống các quy tắc chặt chẽ được **kiểm tra hoàn toàn tại thời điểm biên dịch (Compile-time)** bởi **Borrow Checker**. Nếu vi phạm bất kỳ quy tắc nào, chương trình không thể biên dịch. Khi chương trình chạy, **chi phí quản lý bộ nhớ bằng đúng $0$ (Zero-cost)**!

---

### 5.2. 🧠 Kiến Trúc Bộ Nhớ: Ngăn Xếp (Stack) vs. Đống (Heap)

```text
+-----------------------------------------------------------------------+
|                         KIẾN TRÚC BỘ NHỚ RAM                          |
+-----------------------------------+-----------------------------------+
|       🥞 NGĂN XẾP (STACK)         |           🗄️ ĐỐNG (HEAP)          |
+-----------------------------------+-----------------------------------+
| - Cơ chế LIFO (Vào sau ra trước)  | - Không gian nhớ tự do, phi cấu trúc|
| - Kích thước DỮ LIỆU CỐ ĐỊNH      | - Kích thước DỮ LIỆU ĐỘNG         |
|   phải biết trước lúc compile     |   có thể co giãn lúc chạy (run)   |
| - Tốc độ truy xuất CỰC KỲ NHANH   | - Cần tìm ô nhớ trống (Allocating)|
|   (chỉ dịch chuyển Stack Pointer) |   và truy cập gián tiếp qua con trỏ|
| - Tự động thu hồi khi thoát hàm   | - Quản lý vòng đời qua Ownership  |
+-----------------------------------+-----------------------------------+
```

#### 🔬 Phân tích bố cục bộ nhớ của kiểu `String`:
Một biến `String` thực chất bao gồm $3$ trường lưu trên **Stack** (chiếm $24$ bytes trên kiến trúc $64$-bit):
- **`ptr`** ($8$ bytes): Con trỏ trỏ đến địa chỉ vùng nhớ chứa nội dung chuỗi trên Heap.
- **`len`** ($8$ bytes): Độ dài nội dung chuỗi hiện tại (tính bằng byte).
- **`capacity`** ($8$ bytes): Tổng dung lượng bộ nhớ (tính bằng byte) đã được cấp phát trên Heap.

```text
         STACK (Biến s1)                         HEAP
    +--------------+-------+             +-----+---+---+---+---+---+
    | Tên trường   | Giá trị|            |Index| 0 | 1 | 2 | 3 | 4 |
    +--------------+-------+             +-----+---+---+---+---+---+
    |     ptr      |   o---+------------>| Val | h | e | l | l | o |
    |     len      |   5   |             +-----+---+---+---+---+---+
    |   capacity   |   5   |
    +--------------+-------+
```

---

### 5.3. 🏆 Ba Quy Tắc Vàng Của Quyền Sở Hữu (Ownership Rules)

Mọi chương trình Rust đều phải tuân thủ nghiêm ngặt $3$ quy tắc bất biến sau:
1. 🥇 **Mỗi giá trị trong Rust đều có một biến làm chủ sở hữu của nó (gọi là *Owner*).**
2. 🥈 **Tại một thời điểm bất kỳ, mỗi giá trị chỉ có DUY NHẤT MỘT chủ sở hữu.**
3. 🥉 **Khi biến chủ sở hữu đi ra khỏi phạm vi hoạt động (*Scope*), giá trị đó sẽ tự động bị hủy (*dropped*) và vùng nhớ được giải phóng ngay lập tức.**

---

### 5.4. 🚚 Cơ Chế Dịch Chuyển Quyền Sở Hữu (Move Semantics)

Hãy xem chuyện gì xảy ra khi gán biến `s1` cho `s2`:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1; // ⚡ Quyền sở hữu chuyển từ s1 sang s2. s1 bị vô hiệu hóa!

    // println!("{s1}"); // ❌ LỖI BIÊN DỊCH: borrow of moved value: `s1`
    println!("{s2}");    // ✅ Hợp lệ!
}
```

#### ⚖️ Tại sao Rust không dùng Shallow Copy mà dùng Move?
- Nếu Rust chỉ sao chép con trỏ trên Stack (*Shallow Copy*) và giữ cả `s1` lẫn `s2` hợp lệ, thì cả hai biến sẽ cùng trỏ vào một vùng nhớ trên Heap. Khi kết thúc hàm, cả `s1` và `s2` sẽ cùng gọi hàm `drop` để giải phóng cùng một vùng nhớ hai lần (**Double Free Error**) — một lỗ hổng bảo mật cực kỳ nguy hiểm!
- **🛡️ Giải pháp của Rust:** Rust sao chép $24$ bytes trên Stack (`ptr`, `len`, `capacity`) sang `s2`, nhưng **VÔ HIỆU HÓA HOÀN TOÀN** biến `s1`. Hành động này gọi là **Move (Dịch chuyển quyền sở hữu)**. Khi kết thúc scope, chỉ một mình `s2` giải phóng bộ nhớ Heap. Không tốn chi phí copy dữ liệu Heap, và không bao giờ xảy ra Double Free!

---

### 5.5. 🧬 Sao Chép Sâu Với `.clone()` & Đặc Tính `Copy` Trên Stack

#### 1️⃣ Sao chép sâu trên Heap với `.clone()`:
Khi bạn thực sự muốn nhân bản cả dữ liệu trên Heap để có hai biến độc lập:

```rust
fn main() {
    let s1 = String::from("hello");
    let s2 = s1.clone(); // Cấp phát vùng nhớ mới trên Heap và sao chép nội dung

    println!("s1 = {s1}, s2 = {s2}"); // ✅ Cả hai đều hợp lệ!
}
```

#### 2️⃣ Đặc tính `Copy` cho dữ liệu nằm hoàn toàn trên Stack:
Các kiểu dữ liệu có kích thước cố định nằm hoàn toàn trên Stack được cài đặt sẵn **Trait `Copy`**. Với các kiểu này, phép gán `let y = x;` sẽ sao chép bit trực tiếp với tốc độ $O(1)$ mà không làm mất hiệu lực của `x`:

```rust
fn main() {
    let x = 5;
    let y = x; // i32 có trait Copy nên x không bị Move!
    println!("x = {x}, y = {y}"); // ✅ Hợp lệ!
}
```

*📋 Danh sách các kiểu cài đặt `Copy`:*
- Mọi kiểu số nguyên (`i32`, `u64`, `usize`,...), số thực (`f32`, `f64`), `bool`, `char`.
- Tham chiếu bất biến `&T`.
- Tuple và Array cố định, **nếu mọi phần tử bên trong nó đều có `Copy`** (ví dụ: `(i32, bool)` có `Copy`, nhưng `(i32, String)` thì không).

---

### 5.6. 🔄 Quyền Sở Hữu Trong Hàm

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

### 5.7. 🤝 Cơ Chế Mượn (Borrowing) & Tham Chiếu (References)

Thay vì chuyển giao quyền sở hữu vào hàm rồi lại phải trả về, Rust cho phép tạo một **Tham chiếu (Reference)** trỏ đến giá trị mà không sở hữu nó. Hành động tạo tham chiếu gọi là **Mượn (Borrowing)**.

#### 1️⃣ Tham chiếu bất biến (`&T` - Shared Borrow):
Cho phép đọc dữ liệu nhưng không được phép chỉnh sửa:

```rust
fn main() {
    let s1 = String::from("hello");
    let len = calculate_length(&s1); // Cho mượn tham chiếu bất biến &s1
    println!("Độ dài của '{s1}' là {len}."); // ✅ s1 vẫn thuộc sở hữu của main!
}

fn calculate_length(s: &String) -> usize {
    s.len()
} // s ra khỏi scope, nhưng vì s chỉ mượn (không sở hữu) nên không giải phóng gì cả!
```

#### 2️⃣ Tham chiếu khả biến (`&mut T` - Exclusive Borrow):
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

### 5.8. 📜 Quy Tắc Bất Biến Của Borrow Checker & Non-Lexical Lifetimes (NLL)

> ### 🚨 QUY TẮC VÀNG CỦA BORROW CHECKER
> Tại một thời điểm bất kỳ trong cùng một phạm vi dữ liệu, bạn chỉ được phép có:
> - 📖 **HOẶC là vô số tham chiếu bất biến (`&T` - Nhiều người cùng đọc).**
> - ✍️ **HOẶC là DUY NHẤT MỘT tham chiếu khả biến (`&mut T` - Một người ghi độc quyền).**
> 
> **❌ TUYỆT ĐỐI KHÔNG BAO GIỜ vừa có tham chiếu đọc (`&T`) vừa có tham chiếu ghi (`&mut T`) cùng lúc!**

Quy tắc này giúp Rust loại trừ $100\%$ lỗi **Data Races (Xung đột dữ liệu)** ngay từ lúc biên dịch.

#### ✨ Cơ chế Non-Lexical Lifetimes (NLL):
Trình biên dịch Rust thông minh xác định phạm vi của một tham chiếu kết thúc ngay tại **lần cuối cùng tham chiếu đó được sử dụng**, chứ không cần chờ đến dấu đóng ngoặc nhọn `}`:

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

### 5.9. 🚫 Ngăn Chặn Con Trỏ Lơ Lửng (Dangling References)

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

### 5.10. 🍰 Kiểu Lát Cắt (Slices)

Lát cắt (**Slice**) là một tham chiếu đến một chuỗi các phần tử liên tiếp trong một tập hợp mà không chiếm quyền sở hữu của tập hợp đó.

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

#### 🏆 Quy ước thiết kế hàm tối ưu với `&str`:
Khi viết hàm nhận tham số chuỗi chỉ để đọc, hãy luôn dùng kiểu `&str` thay vì `&String`. Nhờ cơ chế *Deref Coercion*, hàm nhận `&str` có thể truyền vào cả `&str` lẫn `&String`!

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

> ### 🧠 THỬ THÁCH TƯ DUY RUSTACEAN (PHẦN III)
> **Câu hỏi:** Đoạn mã sau có biên dịch thành công không? Tại sao?
> ```rust
> fn main() {
>     let mut s = String::from("Rust 2024");
>     let word = first_word(&s);
>     s.clear();
>     println!("Từ đầu tiên là: {word}");
> }
> ```
> **💡 Giải đáp:** **KHÔNG biên dịch được!** Hàm `first_word(&s)` mượn bất biến biến `s` và trả về lát cắt `word` cũng gắn liền với mượn bất biến của `s`. Ở dòng tiếp theo, `s.clear()` yêu cầu một **mượn khả biến (`&mut s`)** để xóa nội dung chuỗi, trong khi `word` (mượn bất biến) vẫn còn được sử dụng ở lệnh `println!` phía dưới. Điều này vi phạm quy tắc vàng của Borrow Checker: *Không thể vừa mượn bất biến vừa mượn khả biến tại cùng một thời điểm!*

---

# 🧩 PHẦN IV: KIỂU PHỨC HỢP & KHỚP MẪU

---

## CHƯƠNG 6: 🔤 CHUỖI KÝ TỰ CHUYÊN SÂU (STRING & &STR)

Chuỗi ký tự trong Rust phân biệt rõ ràng giữa **chuỗi sở hữu (`String`)** và **lát cắt chuỗi mượn (`&str`)**, đồng thời thực thi nghiêm ngặt chuẩn mã hóa **UTF-8**.

### 6.1. 🌐 Bản Chất Mã Hóa UTF-8 & Ba Góc Nhìn Về Chuỗi

Tại sao trong Rust bạn **KHÔNG THỂ** viết `s[0]` để lấy ký tự đầu tiên của chuỗi?
Vì UTF-8 là bảng mã có độ dài biến thiên từ **$1$ đến $4$ bytes** cho mỗi ký tự:
- Chữ cái tiếng Anh ASCII (`"hello"`) mỗi ký tự chiếm $1$ byte.
- Chữ cái tiếng Việt có dấu (`"Việt"`) hoặc chữ Cyrillic (`"Здравствуйте"`) mỗi ký tự có thể chiếm từ $2$ đến $3$ bytes.
- Biểu tượng cảm xúc Emoji (`"🦀"`) chiếm $4$ bytes.

Nếu Rust cho phép truy xuất `s[0]`, nó sẽ trả về giá trị byte đầu tiên chứ không phải một ký tự hoàn chỉnh, làm vỡ ký tự Unicode và phá vỡ kỳ vọng thời gian truy xuất $O(1)$.

#### 🔬 Ba Góc Nhìn Về Chuỗi Trong Rust (Ví dụ chuỗi `"Việt"`):
1. **🔢 Dưới góc nhìn Bytes (`u8`):** Gồm $6$ bytes: `[86, 105, 225, 187, 135, 116]` (trong đó riêng chữ `'ệ'` được mã hóa bởi $3$ bytes `[225, 187, 135]`).
2. **🔤 Dưới góc nhìn Scalar Values (`char`):** Gồm $4$ ký tự Unicode: `['V', 'i', 'ệ', 't']`.
3. **👁️ Dưới góc nhìn Grapheme Clusters (Cụm ký tự hiển thị mắt người nhìn thấy):** `"V"`, `"i"`, `"ệ"`, `"t"`.

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

### 6.2. ⚖️ Bảng Đối Chiếu `String` và `&str`

| 📌 Tiêu chí | 📦 `String` | 🍰 `&str` (String Slice) |
| :--- | :--- | :--- |
| **Vùng nhớ lưu trữ** | Dữ liệu nằm trên **Heap**, co giãn động | Tham chiếu tới vùng nhớ UTF-8 (trên Heap, Stack hoặc Binary tĩnh) |
| **Quyền sở hữu** | Sở hữu dữ liệu (*Owned type*) | Chỉ mượn dữ liệu (*Borrowed view*) |
| **Kích thước trên Stack** | $24$ bytes (`ptr`, `len`, `capacity`) | $16$ bytes (`ptr`, `len`) — *Fat Pointer* |
| **Khả năng chỉnh sửa** | Thêm, nối, xóa ký tự linh hoạt (với `mut`) | Bất biến (chỉ đọc) |

---

### 6.3. 🛠️ Các Phép Toán Thao Tác Chuỗi Thường Dùng

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

## CHƯƠNG 7: 🏗️ KIỂU DỮ LIỆU TÙY CHỈNH: STRUCTS & ENUMS

### 7.1. 🧱 Cấu Trúc Dữ Liệu Structs (Structures)

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

#### 📦 Các dạng Struct đặc biệt:
1. **Tuple Structs:** Có tên kiểu nhưng các trường không đặt tên. Rất hữu ích để tạo kiểu mới phân biệt ngữ nghĩa (*Newtype Pattern*):
   ```rust
   struct Color(i32, i32, i32);
   struct Point(i32, i32, i32);
   ```
2. **Unit-Like Structs:** Không có bất kỳ trường nào (`struct AlwaysEqual;`), kích thước bằng $0$ byte (*ZST*), dùng khi cần cài đặt một Trait trên một kiểu mà không cần lưu trữ trạng thái dữ liệu.

---

### 7.2. 🎭 Kiểu Liệt Kê Enums & Vũ Khí `Option<T>`

Trong khi Struct gom các trường cùng tồn tại đồng thời (*kiểu AND*), **Enum** định nghĩa một giá trị chỉ có thể là **MỘT TRONG NHIỀU** biến thể khả dĩ (*kiểu OR - Algebraic Data Type*).

```rust
#[derive(Debug)]
enum Message {
    Quit,                       // Biến thể không chứa dữ liệu
    Move { x: i32, y: i32 },    // Biến thể chứa struct ẩn danh
    Write(String),              // Biến thể chứa một String
    ChangeColor(i32, i32, i32), // Biến thể chứa tuple 3 số nguyên
}
```

#### 🛡️ Enum Chuẩn `Option<T>` — Giải Pháp Thay Thế Hoàn Hảo Cho Null:
Rust loại bỏ hoàn toàn khái niệm `null`. Để biểu diễn một giá trị có thể tồn tại hoặc vắng mặt, thư viện chuẩn cung cấp `Option<T>`:

```rust
enum Option<T> {
    None,    // Không có giá trị
    Some(T), // Có giá trị kiểu T
}
```

Trình biên dịch bắt buộc bạn phải kiểm tra và xử lý trường hợp `None` trước khi có thể lấy giá trị bên trong `Some(T)`, giúp loại bỏ hoàn toàn lỗi `NullPointerException` tại runtime!

---

## CHƯƠNG 8: 🎯 NGHỆ THUẬT KHỚP MẪU (PATTERN MATCHING)

**Pattern (Mẫu)** là cú pháp đặc biệt của Rust dùng để đối sánh và phân rã cấu trúc dữ liệu.

### 8.1. 📍 Sáu Vị Trí Xuất Hiện Của Pattern & Phân Loại Refutable / Irrefutable

#### 1️⃣ Sáu vị trí Pattern xuất hiện trong Rust:
1. **Nhánh `match`:** `match value { PATTERN => EXPRESSION }`.
2. **Biểu thức `if let` và `let else`:** Xử lý gọn một mẫu cụ thể.
3. **Vòng lặp `while let`:** Lặp chừng nào mẫu còn khớp.
4. **Vòng lặp `for`:** `for (index, value) in v.iter().enumerate()`.
5. **Câu lệnh `let`:** `let (x, y, z) = (1, 2, 3);`.
6. **Tham số hàm:** `fn print_coordinates(&(x, y): &(i32, i32))`.

#### 2️⃣ Phân biệt Irrefutable vs Refutable Patterns:
- ✅ **Irrefutable (Không thể thất bại):** Mẫu luôn khớp với mọi giá trị có thể có của kiểu đó (ví dụ: `let x = 5;`, `let (a, b) = pair;`). Câu lệnh `let`, vòng lặp `for` và tham số hàm **chỉ chấp nhận** mẫu Irrefutable.
- ❓ **Refutable (Có thể thất bại):** Mẫu có thể không khớp với một số giá trị (ví dụ: `Some(x)` sẽ thất bại nếu giá trị là `None`). Dùng trong `if let`, `let else`, `while let` và các nhánh của `match`.

---

### 8.2. 🎛️ Cấu Trúc `match`, `if let` và `let else`

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

### 8.3. 🔥 Toàn Bộ Cú Pháp Khớp Mẫu Nâng Cao

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

# ⚙️ PHẦN V: PHƯƠNG THỨC, GENERICS, TRAITS & OOP

---

## CHƯƠNG 9: 🔧 PHƯƠNG THỨC, KHỐI TRIỂN KHAI (IMPL) & THIẾT KẾ HƯỚNG ĐỐI TƯỢNG (OOP)

### 9.1. 📐 Định Nghĩa Phương Thức (`&self`, `&mut self`, `self`) & Hàm Liên Kết

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

### 9.2. 🎭 Rust Dưới Góc Nhìn Lập Trình Hướng Đối Tượng (OOP)

Rust tiếp thu những tinh hoa của OOP nhưng loại bỏ những khuyết điểm lịch sử của nó:
- **📦 Đóng gói (Encapsulation):** Hỗ trợ hoàn hảo qua module và từ khóa `pub`. Dữ liệu nội bộ của struct được che giấu an toàn, bên ngoài chỉ tương tác qua các phương thức công khai.
- **🧩 Tổ hợp thay vì Kế thừa (Composition over Inheritance):** Rust **không có kế thừa lớp (`extends`)** để tránh sự phụ thuộc chặt chẽ và bài toán đa kế thừa (*Diamond Problem*). Thay vào đó, Rust sử dụng **Traits** để chia sẻ hành vi và nhúng các struct vào nhau để tái sử dụng cấu trúc.
- **🎨 Đa hình (Polymorphism):** Thực hiện thông qua **Generics** (đa hình tĩnh) và **Trait Objects `dyn Trait`** (đa hình động).

---

### 9.3. 🏆 Mẫu Thiết Kế Trạng Thái Chuẩn Rustacean: Typestate Pattern

Trong OOP truyền thống, để biểu diễn một đối tượng thay đổi hành vi theo trạng thái (như bài viết chuyển từ *Nháp* sang *Đã xuất bản*), ta thường dùng *State Pattern* với các biến cờ hoặc nhánh kiểm tra lúc chạy.

Trong Rust, các kỹ sư sử dụng **Typestate Pattern**: **Biến mỗi trạng thái thành một kiểu Struct riêng biệt!** Nhờ cơ chế phương thức tiêu thụ quyền sở hữu (`self`), khi chuyển trạng thái, đối tượng ở trạng thái cũ bị hủy hoàn toàn và trả về đối tượng ở trạng thái mới. Mọi hành vi gọi sai trạng thái sẽ bị **chặn đứng ngay tại thời điểm biên dịch**!

```rust
// Trạng thái 1: Bản nháp (Chưa hề có phương thức đọc nội dung content!)
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
    println!("📰 Bài viết đã xuất bản: {}", post.content()); // ✅ Hợp lệ tuyệt đối!
}
```

---

## CHƯƠNG 10: 🧬 KIỂU CHUNG (GENERICS) & ĐẶC TÍNH (TRAITS) TOÀN DIỆN

### 10.1. 🧩 Kiểu Chung (Generics) & Const Generics

Generics cho phép viết hàm, struct, enum và phương thức hoạt động trên nhiều kiểu dữ liệu mà không phải viết lặp lại mã:

```rust
// 1. Generic Function:
fn largest<T: std::cmp::PartialOrd>(list: &[T]) -> &T {
    let mut largest = &list[0]; // giả định list không rỗng (nếu truyền &[] sẽ panic!)
    for item in list {
        if item > largest {
            largest = item;
        }
    }
    largest
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
    println!("Số lớn nhất là: {}", largest(&numbers));

    let p1 = Point { x: 5, y: 10.4 };
    let p2 = Point { x: "Hello", y: 'c' };
    let p3 = p1.mixup(p2);
    println!("p3.x = {}, p3.y = {}", p3.x, p3.y);

    display_array([10, 20, 30]);
}
```

#### ⚡ Bản chất hiệu năng: Cơ chế Đơn hình hóa (Monomorphization):
Tại thời điểm biên dịch, trình biên dịch quét toàn bộ các kiểu cụ thể được truyền vào Generic và sinh ra mã máy riêng biệt cho từng kiểu (ví dụ `Point_i32` và `Point_f64`). Do đó, sử dụng Generics trong Rust **hoàn toàn không phát sinh chi phí runtime** (*Zero-Cost Abstraction*).

---

### 10.2. 📜 Định Nghĩa Traits, Trait Bounds & Blanket Implementations

```rust
pub trait Summary {
    fn summarize_author(&self) -> String;

    // Phương thức cài đặt mặc định (Default Implementation):
    fn summarize(&self) -> String {
        format!("(Đọc thêm từ {}...)", self.summarize_author())
    }
}

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
    U: Clone + std::fmt::Display,
{
    println!("Thông báo: {}", t.summarize());
}
```

#### 🌟 Blanket Implementations (Triển khai Bao phủ):
Rust cho phép cài đặt một Trait đồng loạt cho mọi kiểu dữ liệu nếu kiểu đó thỏa mãn một Trait khác. Ví dụ điển hình trong thư viện chuẩn:
```rust
// Mọi kiểu T có cài đặt Display đều tự động có phương thức .to_string() của trait ToString!
// impl<T: std::fmt::Display> ToString for T { ... }
```

---

### 10.3. ⚖️ Đa Hình Động Với Trait Objects (`dyn Trait`)

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

### 10.4. 🔥 Các Tính Năng Trait Nâng Cao (Advanced Traits)

#### 1️⃣ Kiểu Liên kết (Associated Types):
Kết nối một kiểu giữ chỗ (`type Item;`) vào trong Trait để người cài đặt chỉ định kiểu cụ thể đúng một lần duy nhất:
```rust
pub trait Iterator {
    type Item; // Associated Type
    fn next(&mut self) -> Option<Self::Item>;
}
```

#### 2️⃣ Nạp Chồng Toán Tử (Operator Overloading) Với `std::ops`:
Cài đặt các trait trong `std::ops` (như `Add`, `Sub`, `Mul`, `Index`) để nạp chồng toán tử cho Struct của bạn:

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

#### 3️⃣ Cú Pháp Định Danh Đầy Đủ (Fully Qualified Syntax) & Supertraits:
- **Supertrait:** Yêu cầu một kiểu muốn cài đặt Trait `A` thì bắt buộc phải cài đặt Trait `B` trước (`trait OutlinePrint: std::fmt::Display`).
- **Fully Qualified Syntax:** Khi hai Trait có phương thức trùng tên nhau trên cùng một kiểu, dùng cú pháp `<Type as Trait>::function(...)` để chỉ định rõ hàm muốn gọi.

#### 4️⃣ Mẫu Hình Newtype Vượt Qua Quy Tắc Cô Nhi (Orphan Rule):
Quy tắc **Orphan Rule** ngăn không cho bạn cài đặt `fmt::Display` (thuộc crate `std`) trực tiếp lên `Vec<String>` (cũng thuộc crate `std`). Để vượt qua một cách hợp lệ và không tốn chi phí runtime, ta bọc `Vec<String>` vào một Tuple Struct cục bộ:

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

> ### 🧠 THỬ THÁCH TƯ DUY RUSTACEAN (PHẦN V)
> **Câu hỏi:** Khi nào bạn nên dùng **Đa hình tĩnh (`impl Trait` / Generics `<T: Trait>`)** và khi nào nên dùng **Đa hình động (`Box<dyn Trait>`)**?
> **💡 Giải đáp:**
> - Dùng **Generics (`<T: Trait>`)** làm mặc định trong $90\%$ trường hợp vì trình biên dịch thực hiện *Monomorphization* (tạo mã máy trực tiếp cho từng kiểu, hỗ trợ inline hàm, chi phí runtime bằng $0$).
> - Chỉ dùng **Trait Objects (`Box<dyn Trait>` hoặc `&dyn Trait`)** khi bạn thực sự cần lưu trữ một tập hợp hỗn hợp nhiều kiểu dữ liệu khác nhau trong cùng một cấu trúc tại runtime (ví dụ `Vec<Box<dyn Draw>>`) hoặc khi muốn giảm dung lượng file nhị phân đánh đổi lấy một bước nhảy con trỏ hàm qua bảng `vtable`.

---

# 🗂️ PHẦN VI: TẬP HỢP DỮ LIỆU, CHUYỂN ĐỔI KIỂU & XỬ LÝ LỖI

---

## CHƯƠNG 11: 📚 CÁC CẤU TRÚC DỮ LIỆU TẬP HỢP (COLLECTIONS)

Các tập hợp dữ liệu trong `std::collections` lưu trữ dữ liệu trên **Heap**, cho phép mở rộng và thu hẹp kích thước linh hoạt tại runtime.

### 11.1. 📊 Bảng Tổng Hợp Toàn Bộ Collections Trong Thư Viện Chuẩn

| Cấu trúc | Nhóm | Độ phức tạp truy xuất / tìm kiếm | Độ phức tạp thêm / xóa | Khi nào nên sử dụng? |
| :--- | :--- | :--- | :--- | :--- |
| **`Vec<T>`** | Sequence | $O(1)$ theo chỉ mục | $O(1)$ ở cuối, $O(n)$ ở đầu/giữa | Mặc định cho hầu hết danh sách tuần tự, tối ưu bộ nhớ đệm CPU (Cache-friendly). |
| **`VecDeque<T>`** | Sequence | $O(1)$ theo chỉ mục | $O(1)$ ở **cả hai đầu** (đầu & cuối) | Khi cần hàng đợi hai đầu (FIFO Queue, Ring Buffer). |
| **`LinkedList<T>`**| Sequence | $O(n)$ | $O(1)$ khi đã có con trỏ nút | Rất hiếm dùng; chỉ dùng khi cần tách/ghép hai danh sách lớn trong $O(1)$. |
| **`HashMap<K, V>`**| Map | $O(1)$ trung bình | $O(1)$ trung bình | Tra cứu khóa - giá trị tốc độ cao không cần thứ tự khóa (dùng thuật toán SipHash chống DoS). |
| **`BTreeMap<K, V>`**| Map | $O(\log n)$ | $O(\log n)$ | Khi cần các khóa luôn được **sắp xếp theo thứ tự** hoặc truy vấn theo dải khóa (`.range()`). |
| **`HashSet<T>`** | Set | $O(1)$ trung bình | $O(1)$ trung bình | Kiểm tra sự tồn tại duy nhất của phần tử, phép hợp/giao/hiệu tập hợp nhanh. |
| **`BTreeSet<T>`** | Set | $O(\log n)$ | $O(\log n)$ | Tập hợp các phần tử duy nhất luôn được giữ thứ tự tăng dần. |
| **`BinaryHeap<T>`**| Misc | $O(1)$ lấy phần tử lớn nhất | $O(\log n)$ đẩy vào / lấy ra | Hàng đợi ưu tiên (*Priority Queue*), thuật toán tìm đường Dijkstra, lập lịch tác vụ. |

---

### 11.2. 📈 Vector Co Giãn (`Vec<T>`)

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

#### 🛡️ Tại sao Borrow Checker cấm `v.push()` khi đang giữ tham chiếu phần tử `&v[0]`?
```rust
let mut v = vec![1, 2, 3, 4, 5];
let first = &v[0]; // Mượn bất biến phần tử đầu tiên
// v.push(6);      // ❌ LỖI BIÊN DỊCH!
println!("Phần tử đầu: {first}");
```
*🔬 Giải thích bản chất bộ nhớ:* Khi gọi `v.push(6)`, nếu vùng nhớ hiện tại trên Heap đã đầy (`len == capacity`), Vector sẽ phải xin cấp phát một vùng nhớ mới lớn hơn ở địa chỉ khác, sao chép toàn bộ phần tử sang địa chỉ mới và **giải phóng vùng nhớ cũ**. Khi đó, con trỏ `first` sẽ trỏ vào vùng nhớ cũ đã bị hủy (*dangling pointer*)! Borrow Checker phát hiện và ngăn chặn nguy cơ này ngay lúc biên dịch.

#### 📦 Lưu trữ nhiều kiểu dữ liệu khác nhau trong Vector qua Enum:
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

### 11.3. 🗺️ Bảng Băm (`HashMap<K, V>`) & Entry API

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

### 11.4. 🧩 Thực Chiến Với `VecDeque`, `BTreeMap`, `HashSet` & `BinaryHeap`

```rust
use std::collections::{BTreeMap, BinaryHeap, HashSet, VecDeque};

fn main() {
    // 1. VecDeque: Hàng đợi hai đầu (thêm/xóa ở cả đầu và cuối đều đạt O(1))
    let mut queue = VecDeque::new();
    queue.push_back("Task 2");
    queue.push_front("Task 1 (Khẩn cấp)");
    println!("Hàng đợi VecDeque: {queue:?}");

    // 2. BTreeMap: Bản đồ tự động sắp xếp khóa và truy vấn theo khoảng (Range query)
    let mut timeline = BTreeMap::new();
    timeline.insert(2024, "Rust Edition 2024");
    timeline.insert(2015, "Rust 1.0 Stable");
    timeline.insert(2021, "Rust Edition 2021");
    for (year, event) in timeline.range(2018..=2024) {
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

## CHƯƠNG 12: 🔄 CHUYỂN ĐỔI KIỂU DỮ LIỆU (TYPE CONVERSIONS)

Rust không bao giờ tự động ép kiểu ngầm định giữa các kiểu dữ liệu số để tránh mất mát độ chính xác ngoài ý muốn.

### 12.1. 🔨 Ép Kiểu Nguyên Thủy Với `as`

```rust
let a: i32 = 10;
let b: f64 = a as f64; // Ép kiểu tường minh bằng từ khóa as
```

---

### 12.2. ✅ Chuyển Đổi Không Thất Bại (`From` / `Into`) & Có Thể Thất Bại (`TryFrom` / `TryInto`)

- **`From<T>` và `Into<U>`:** Dành cho các phép chuyển đổi luôn thành công. **Quy tắc vàng:** Hãy luôn ưu tiên cài đặt trait `From`, vì khi có `From`, thư viện chuẩn sẽ tự động cung cấp `Into` cho bạn thông qua Blanket Implementation!
- **`TryFrom<T>` và `TryInto<U>`:** Dành cho các phép chuyển đổi có nguy cơ thất bại, trả về `Result<Self, Self::Error>`.

```rust
use std::convert::{From, TryFrom};

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

## CHƯƠNG 13: 🛡️ CHIẾN LƯỢC XỬ LÝ LỖI (ERROR HANDLING)

Rust phân biệt rạch ròi hai nhóm lỗi:
1. 💥 **Lỗi không thể phục hồi (Unrecoverable Errors):** Do bug lập trình (truy cập mảng vượt biên, chia cho $0$). Xử lý bằng `panic!`.
2. 🔄 **Lỗi có thể phục hồi (Recoverable Errors):** Sự cố ngoại cảnh dự kiến trước (không tìm thấy file, mất kết nối mạng). Xử lý bằng `Result<T, E>`.

### 13.1. 💥 `panic!` và Truy Vết Ngăn Xếp (`RUST_BACKTRACE=1`)

Khi `panic!` xảy ra, mặc định Rust sẽ thực hiện *stack unwinding* (đi ngược ngăn xếp để giải phóng từng biến cục bộ của từng hàm đã gọi). Để xem toàn bộ lịch sử ngăn xếp lời gọi hàm dẫn tới dòng lỗi, chạy lệnh:

```bash
RUST_BACKTRACE=1 cargo run
```

---

### 13.2. 🔄 `Result<T, E>` và Toán Tử Lan Truyền Lỗi `?`

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

### 13.3. ⚖️ Khi Nào Dùng `panic!` vs `Result` & Xác Thực Bằng Kiểu Tùy Chỉnh

| Tình huống | Lựa chọn khuyến nghị | Lý do |
| :--- | :--- | :--- |
| 🧪 Viết mã mẫu, prototype, bài kiểm thử (`#[test]`) | `unwrap()`, `expect()`, `panic!` | Ngắn gọn, làm nổi bật logic chính hoặc báo test thất bại ngay. |
| 📦 Viết thư viện dùng chung (Library crate) | Luôn trả về `Result<T, E>` | Để ứng dụng gọi thư viện có toàn quyền quyết định cách phục hồi lỗi. |
| 🚨 Vi phạm điều kiện bất biến nội bộ (Contract violation) | `panic!` | Trạng thái bộ nhớ hoặc logic đã hỏng, tiếp tục chạy sẽ gây nguy hiểm. |
| 🛡️ Xác thực dữ liệu đầu vào của người dùng | Tạo Custom Type + trả `Result` | Đảm bảo mọi hàm nhận kiểu đó luôn nhận dữ liệu đã được kiểm chứng. |

#### 💎 Mẫu thiết kế Tạo Kiểu Tùy Chỉnh Để Xác Thực (Validation Custom Type):
Thay vì kiểm tra số dự đoán nằm trong khoảng $1 \dots 100$ ở khắp mọi hàm, ta đóng gói nó thành một kiểu `Guess` có trường `value` là `private`:

```rust
pub struct Guess {
    value: i32, // 🔒 Trường private: Không ai bên ngoài có thể gán trực tiếp giá trị sai!
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

# 🏛️ PHẦN VII: TỔ CHỨC DỰ ÁN, KIỂM THỬ & DỰ ÁN MINIGREP

---

## CHƯƠNG 14: 📁 QUẢN LÝ DỰ ÁN VỚI PACKAGES, CRATES, MODULES & WORKSPACES

### 14.1. 🏛️ Bốn Cấp Độ Tổ Chức: Workspace, Package, Crate, Module

```text
🏢 WORKSPACE (Quản lý đa dự án dùng chung Cargo.lock và thư mục target/)
 └── 📦 PACKAGE (Định nghĩa bởi Cargo.toml: Tối đa 1 Library crate + Vô số Binary crates)
      └── 🧱 CRATE (Đơn vị biên dịch: src/lib.rs hoặc src/main.rs)
           └── 📂 MODULE (Phân cấp cây mã nguồn và kiểm soát quyền riêng tư pub / private)
```

---

### 14.2. 🔐 Quy Tắc Riêng Tư, Đường Dẫn (`use`, `pub use`) & Tách Nhiều File

#### 1️⃣ Quy tắc riêng tư (Privacy Rules):
- Mọi thực thể mặc định là **riêng tư (`private`)** đối với module cha.
- Module con có thể truy cập mọi mục trong module cha, nhưng module cha chỉ truy cập được các mục có từ khóa `pub` của module con.
- Với `pub struct`: Các trường bên trong vẫn là `private` trừ khi từng trường được gắn `pub`.
- Với `pub enum`: **Toàn bộ các biến thể bên trong tự động là `pub`**.

#### 2️⃣ Tách Module thành nhiều tập tin chuẩn hiện đại (Không dùng `mod.rs` cũ):
Khi dự án lớn lên, ta tách các module ra thành các tập tin riêng biệt theo cấu trúc chuẩn:

```text
src/
├── lib.rs                      # Khai báo: pub mod front_of_house;
├── front_of_house.rs           # Khai báo: pub mod hosting;
└── front_of_house/
    └── hosting.rs              # Chứa: pub fn add_to_waitlist() {}
```

---

### 14.3. ⚙️ Tùy Biến Cấu Hình Tối Ưu Hóa Với Release Profiles

Trong `Cargo.toml`, bạn có thể kiểm soát chi tiết cách trình biên dịch tối ưu hóa mã máy:

```toml
[profile.dev]
opt-level = 0       # Tắt tối ưu hóa để biên dịch nhanh nhất khi đang phát triển

[profile.release]
opt-level = 3       # Tối ưu hóa tốc độ thực thi ở mức tối đa
lto = true          # Bật Link-Time Optimization (tối ưu hóa xuyên suốt toàn bộ các crate)
codegen-units = 1   # Gom thành 1 đơn vị sinh mã để trình biên dịch tối ưu hóa sâu nhất
panic = "abort"     # Dừng ngay khi panic thay vì unwinding, giúp giảm kích thước file nhị phân
strip = true        # Loại bỏ debug symbols, giảm mạnh dung lượng file thực thi
```

---

## CHƯƠNG 15: 🧪 KIỂM THỬ TỰ ĐỘNG (AUTOMATED TESTING) & TÀI LIỆU HÓA

### 15.1. 🔬 Giải Phẫu Hàm Kiểm Thử & Các Cờ Điều Khiển `cargo test`

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

#### 💻 Các lệnh điều khiển `cargo test` chuyên sâu:
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

### 15.2. ⚖️ Phân Biệt Unit Tests vs Integration Tests & Doctests

- **🧩 Unit Tests:** Đặt ngay trong `src/` cùng file với mã nguồn bên trong module `#[cfg(test)]`. Có đặc quyền kiểm thử được cả các hàm `private` nội bộ.
- **🔗 Integration Tests:** Đặt trong thư mục độc lập `tests/` ở gốc dự án. Mỗi tập tin trong `tests/*.rs` được biên dịch như một crate riêng biệt và chỉ gọi được các API `pub` của thư viện.
- **📖 Documentation Tests (Doctests):** Các khối mã ví dụ viết trong chú thích tài liệu `///` sẽ được `cargo test` tự động biên dịch và chạy kiểm thử, đảm bảo tài liệu luôn chính xác $100\%$ so với code thực tế!

```text
my_project/
├── Cargo.toml
├── src/
│   └── lib.rs               # Chứa Unit Tests & Doctests (///)
└── tests/
    └── integration_test.rs  # Chứa Integration Tests kiểm thử hộp đen
```

---

## CHƯƠNG 16: 🔍 DỰ ÁN 2 — XÂY DỰNG CÔNG CỤ DÒNG LỆNH MINIGREP

Trong dự án thứ hai này, chúng ta xây dựng công cụ tìm kiếm văn bản dòng lệnh `minigrep` theo đúng quy trình phát triển phần mềm chuyên nghiệp: tách biệt `src/lib.rs` và `src/main.rs`, áp dụng TDD (Test-Driven Development), hỗ trợ biến môi trường `IGNORE_CASE` và xuất lỗi chuẩn qua `eprintln!`.

### 16.1. 📚 Mã Nguồn Thư Viện Nghiệp Vụ (`src/lib.rs`)

```rust
use std::env;
use std::error::Error;
use std::fs;

pub struct Config {
    pub query: String,
    pub file_path: String,
    pub ignore_case: bool,
}

impl Config {
    // Tối ưu hóa bằng cách nhận trực tiếp một Iterator thay vì dùng .clone() trên mảng:
    pub fn build(mut args: impl Iterator<Item = String>) -> Result<Config, &'static str> {
        args.next(); // Bỏ qua phần tử đầu tiên (tên đường dẫn chương trình)

        let query = match args.next() {
            Some(arg) => arg,
            None => return Err("Thiếu từ khóa tìm kiếm! Cú pháp: minigrep <query> <file_path>"),
        };

        let file_path = match args.next() {
            Some(arg) => arg,
            None => return Err("Thiếu đường dẫn tập tin! Cú pháp: minigrep <query> <file_path>"),
        };

        let ignore_case = env::var("IGNORE_CASE").is_ok();

        Ok(Config {
            query,
            file_path,
            ignore_case,
        })
    }
}

pub fn run(config: Config) -> Result<(), Box<dyn Error>> {
    let contents = fs::read_to_string(config.file_path)?;

    let results = if config.ignore_case {
        search_case_insensitive(&config.query, &contents)
    } else {
        search(&config.query, &contents)
    };

    for line in results {
        println!("{line}");
    }

    Ok(())
}

// Sử dụng chuỗi biến đổi Iterator thanh lịch và tối ưu (Zero-cost abstraction):
pub fn search<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    contents
        .lines()
        .filter(|line| line.contains(query))
        .collect()
}

pub fn search_case_insensitive<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let query_lower = query.to_lowercase();
    contents
        .lines()
        .filter(|line| line.to_lowercase().contains(&query_lower))
        .collect()
}

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

### 16.2. 🚀 Mã Nguồn Điểm Khởi Đầu (`src/main.rs`)

```rust
use std::env;
use std::process;
use minigrep::Config;

fn main() {
    // Truyền trực tiếp bộ lặp env::args() vào Config::build:
    let config = Config::build(env::args()).unwrap_or_else(|err| {
        eprintln!("⚠️ Lỗi phân tích tham số: {err}");
        process::exit(1);
    });

    if let Err(e) = minigrep::run(config) {
        eprintln!("❌ Lỗi thực thi ứng dụng: {e}");
        process::exit(1);
    }
}
```

---

# 🧠 PHẦN VIII: VÒNG ĐỜI, LẬP TRÌNH HÀM & CON TRỎ THÔNG MINH

---

## CHƯƠNG 17: ⏳ VÒNG ĐỜI THAM CHIẾU (LIFETIMES 'A)

Mọi tham chiếu trong Rust đều có một **Vòng đời (Lifetime)** — là khoảng thời gian mà tham chiếu đó đảm bảo trỏ tới vùng nhớ hợp lệ. Phần lớn thời gian, trình biên dịch tự suy luận được vòng đời; nhưng khi có nhiều tham chiếu đầu vào có thể liên quan đến tham chiếu đầu ra, bạn cần chú thích bằng ký hiệu `'a` để giúp Borrow Checker xác minh tính an toàn.

### 17.1. 🔬 Sơ Đồ Không Gian Vòng Đời & Giao Ước Lifetime `'a`

Hãy xem lý do tại sao Borrow Checker từ chối đoạn mã có tham chiếu sống lâu hơn dữ liệu gốc:

```text
fn main() {
    let r;                  // ---------+-- 'a (Vòng đời của r bắt đầu)
                            //          |
    {                       //          |
        let x = 5;          // -+-- 'b  | (Vòng đời của x bắt đầu)
        r = &x;             //  |       | ❌ LỖI: 'b ngắn hơn 'a!
    }                       // -+       | (x bị giải phóng tại đây!)
                            //          |
    println!("r: {r}");     //          | (r cố đọc vùng nhớ đã hủy!)
}                           // ---------+
```

Khi viết hàm nhận vào hai lát cắt chuỗi và trả về một lát cắt chuỗi, Borrow Checker không thể biết trước tại thời điểm biên dịch nhánh `if` hay `else` sẽ chạy. Do đó, ta dùng chú thích `'a`:

```rust
// Chú thích 'a khẳng định với Borrow Checker rằng:
// Tham chiếu trả về sẽ sống hợp lệ chừng nào CẢ x VÀ y đều còn sống:
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

> 💡 **Bản chất toán học của `'a`:** Chú thích `'a` **không bao giờ làm thay đổi** thời gian sống thực tế của bất kỳ giá trị nào trên Stack hay Heap. Nó chỉ thiết lập ràng buộc miền giao thời gian sống: $\text{Lifetime}(\text{return}) \subseteq \text{Lifetime}(x) \cap \text{Lifetime}(y)$. Nghĩa là tham chiếu trả về có vòng đời bằng với **vòng đời ngắn hơn** giữa `x` và `y`.

---

### 17.2. 🏗️ Lifetime Trong Định Nghĩa Struct & Khối `impl`

Nếu một Struct lưu trữ các trường là tham chiếu (thay vì kiểu sở hữu như `String`), bạn **bắt buộc** phải khai báo tham số vòng đời trên Struct đó:

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
    let first_sentence = novel.split('.').next().expect("Không tìm thấy dấu chấm");
    let excerpt = ImportantExcerpt {
        part: first_sentence,
    };
    println!("Trích đoạn: {}", excerpt.announce_and_return_part("Bắt đầu câu chuyện"));
}
```

---

### 17.3. 📏 Ba Quy Tắc Suy Đoán Vòng Đời Tự Động (Lifetime Elision Rules) & `'static`

Trình biên dịch tự động suy luận lifetime trong chữ ký hàm theo $3$ quy tắc:
1. **Quy tắc 1 (Đầu vào):** Mỗi tham số là tham chiếu được gán một tham số lifetime riêng biệt (`fn foo<'a, 'b>(x: &'a i32, y: &'b i32)`).
2. **Quy tắc 2 (Một đầu vào):** Nếu chỉ có **duy nhất $1$ tham số lifetime đầu vào**, lifetime đó được gán cho toàn bộ các tham chiếu đầu ra (`fn first_word<'a>(s: &'a str) -> &'a str`).
3. **Quy tắc 3 (Phương thức):** Nếu là phương thức có `&self` hoặc `&mut self`, lifetime của `self` được tự động gán cho toàn bộ các tham chiếu đầu ra.

#### ♾️ Vòng đời tĩnh `'static`:
Tham chiếu `'static` biểu thị dữ liệu có thể tồn tại trong suốt thời gian chạy của chương trình (ví dụ các chuỗi hằng `let s: &'static str = "Hello";` được nhúng thẳng vào phân vùng dữ liệu chỉ đọc `.rodata` của file nhị phân).

---

### 17.4. 🏆 Kết Hợp Chung Generics, Trait Bounds và Lifetimes Trong Một Hàm

Đây là hình thái chữ ký hàm đầy đủ và tổng quát nhất trong Rust:

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

## CHƯƠNG 18: 🔁 LẬP TRÌNH HÀM: CLOSURES & ITERATORS

Rust kết hợp vẻ đẹp thanh lịch của Lập trình Hàm (*Functional Programming*) với hiệu năng cấp thấp của ngôn ngữ hệ thống.

### 18.1. 🎣 Closures, Chế Độ Bắt Giữ Môi Trường & Ba Trait `FnOnce`, `FnMut`, `Fn`

**Closure (Hàm đóng)** là hàm ẩn danh có thể lưu vào biến, truyền làm tham số cho hàm khác, và đặc biệt là **có khả năng bắt giữ (capture) các biến từ phạm vi môi trường nơi nó được định nghĩa**.

Trình biên dịch tự động chọn cách bắt giữ ít hạn chế nhất, tương ứng với $3$ Trait phân cấp từ rộng đến hẹp (`Fn: FnMut`, `FnMut: FnOnce`):
1. 🥇 **`FnOnce`:** Chiếm quyền sở hữu (*Move*) các biến bị bắt giữ ra khỏi môi trường. Chỉ có thể gọi **$1$ lần duy nhất**. Mọi closure đều cài đặt `FnOnce`.
2. 🥈 **`FnMut`:** Mượn tham chiếu khả biến (`&mut T`) các biến từ môi trường, cho phép thay đổi trạng thái biến ngoài. Có thể gọi nhiều lần. Mọi closure không di chuyển biến ra ngoài đều cài đặt `FnMut`.
3. 🥉 **`Fn`:** Mượn tham chiếu bất biến (`&T`) hoặc không bắt giữ gì cả, chỉ đọc dữ liệu, có thể gọi nhiều lần đồng thời một cách an toàn.

#### 🚀 Ép buộc chiếm quyền sở hữu bằng từ khóa `move`:
Khi truyền một closure sang một luồng (thread) mới hoặc trả về một closure từ hàm, bạn dùng từ khóa `move` trước `||` để buộc closure chiếm quyền sở hữu biến:

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

### 18.2. ⚡ Iterators: Ba Phương Thức Tạo Lặp & Xây Dựng Custom Iterator

#### 1️⃣ Phân biệt 3 phương thức tạo Iterator cốt lõi:
- **`.iter()`:** Tạo bộ lặp trả về tham chiếu bất biến **`&T`** (giữ nguyên tập hợp gốc).
- **`.iter_mut()`:** Tạo bộ lặp trả về tham chiếu khả biến **`&mut T`** (sửa trực tiếp phần tử tại chỗ).
- **`.into_iter()`:** Tiêu thụ tập hợp gốc và trả về quyền sở hữu từng phần tử **`T`**.

#### 2️⃣ Tự xây dựng một cấu trúc Iterator tùy chỉnh từ con số 0:
Để biến bất kỳ Struct nào thành một Iterator có thể dùng với `for`, `.map()`, `.filter()`, `.zip()`, bạn chỉ cần cài đặt duy nhất phương thức `next()` của Trait `Iterator`:

```rust
struct Fibonacci {
    curr: u64,
    next: u64,
}

impl Fibonacci {
    fn new() -> Self {
        Fibonacci { curr: 0, next: 1 }
    }
}

impl Iterator for Fibonacci {
    type Item = u64;

    fn next(&mut self) -> Option<Self::Item> {
        let current = self.curr;
        self.curr = self.next;
        self.next = current + self.next;
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

> 💎 **Hiệu năng Zero-Cost Abstraction của Iterator:** Khi biên dịch ở chế độ `--release`, trình biên dịch `rustc` (cùng backend LLVM) thực hiện *Loop Unrolling* (trải phẳng vòng lặp), loại bỏ kiểm tra biên thừa (*bounds check elimination*) và áp dụng tập lệnh vector SIMD trên CPU. Do đó, chuỗi `.iter().filter().map().sum()` chạy nhanh ngang ngửa hoặc nhanh hơn cả vòng lặp `for` chỉ mục viết tay!

---

## CHƯƠNG 19: 🧭 CON TRỎ THÔNG MINH (SMART POINTERS)

Con trỏ thông minh là các cấu trúc dữ liệu không chỉ đóng vai trò như một con trỏ trỏ tới địa chỉ bộ nhớ mà còn chứa siêu dữ liệu (*metadata* như bộ đếm tham chiếu, dung lượng) và sở hữu dữ liệu mà nó trỏ tới. Chúng cài đặt hai Trait nền tảng là **`Deref`** (tùy biến toán tử giải tham chiếu `*` và hỗ trợ *Deref Coercion*) và **`Drop`** (tự động dọn dẹp tài nguyên khi ra khỏi scope theo mô hình *RAII*).

### 19.1. ⚖️ Bảng Tổng Hợp Các Con Trỏ Thông Minh Trong Rust

| Con trỏ | Số chủ sở hữu | Kiểu mượn & Khả biến | Thời điểm kiểm tra mượn | Môi trường luồng |
| :--- | :--- | :--- | :--- | :--- |
| **`Box<T>`** | $1$ chủ sở hữu | Bất biến hoặc Khả biến | **Compile-time** | Đơn luồng & Đa luồng (`Send + Sync`) |
| **`Rc<T>`** | Nhiều chủ sở hữu | Chỉ đọc bất biến | **Compile-time** | **Chỉ Đơn luồng** (`!Send`) |
| **`RefCell<T>`**| $1$ chủ sở hữu | Bất biến hoặc Khả biến nội tại | **Runtime** (sai sẽ `panic!`) | **Chỉ Đơn luồng** (`!Sync`) |
| **`Arc<T>`** | Nhiều chủ sở hữu | Chỉ đọc bất biến (trừ khi bọc `Mutex`) | **Compile-time** | **Đa luồng an toàn** (`Send + Sync`) |
| **`Cow<'a, B>`**| Mượn hoặc Sở hữu | Clone-on-Write (chỉ copy khi cần ghi) | **Compile-time** | Đơn luồng & Đa luồng |

---

### 19.2. 🧠 Sơ Đồ Bộ Nhớ Của `Box<T>`, `Rc<T>` và Tính Khả Biến Nội Tại (`RefCell<T>`)

```text
1. Box<T> (Sở hữu độc quyền trên Heap):
   [Stack: ptr] ──────────────────────► [Heap: Dữ liệu T]

2. Rc<T> (Đếm tham chiếu chia sẻ nhiều chủ sở hữu):
   [Stack: rc_1] ──┐
   [Stack: rc_2] ──┼─► [Heap: strong_count: 3 | weak_count: 0 | Dữ liệu T]
   [Stack: rc_3] ──┘

3. RefCell<T> (Khả biến nội tại - Kiểm tra mượn tại Runtime):
   [Stack: RefCell] ──► [borrow_flag (isize) | Dữ liệu T]
   (borrow_flag = 0: Chưa ai mượn | > 0: Số người đang đọc borrow() | -1: Đang ghi độc quyền borrow_mut())
```

---

### 19.3. 🔬 Tự Xây Dựng Smart Pointer `MyBox<T>` & `Drop`

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
        println!("🗑️ Đang giải phóng vùng nhớ của MyBox!");
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

### 19.4. 🤝 Kết Hợp `Rc<RefCell<T>>` & Chống Rò Rỉ Bộ Nhớ Với `Weak<T>`

Khi xây dựng cấu trúc Cây (*Tree*) có nút cha trỏ xuống nút con và nút con trỏ ngược lên nút cha:
- Chiều từ **Cha $\rightarrow$ Con**: Dùng `Rc<T>` (Cha sở hữu con).
- Chiều từ **Con $\rightarrow$ Cha**: Bắt buộc dùng **`Weak<T>`** (`Rc::downgrade`) để phá vỡ vòng lặp tham chiếu (*Reference Cycle*), ngăn chặn rò rỉ bộ nhớ!

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

    println!("Nút cha của leaf: {:?}", leaf.parent.borrow().upgrade());
}
```

---

### 19.5. 🐄 Tối Ưu Hóa Cấp Phát Với `Cow<'a, B>` (Clone-on-Write)

`std::borrow::Cow` (Clone-on-Write) là một Smart Pointer cực kỳ thông minh có $2$ biến thể:
- `Cow::Borrowed(&'a B)`: Chỉ mượn dữ liệu gốc (không tốn bất kỳ chi phí cấp phát Heap nào) nếu dữ liệu không cần chỉnh sửa.
- `Cow::Owned(<B as ToOwned>::Owned)`: Chỉ thực sự cấp phát Heap và sao chép dữ liệu khi phát sinh nhu cầu chỉnh sửa!

```rust
use std::borrow::Cow;

// Hàm chuẩn hóa chuỗi: Nếu chuỗi không có khoảng trắng thừa thì trả về nguyên bản &str (0 cấp phát Heap!),
// chỉ khi phát hiện có dấu cách mới cấp phát String mới để thay thế:
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

> ### 🧠 THỬ THÁCH TƯ DUY RUSTACEAN (PHẦN VIII)
> **Câu hỏi:** Điều gì sẽ xảy ra khi chạy đoạn mã sử dụng `RefCell` dưới đây?
> ```rust
> use std::cell::RefCell;
> fn main() {
>     let data = RefCell::new(vec![1, 2, 3]);
>     let r1 = data.borrow();
>     let r2 = data.borrow_mut();
>     println!("{r1:?}, {r2:?}");
> }
> ```
> **💡 Giải đáp:** Chương trình sẽ **biên dịch thành công** nhưng bị **`panic!` ngay tại thời điểm chạy (runtime)** với thông báo: `already borrowed: BorrowMutError`. Lý do là `RefCell<T>` chuyển việc kiểm tra quy tắc mượn từ lúc biên dịch sang lúc chạy: khi biến `r1` (`Ref<Vec<i32>>`) vẫn đang còn hiệu lực trong scope, việc gọi `data.borrow_mut()` để lấy tham chiếu khả biến sẽ vi phạm quy tắc độc quyền và kích hoạt `panic!`.

---

# ⚡ PHẦN IX: LẬP TRÌNH ĐỒNG THỜI & BẤT ĐỒNG BỘ

---

## CHƯƠNG 20: 🧵 LẬP TRÌNH ĐA LUỒNG (MULTI-THREADING CONCURRENCY)

### 20.1. ⚡ Tạo Luồng (`thread::spawn`), Luồng Theo Phạm Vi (`thread::scope`) & Kênh `mpsc`

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

### 20.2. 🔒 Chia Sẻ Trạng Thái Đa Luồng Với `Arc<Mutex<T>>` & Xử Lý Poisoned Mutex

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

> ⚠️ **Cơ chế Poisoned Mutex (Khóa bị nhiễm độc):** Tại sao `counter.lock()` lại trả về `Result`? Trong Rust, nếu một luồng đang giữ khóa `Mutex` mà bất ngờ bị `panic!`, khóa đó sẽ được đánh dấu là *"Poisoned"* để cảnh báo các luồng khác rằng dữ liệu bên trong có thể đang ở trạng thái dở dang, mất tính nhất quán. Các luồng khác có thể dùng `.unwrap()` để dừng theo, hoặc gọi `.unwrap_or_else(|poisoned| poisoned.into_inner())` để chủ động khôi phục lại dữ liệu.

---

### 20.3. ⚡ Khóa Đọc-Ghi (`RwLock<T>`) & Kiểu Nguyên Tử Không Khóa (`Atomics`)

1. **`RwLock<T>` (Read-Write Lock):** Trong khi `Mutex<T>` chỉ cho phép duy nhất $1$ luồng truy cập tại một thời điểm (dù chỉ để đọc), `RwLock<T>` cho phép **nhiều luồng cùng đọc đồng thời (`.read()`)** hoặc **duy nhất $1$ luồng ghi độc quyền (`.write()`)**. Rất tối ưu cho dữ liệu cấu hình đọc nhiều - ghi ít.
2. **Kiểu Nguyên Tử (`std::sync::atomic`):** Thực hiện các phép toán nguyên tử trực tiếp bằng chỉ thị phần cứng CPU (*Lock-free*) mà không tốn chi phí khóa hệ điều hành:

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

#### 🛡️ Hai Marker Traits Cốt Lõi: `Send` và `Sync`
- 📤 **`Send`:** Đánh dấu kiểu dữ liệu an toàn khi **chuyển giao quyền sở hữu (Move) giữa các luồng**.
- 🔄 **`Sync`:** Đánh dấu kiểu dữ liệu an toàn khi **chia sẻ tham chiếu bất biến (`&T`) giữa nhiều luồng cùng lúc** ($T$ là `Sync` $\iff \&T$ là `Send`).

---

## CHƯƠNG 21: 🚀 LẬP TRÌNH BẤT ĐỒNG BỘ (ASYNC / AWAIT)

### 21.1. ⚖️ Threads vs Async & Bản Chất Trait `Future`

| Tiêu chí | OS Threads (`std::thread`) | Async Tasks (`async` / `.await`) |
| :--- | :--- | :--- |
| **Chi phí bộ nhớ** | Nặng (Mỗi luồng tốn hàng Megabytes Stack) | Cực nhẹ (Mỗi task chỉ tốn vài trăm Bytes) |
| **Số lượng đồng thời** | Vài nghìn luồng | Hàng trăm nghìn đến hàng triệu kết nối |
| **Bài toán tối ưu** | Tính toán nặng CPU (*CPU-bound*) | Chờ đợi I/O mạng, đĩa cứng (*I/O-bound*) |

Trong Rust, một `Future` là một máy trạng thái lười biếng (*lazy state machine*), chỉ tiến triển khi được Async Runtime gọi phương thức `.poll()`:

```rust
use std::pin::Pin;
use std::task::{Context, Poll};

pub trait Future {
    type Output;
    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output>;
}
```

- **📌 `Pin<P>`:** Đảm bảo cố định địa chỉ bộ nhớ của các máy trạng thái `Future` có chứa con trỏ tự tham chiếu (*Self-Referential Structs*) qua các điểm chờ `.await`.

---

### 21.2. ⚡ Lập Trình Bất Đồng Bộ Thực Chiến Với `Tokio` (`join!`, `select!`, `spawn` & `mpsc`)

```rust
use tokio::sync::mpsc;
use tokio::time::{sleep, Duration};

async fn fetch_service(name: &str, ms: u64) -> String {
    sleep(Duration::from_millis(ms)).await;
    format!("Phản hồi từ {name} ({ms}ms)")
}

#[tokio::main]
async fn main() {
    // 1. Chạy song song cùng lúc hai tác vụ bằng tokio::join!:
    let (r1, r2) = tokio::join!(
        fetch_service("AuthService", 200),
        fetch_service("OrderService", 300),
    );
    println!("✅ Kết quả join: {r1} | {r2}");

    // 2. Chạy đua tác vụ (Timeout pattern) bằng tokio::select!:
    tokio::select! {
        res = fetch_service("PaymentService", 100) => {
            println!("🎉 Thanh toán hoàn tất: {res}");
        }
        _ = sleep(Duration::from_millis(500)) => {
            println!("⏰ Quá thời gian chờ (Timeout)!");
        }
    }

    // 3. Khởi chạy các Background Tasks độc lập với tokio::spawn và kênh bất đồng bộ mpsc:
    let (tx, mut rx) = mpsc::channel(32);

    for i in 1..=3 {
        let tx_clone = tx.clone();
        tokio::spawn(async move {
            let msg = format!("Sự kiện bất đồng bộ #{i}");
            tx_clone.send(msg).await.unwrap();
        });
    }
    drop(tx); // Đóng đầu gửi gốc để vòng lặp while let kết thúc khi hết dữ liệu

    while let Some(event) = rx.recv().await {
        println!("📨 Nhận qua kênh Async: {event}");
    }
}
```

> 🚨 **Quy tắc sống còn trong Async Rust — Không làm nghẽn Executor (Never Block the Executor):**
> Tuyệt đối không gọi `std::thread::sleep` hoặc thực hiện các phép tính toán nặng CPU kéo dài trực tiếp bên trong `async fn`, vì nó sẽ khóa cứng luồng Worker của Tokio, làm tê liệt hàng nghìn task khác đang chạy chung trên luồng đó!
> - Thay cho `std::thread::sleep` $\rightarrow$ Luôn dùng `tokio::time::sleep(...).await`.
> - Nếu cần chạy tác vụ nặng CPU hoặc I/O đồng bộ $\rightarrow$ Đẩy sang bể luồng riêng bằng `tokio::task::spawn_blocking(|| { /* việc nặng */ }).await`.

---

### 21.3. 🌟 Async Traits (`async fn` trong Trait) & Async Closures (`async ||` — Chuẩn Rust 2024)

Trong các phiên bản Rust trước đây, việc khai báo `async fn` trực tiếp trong `trait` đòi hỏi phải cài đặt macro ngoài `#[async_trait]`. Kể từ Rust $1.75+$ và đặc biệt hoàn thiện trong **Rust Edition 2024 (`rustc 1.85+`)**, Rust đã hỗ trợ trực tiếp **Native `async fn` trong Trait** và **Async Closures (`async || {}`)** kèm bộ ba Trait `AsyncFn`, `AsyncFnMut`, `AsyncFnOnce`:

```rust
// 1. Khai báo trực tiếp async fn trong Trait mà không cần crate ngoài:
pub trait HealthCheck {
    async fn check_status(&self) -> Result<String, &'static str>;
}

pub struct PostgresDb;

impl HealthCheck for PostgresDb {
    async fn check_status(&self) -> Result<String, &'static str> {
        Ok(String::from("PostgreSQL: Healthy (Latency 2ms)"))
    }
}

// 2. Sử dụng Async Closure (async ||) chuẩn Rust 2024:
async fn run_with_retry<F>(mut action: F)
where
    F: AsyncFnMut() -> String,
{
    let result = action().await;
    println!("⚡ Kết quả từ Async Closure: {result}");
}

#[tokio::main]
async fn main() {
    let db = PostgresDb;
    println!("🩺 Kiểm tra DB: {:?}", db.check_status().await);

    let prefix = String::from("Request #101");
    // Async closure có thể mượn trực tiếp biến `prefix` từ môi trường qua các điểm .await!
    let task = async || {
        format!("{prefix}: Xử lý hoàn tất!")
    };

    run_with_retry(task).await;
}
```

---

# 🔥 PHẦN X: NÂNG CAO, MACROS & DỰ ÁN WEB SERVER

---

## CHƯƠNG 22: ⚠️ UNSAFE RUST, KIỂU NÂNG CAO & TƯƠNG TÁC CẤP THẤP (FFI)

### 22.1. ⚡ Năm Siêu Năng Lực Của Unsafe Rust & FFI Chuẩn Rust 2024

Khối `unsafe { ... }` không tắt Borrow Checker mà chỉ mở khóa $5$ thao tác cấp thấp:
1. Giải tham chiếu con trỏ thô (`*const T` và `*mut T`).
2. Gọi một hàm hoặc phương thức `unsafe fn`.
3. Truy cập hoặc sửa đổi biến tĩnh khả biến (`static mut`).
> ⚠️ **Lưu ý quan trọng trong Rust Edition 2024**: Việc tạo tham chiếu trực tiếp (`&` hoặc `&mut`) tới biến `static mut` đã bị trình biên dịch cấm mặc định (`deny-by-default` do quy tắc `static_mut_refs`). Khi cần thao tác với `static mut`, bạn bắt buộc phải dùng toán tử con trỏ thô `&raw const` / `&raw mut`, hoặc tốt nhất hãy thay thế bằng `LazyLock`, `Mutex` hoặc các kiểu `Atomic`.
4. Cài đặt một `unsafe trait`.
5. Truy cập các trường của một `union`.

```rust
use std::ffi::c_int;

// Trong chuẩn Rust Edition 2024, khối extern bắt buộc phải có từ khóa `unsafe`:
unsafe extern "C" {
    fn abs(input: c_int) -> c_int;
}

fn main() {
    let mut num = 42;
    // Tạo con trỏ thô an toàn với toán tử &raw (Rust 2024):
    let r1 = &raw const num;
    let r2 = &raw mut num;

    // SAFETY: r1 và r2 trỏ tới biến `num` hợp lệ trên Stack, và hàm C `abs` an toàn với mọi c_int.
    unsafe {
        *r2 = -100;
        println!("Giá trị qua r1: {}, trị tuyệt đối qua C FFI: {}", *r1, abs(*r1));
    }
}
```

---

### 22.2. 🧬 Các Kiểu Dữ Liệu Nâng Cao (Advanced Types)

1. **🏷️ Bí danh kiểu (Type Aliases):** Giúp rút gọn các chữ ký kiểu dài dòng:
   ```rust
   type Thunk = Box<dyn Fn() + Send + 'static>;
   type Result<T> = std::result::Result<T, std::io::Error>;
   ```
2. **❗ Kiểu Không Bao Giờ Trả Về (The Never Type `!`):**
   Các biểu thức như `panic!()`, `continue`, `break`, hoặc `loop` vô hạn có kiểu là `!` (*diverging functions*). Kiểu `!` có thể tự động ép sang bất kỳ kiểu dữ liệu nào khác trong nhánh `match`.
3. **📏 Kiểu Có Kích Thước Động (Dynamically Sized Types - DST & Trait `Sized`):**
   Các kiểu như `str` hoặc `[T]` hoặc `dyn Trait` không có kích thước cố định lúc biên dịch, nên luôn phải đứng sau một con trỏ (`&str`, `Box<dyn Trait>`). Mặc định mọi hàm generic `fn generic<T>(t: T)` đều ngầm định ràng buộc `T: Sized`. Nếu muốn cho phép nhận cả DST qua tham chiếu, dùng cú pháp nới lỏng: `fn generic<T: ?Sized>(t: &T)`.

---

## CHƯƠNG 23: 🪄 LẬP TRÌNH SIÊU HÌNH VỚI MACROS (METAPROGRAMMING)

**Macros** là kỹ thuật viết mã sinh ra mã (*code that writes code*) ngay tại thời điểm biên dịch, giúp mở rộng cú pháp ngôn ngữ và loại bỏ hoàn toàn mã lặp lại (*boilerplate*).

### 23.1. 📜 Declarative Macros (`macro_rules!`) & Các Bộ Chỉ Định Mẫu

Declarative Macros hoạt động tương tự như biểu thức `match`, nhưng thay vì so khớp giá trị lúc chạy, nó **so khớp cấu trúc cây cú pháp Rust tại thời điểm biên dịch**.

#### 📋 Các bộ chỉ định phân mảnh cú pháp (Fragment Specifiers) quan trọng:
- `$x:expr`: Một biểu thức bất kỳ (ví dụ: `1 + 2`, `func()`, `"hello"`).
- `$i:ident`: Một tên định danh biến, hàm hoặc kiểu (ví dụ: `my_var`, `User`).
- `$t:ty`: Một kiểu dữ liệu (ví dụ: `i32`, `Vec<String>`).
- `$p:pat`: Một mẫu pattern matching.
- `$tt:tt`: Một Token Tree đơn lẻ.
- `$( ... ),*` (hoặc `$( ... ),+`): Lặp lại mẫu $0$ hoặc nhiều lần (`*`), hoặc $1$ hoặc nhiều lần (`+`), phân tách bởi dấu phẩy.

```rust
#[macro_export]
macro_rules! hashmap {
    // Nhánh 1: Gọi hashmap!() rỗng
    () => {
        std::collections::HashMap::new()
    };
    // Nhánh 2: Khởi tạo với danh sách các cặp key => value
    // $(,)? ở cuối cho phép có hoặc không có dấu phẩy thừa (trailing comma)
    ( $( $key:expr => $val:expr ),+ $(,)? ) => {
        {
            let mut map = std::collections::HashMap::new();
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

### 23.2. ⚙️ Procedural Macros (`#[derive]`, Attribute-like & Function-like)

Procedural Macros hoạt động như một hàm Rust chạy trong quá trình biên dịch: nhận đầu vào là một luồng mã nguồn (`proc_macro::TokenStream`), phân tích cú pháp bằng crate **`syn`**, và sinh ra mã Rust mới bằng crate **`quote`**. Nó phải được đặt trong một crate riêng có khai báo `proc-macro = true` trong `Cargo.toml`.

Có $3$ loại Procedural Macros:
1. **Custom Derive Macro (`#[derive(HelloMacro)]`):** Tự động cài đặt Trait cho Struct/Enum.
2. **Attribute-like Macro (`#[route(GET, "/users")]`):** Tùy biến hàm, struct hoặc module (rất phổ biến trong `tokio::main`, `axum`, `actix-web`).
3. **Function-like Macro (`sql!(SELECT * FROM users WHERE id = 1)`):** Trông giống lời gọi macro thường nhưng cho phép phân tích cú pháp tùy ý phức tạp hơn `macro_rules!`.

#### 🔬 Ví dụ cấu trúc triển khai một Custom Derive Macro chuẩn công nghiệp:

```rust
// [Trong crate: hello_macro_derive/src/lib.rs]
// Yêu cầu trong Cargo.toml:
// [lib]
// proc-macro = true
// [dependencies]
// syn = "2.0"
// quote = "1.0"

use proc_macro::TokenStream;
use quote::quote;
use syn::{parse_macro_input, DeriveInput};

#[proc_macro_derive(HelloMacro)]
pub fn hello_macro_derive(input: TokenStream) -> TokenStream {
    // 1. Phân tích TokenStream đầu vào thành cây cú pháp trừu tượng (AST) bằng syn:
    let ast = parse_macro_input!(input as DeriveInput);
    let name = &ast.ident; // Lấy tên của Struct/Enum được gắn #[derive(HelloMacro)]

    // 2. Sinh mã cài đặt Trait tự động bằng macro quote!:
    let expanded = quote! {
        impl HelloMacro for #name {
            fn hello_macro() {
                println!("👋 Xin chào từ Macro! Tên kiểu của tôi là: {}!", stringify!(#name));
            }
        }
    };

    // 3. Chuyển đổi ngược về TokenStream trả lại cho trình biên dịch rustc:
    TokenStream::from(expanded)
}
```

Khi sử dụng trong ứng dụng chính, bạn chỉ cần viết:
```rust
#[derive(HelloMacro)]
struct Pancakes;

fn main() {
    Pancakes::hello_macro(); // In ra: 👋 Xin chào từ Macro! Tên kiểu của tôi là: Pancakes!
}
```

---

## CHƯƠNG 24: 🌐 DỰ ÁN 3 — XÂY DỰNG MULTITHREADED WEB SERVER HOÀN CHỈNH

Trong dự án tốt nghiệp này, chúng ta xây dựng một máy chủ Web đa luồng chuẩn HTTP/1.1 từ con số $0$ chỉ bằng thư viện chuẩn `std`, tích hợp **ThreadPool**, kênh truyền tin **`mpsc`**, đồng bộ hóa **`Arc<Mutex<T>>`** và cơ chế đóng máy chủ an toàn (**Graceful Shutdown**) qua Trait **`Drop`**.

### 24.1. 📁 Cấu Trúc Thư Mục Dự Án

```text
web_server/
├── Cargo.toml
├── hello.html          # Trang HTML trả về khi thành công (200 OK)
├── 404.html            # Trang HTML trả về khi không tìm thấy (404 NOT FOUND)
└── src/
    ├── lib.rs          # Cài đặt ThreadPool, Worker và Graceful Shutdown
    └── main.rs         # Lắng nghe kết nối TCP và xử lý giao thức HTTP/1.1
```

---

### 24.2. ⚙️ Module `ThreadPool` Đa Luồng Chuẩn Mực (`src/lib.rs`)

```rust
use std::sync::{mpsc, Arc, Mutex};
use std::thread;

type Job = Box<dyn FnOnce() + Send + 'static>;

pub struct ThreadPool {
    workers: Vec<Worker>,
    sender: Option<mpsc::Sender<Job>>,
}

impl ThreadPool {
    /// Khởi tạo một ThreadPool mới với `size` luồng xử lý.
    ///
    /// # Panics
    /// Hàm sẽ panic nếu `size == 0`.
    pub fn new(size: usize) -> ThreadPool {
        assert!(size > 0, "Số lượng luồng trong ThreadPool phải lớn hơn 0!");

        let (sender, receiver) = mpsc::channel();
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

    pub fn execute<F>(&self, f: F)
    where
        F: FnOnce() + Send + 'static,
    {
        let job = Box::new(f);
        self.sender.as_ref().unwrap().send(job).unwrap();
    }
}

impl Drop for ThreadPool {
    fn drop(&mut self) {
        // Hủy sender để đóng kênh truyền, báo hiệu cho mọi Worker dừng vòng lặp:
        drop(self.sender.take());

        println!("🛑 Đang đóng toàn bộ các Worker threads an toàn...");

        for worker in &mut self.workers {
            println!("⏳ Đang chờ Worker #{} hoàn tất công việc...", worker.id);

            if let Some(thread) = worker.thread.take() {
                thread.join().unwrap();
            }
        }

        println!("✅ Toàn bộ Web Server đã tắt an toàn (Graceful Shutdown)!");
    }
}

struct Worker {
    id: usize,
    thread: Option<thread::JoinHandle<()>>,
}

impl Worker {
    fn new(id: usize, receiver: Arc<Mutex<mpsc::Receiver<Job>>>) -> Worker {
        let thread = thread::spawn(move || loop {
            // 💡 CHÚ Ý QUAN TRỌNG VỀ VÒNG ĐỜI KHÓA MUTEXGUARD:
            // Khi dùng câu lệnh `let message = ...;`, đối tượng tạm `MutexGuard` sinh ra từ `.lock()`
            // sẽ tự động được giải phóng (drop) NGAY TẠI DẤU CHẤM PHẨY `;` khi `.recv()` vừa lấy xong Job!
            // Nhờ đó khóa Mutex được mở ra ngay lập tức trước khi `job()` thực thi,
            // giúp các Worker khác nhận công việc song song thực sự!
            let message = receiver.lock().unwrap().recv();

            match message {
                Ok(job) => {
                    println!("👷 Worker #{id} nhận công việc; đang thực thi...");
                    job();
                }
                Err(_) => {
                    println!("👋 Worker #{id} nhận tín hiệu đóng kênh; đang dừng luồng.");
                    break;
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

> ⚠️ **Cảnh báo kinh điển với `while let` và `MutexGuard`:** Nếu trong `Worker::new`, bạn viết `while let Ok(job) = receiver.lock().unwrap().recv() { job(); }`, thì biến tạm `MutexGuard` trong điều kiện của `while let` sẽ **bị giữ chặt trong suốt toàn bộ khối lệnh `{ job(); }`**! Hậu quả là các luồng Worker khác không thể lấy khóa để nhận request mới cho đến khi `job()` chạy xong, biến Web Server đa luồng thành đơn luồng tuần tự!

---

### 24.3. 🌐 Mã Nguồn Máy Chủ HTTP (`src/main.rs`)

```rust
use std::fs;
use std::io::{prelude::*, BufReader};
use std::net::{TcpListener, TcpStream};
use std::thread;
use std::time::Duration;
use web_server::ThreadPool;

fn main() {
    let listener = TcpListener::bind("127.0.0.1:7878").unwrap();
    let pool = ThreadPool::new(4);

    println!("=======================================================");
    println!(" 🌐 Rust Web Server đang chạy tại http://127.0.0.1:7878 ");
    println!("=======================================================");

    // Dùng .take(5) nếu muốn thử nghiệm tự động Graceful Shutdown sau 5 requests,
    // hoặc bỏ .take(5) để chạy liên tục vĩnh viễn:
    for stream in listener.incoming() {
        let stream = stream.unwrap();

        pool.execute(|| {
            handle_connection(stream);
        });
    }
}

fn handle_connection(mut stream: TcpStream) {
    let buf_reader = BufReader::new(&stream);
    let request_line = match buf_reader.lines().next() {
        Some(Ok(line)) => line,
        _ => return,
    };

    let (status_line, filename) = match &request_line[..] {
        "GET / HTTP/1.1" => ("HTTP/1.1 200 OK", "hello.html"),
        "GET /sleep HTTP/1.1" => {
            thread::sleep(Duration::from_secs(5));
            ("HTTP/1.1 200 OK", "hello.html")
        }
        _ => ("HTTP/1.1 404 NOT FOUND", "404.html"),
    };

    let contents = fs::read_to_string(filename).unwrap_or_else(|_| {
        String::from("<!DOCTYPE html><html><body><h1>🦀 Rust Web Server</h1></body></html>")
    });
    let length = contents.len();

    let response = format!("{status_line}\r\nContent-Length: {length}\r\n\r\n{contents}");
    stream.write_all(response.as_bytes()).unwrap();
}
```

---

# 📖 PHẦN XI: PHỤ LỤC CẨM NANG RUSTACEAN TOÀN DIỆN

---

## PHỤ LỤC A: 🔑 BẢNG TỪ KHÓA TRONG RUST (KEYWORDS & RAW IDENTIFIERS)

### 1️⃣ Các Từ Khóa Đang Sử Dụng (Keywords Currently in Use)

| 🔑 Từ khóa | 📌 Ý nghĩa và Công dụng chính |
| :--- | :--- |
| `as` | Ép kiểu nguyên thủy, giải quyết xung đột tên Trait, hoặc đổi tên định danh trong `use` |
| `async` | Biến một hàm, khối lệnh hoặc closure thành trả về một `Future` |
| `await` | Tạm dừng thực thi hàm `async` cho đến khi kết quả của `Future` sẵn sàng |
| `break` | Thoát khỏi vòng lặp ngay lập tức (có thể trả về giá trị từ `loop`) |
| `const` | Định nghĩa hằng số thời điểm biên dịch, hằng số generic hoặc con trỏ thô hằng |
| `continue` | Bỏ qua phần còn lại của lượt lặp hiện tại và chuyển sang lượt lặp kế tiếp |
| `crate` | Chỉ định gốc của crate hiện tại trong đường dẫn module (`crate::...`) |
| `dyn` | Đánh dấu kiểu phân phối động của một Trait Object (`dyn Trait`) |
| `else` | Nhánh rẽ dự phòng cho cấu trúc `if`, `if let`, hoặc `let else` |
| `enum` | Định nghĩa một kiểu dữ liệu liệt kê nhiều biến thể |
| `extern` | Liên kết với các hàm hoặc biến bên ngoài qua FFI (`unsafe extern "C"`) |
| `false` / `true` | Hai giá trị hằng logic của kiểu `bool` |
| `fn` | Khai báo hàm hoặc kiểu con trỏ hàm (`fn(i32) -> i32`) |
| `for` | Vòng lặp duyệt qua iterator, cài đặt Trait (`impl Trait for Type`), hoặc `for<'a>` |
| `if` | Biểu thức rẽ nhánh điều kiện |
| `impl` | Khối triển khai phương thức tự thân hoặc cài đặt Trait cho một kiểu |
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
| `union` | Khai báo kiểu hợp nhất bộ nhớ tương thích C union |
| `unsafe` | Mở khối mã, định nghĩa hàm, trait hoặc khối extern không an toàn |
| `use` | Đưa các đường dẫn bên ngoài vào phạm vi hiện tại |
| `where` | Mệnh đề ràng buộc Trait Bound ở cuối chữ ký hàm/khối `impl` |
| `while` | Vòng lặp có điều kiện |

### 2️⃣ Từ Khóa Dự Phòng (Reserved Keywords) & Định Danh Thô (`r#`)
- **Từ khóa dự phòng:** `abstract`, `become`, `box`, `do`, `final`, **`gen`** *(mới từ Rust 2024)*, `macro`, `override`, `priv`, `try`, `typeof`, `unsized`, `virtual`, `yield`.
- **Định danh thô (`Raw Identifiers r#`):** Cho phép sử dụng từ khóa làm tên biến hoặc tên hàm (rất hữu ích khi tích hợp với thư viện ngoài hoặc JSON có trường tên `match` hay `type`):
  ```rust
  let r#match = "giá trị hợp lệ";
  ```

---

## PHỤ LỤC B: 🔣 BẢNG TOÁN TỬ & KÝ HIỆU CÚ PHÁP

| ⚡ Ký hiệu | 📌 Ý nghĩa trong ngữ cảnh Rust |
| :--- | :--- |
| `!` | Gọi macro (`println!`, `vec!`), toán tử phủ định logic NOT, hoặc kiểu Never Type (`!`) |
| `?` | Toán tử lan truyền lỗi sớm trong hàm trả về `Result` hoặc `Option` |
| `&` / `&mut` | Mượn tham chiếu bất biến (`&T`) / Mượn tham chiếu khả biến độc quyền (`&mut T`) |
| `&raw const` / `&raw mut` | Tạo con trỏ thô an toàn không qua tham chiếu trung gian (Chuẩn Rust 2024) |
| `*` | Toán tử giải tham chiếu (*Dereference*), phép nhân, hoặc khai báo con trỏ thô (`*const T`) |
| `::` | Toán tử phân giải đường dẫn module, biến thể enum hoặc hàm liên kết (`Vec::new()`) |
| `->` | Khai báo kiểu trả về của hàm hoặc closure |
| `=>` | Tách mẫu đối sánh và biểu thức thực thi trong nhánh `match` |
| `..` / `..=` | Dải số nửa mở `a..b` ($[a, b)$) / Dải số đóng `a..=b` ($[a, b]$), hoặc cập nhật/bỏ qua phần tử |
| `@` | Ràng buộc giá trị vào biến khi đang kiểm tra khớp mẫu trong `match` |
| `'a` | Ký hiệu tham số vòng đời (*Lifetime*) hoặc nhãn vòng lặp (`'outer: loop`) |
| `_` | Mẫu giữ chỗ bỏ qua giá trị (*Wildcard pattern*) hoặc dấu phân cách số `1_000_000` |

---

## PHỤ LỤC C: ⚙️ CÁC TRAIT CÓ THỂ TỰ ĐỘNG DẪN XUẤT (DERIVABLE TRAITS)

Khi đặt thuộc tính `#[derive(...)]` ngay trên khai báo `struct` hoặc `enum`, trình biên dịch sẽ tự động sinh mã cài đặt chuẩn cho các Trait sau:

1. 🔍 **`Debug`:** Cho phép in nội dung đối tượng phục vụ gỡ lỗi qua bộ định dạng `{:?}` và `{:#?}`.
2. 🧬 **`Clone`:** Tự động cài đặt phương thức `.clone()` để nhân bản sâu từng trường dữ liệu.
3. ⚡ **`Copy`:** Đánh dấu kiểu có thể sao chép bit trực tiếp trên Stack thay vì Move quyền sở hữu (yêu cầu kiểu phải đồng thời dẫn xuất `Clone` và mọi trường bên trong đều cài đặt `Copy`).
4. ⚖️ **`PartialEq` & `Eq`:** Cho phép so sánh bằng (`==`) và khác (`!=`). `Eq` bổ sung cam kết tính chất phản xạ tuyệt đối $x == x$ (kiểu số thực `f32`/`f64` chỉ có `PartialEq` mà không có `Eq` vì theo chuẩn IEEE 754: $\text{NaN} \neq \text{NaN}$).
5. 📊 **`PartialOrd` & `Ord`:** Cho phép so sánh thứ tự lớn/nhỏ (`<`, `>`, `<=`, `>=`) để sắp xếp mảng.
6. #️⃣ **`Hash`:** Cho phép băm đối tượng để dùng làm khóa (`Key`) trong `HashMap<K, V>` và `HashSet<T>`.
7. 🏁 **`Default`:** Tự động tạo hàm `Default::default()` khởi tạo các trường với giá trị mặc định ($0$, `false`, `""`, `Vec::new()`).

---

## PHỤ LỤC D: 🧰 BỘ CÔNG CỤ PHÁT TRIỂN & HỆ SINH THÁI PRODUCTION CRATES

### 1️⃣ Công Cụ Phát Triển Chuẩn:
- 🎨 **`cargo fmt` (`rustfmt`):** Tự động định dạng mã nguồn theo chuẩn toàn cầu của Rust.
- 📎 **`cargo clippy`:** Bộ phân tích tĩnh (*Linter*) phát hiện hàng trăm mẫu code chưa tối ưu và gợi ý cách viết chuẩn *idiomatic Rust*.
- 🧠 **`rust-analyzer`:** Trình máy chủ ngôn ngữ (LSP) cung cấp gợi ý mã và hiển thị kiểu dữ liệu tức thì trên VS Code, Neovim, Zed, RustRover.
- 🛡️ **`cargo-audit` & `cargo-expand`:** Kiểm tra lỗ hổng bảo mật của dependencies và bung mã nguồn sinh ra bởi Macro.
- 👻 **`cargo miri`:** Công cụ thông dịch mã MIR của Rust giúp phát hiện chính xác tuyệt đối các lỗi Undefined Behavior, rò rỉ bộ nhớ hoặc vi phạm quy tắc mượn bên trong các khối unsafe và Smart Pointers. (Cài đặt qua: rustup +nightly component add miri).

### 2️⃣ Bảng Thư Viện Thực Chiến Hàng Đầu (Production Crates Cần Biết):

| Lĩnh Vực | Tên Crate | Công Dụng Thực Tế Trong Công Nghiệp |
| :--- | :--- | :--- |
| 🔄 **Serialization** | `serde`, `serde_json` | Chuyển đổi Struct/Enum sang JSON, YAML, TOML, Bincode với tốc độ cao nhất. |
| ⏳ **Async Runtime** | `tokio` | Runtime bất đồng bộ tiêu chuẩn công nghiệp cho hệ thống mạng & Microservices. |
| 🛡️ **Xử lý lỗi** | `thiserror`, `anyhow` | Định nghĩa lỗi chuẩn cho thư viện (`thiserror`) và quản lý lỗi ứng dụng (`anyhow`). |
| 💻 **CLI Tool** | `clap` | Phân tích tham số dòng lệnh chuyên nghiệp tự động qua Derive Macro. |
| 🌐 **Web / Backend** | `axum`, `actix-web` | Xây dựng RESTful API, WebSocket, gRPC (`tonic`) hiệu năng đỉnh cao. |
| 🗄️ **Database / ORM**| `sqlx`, `sea-orm` | Truy vấn SQL bất đồng bộ có kiểm tra cú pháp SQL ngay tại thời điểm biên dịch. |
| 🧮 **Song song dữ liệu**| `rayon` | Biến chuỗi `.iter()` tuần tự thành xử lý đa nhân CPU `.par_iter()` chỉ với $1$ dòng code. |
| 📊 **Observability** | `tracing` | Ghi nhật ký hệ thống có cấu trúc (*structured logging*) và theo dõi phân tán. |

---

## PHỤ LỤC E: 📅 CÁC PHIÊN BẢN RUST EDITIONS (2015, 2018, 2021, 2024)

Rust cam kết nguyên lý **Ổn định không trì trệ (Stability Without Stagnation)**. Cứ mỗi $3$ năm, Rust phát hành một **Edition** mới. Các crate thuộc các Edition khác nhau hoàn toàn có thể liên kết và biên dịch chung với nhau một cách liền mạch! Để nâng cấp dự án lên Edition mới tự động, dùng lệnh: `cargo fix --edition`.

### 🚀 Những Điểm Mới Trọng Tâm Trong Chuẩn Rust 2024 Edition (`rustc 1.85+`):
1. **📌 Quy tắc bắt giữ Lifetime mới cho `impl Trait` (RPIT Lifetime Capture Rules):** Mặc định kiểu trả về `-> impl Trait` sẽ tự động bắt giữ toàn bộ các tham số generic và lifetime trong chữ ký hàm, và hỗ trợ cú pháp chính xác `+ use<'a, T>` để kiểm soát tường minh.
2. **⚡ Chuẩn hóa Async Closures (`async || {}`):** Cho phép định nghĩa các closure bất đồng bộ trực tiếp kèm các trait `AsyncFn`, `AsyncFnMut`, `AsyncFnOnce` trong thư viện chuẩn.
3. **🛡️ Siết chặt an toàn FFI & Unsafe:**
   - Khối liên kết ngoại ngữ bắt buộc phải khai báo tường minh là `unsafe extern "C" { ... }`.
   - Bật cảnh báo mặc định `unsafe_op_in_unsafe_fn`: Bên trong một hàm `unsafe fn`, bạn vẫn phải bọc các thao tác nguy hiểm vào trong khối `unsafe { ... }` nhỏ để khoanh vùng phạm vi rủi ro.
   - Chuẩn hóa toán tử tạo con trỏ thô an toàn `&raw const` và `&raw mut` thay cho việc tạo tham chiếu trung gian.
   - Việc tạo tham chiếu trực tiếp (`&` hoặc `&mut`) tới biến `static mut` đã bị trình biên dịch cấm mặc định (`deny-by-default` do quy tắc `static_mut_refs`). Khi cần thao tác với `static mut`, bạn bắt buộc phải dùng toán tử con trỏ thô `&raw const` / `&raw mut`, hoặc tốt nhất hãy thay thế bằng `LazyLock`, `Mutex` hoặc các kiểu `Atomic`.
4. **🔮 Bảo lưu từ khóa `gen`:** Phục vụ cho tính năng khối sinh dữ liệu tuần tự (*Generator blocks*).
5. **🔒 Chuẩn hóa `LazyLock` và `OnceLock`:** Khởi tạo biến tĩnh lười biếng an toàn đa luồng trực tiếp trong thư viện chuẩn (`std::sync::LazyLock`) mà không cần dùng thêm crate `lazy_static` hay `once_cell` bên ngoài.
6. **🔄 Bổ sung `Future` và `IntoFuture` vào Prelude chuẩn:** Giúp sử dụng trực tiếp trong mọi module mà không cần `use std::future::Future;`.

---

## PHỤ LỤC F: 📏 BẢNG QUY ƯỚC ĐẶT TÊN CHUẨN (IDIOMATIC NAMING CONVENTIONS)

| 🧩 Thực thể mã nguồn | 📐 Quy ước đặt tên | 💡 Ví dụ chuẩn |
| :--- | :--- | :--- |
| 📦 **Packages / Crates** | `snake_case` (ưu tiên) hoặc `kebab-case` | `serde_json`, `tokio_util` |
| 📁 **Modules & Tập tin `.rs`** | `snake_case` | `front_of_house`, `network_io.rs` |
| 🏗️ **Types (Struct, Enum, Trait)**| `UpperCamelCase` (`PascalCase`) | `Rectangle`, `Option`, `Summary` |
| 🎭 **Enum Variants** | `UpperCamelCase` (`PascalCase`) | `Ok`, `Err`, `Some`, `None` |
| ⚙️ **Functions & Methods** | `snake_case` | `add_one`, `calculate_length` |
| 🔢 **Local Variables & Params** | `snake_case` | `secret_number`, `user_input` |
| 📌 **Constants & Statics** | `SCREAMING_SNAKE_CASE` | `MAX_POINTS`, `THREE_HOURS_IN_SECONDS` |
| 🧩 **Type Parameters (Generics)** | Chữ in hoa ngắn gọn (`UpperCamelCase`) | `T`, `U`, `Item`, `Key`, `Error` |
| ⏳ **Lifetimes** | Chữ in thường ngắn có dấu nháy đơn | `'a`, `'b`, `'de`, `'static` |

---

## PHỤ LỤC G: 📘 TỪ ĐIỂN THUẬT NGỮ ANH - VIỆT & 10 NGUYÊN TẮC VÀNG RUSTACEAN

### 1️⃣ Từ Điển Thuật Ngữ Cốt Lõi:
- 🔑 **Ownership:** Quyền sở hữu bộ nhớ.
- 🤝 **Borrowing:** Cơ chế mượn dữ liệu thông qua tham chiếu (`&T`, `&mut T`).
- 🛡️ **Borrow Checker:** Bộ kiểm tra tính hợp lệ của quyền sở hữu và vòng đời mượn tại thời điểm biên dịch.
- ⏳ **Lifetime:** Vòng đời / Thời gian sống hợp lệ của tham chiếu.
- 🚚 **Move Semantics:** Cơ chế dịch chuyển quyền sở hữu làm vô hiệu hóa biến nguồn.
- 🚫 **Dangling Reference / Pointer:** Tham chiếu hoặc con trỏ lơ lửng trỏ vào vùng nhớ đã bị giải phóng.
- 💥 **Data Race:** Hiện tượng xung đột dữ liệu đa luồng.
- 💎 **Zero-Cost Abstraction:** Trừu tượng hóa bậc cao không làm phát sinh chi phí hiệu năng tại runtime.
- ⚡ **Monomorphization:** Cơ chế đơn hình hóa, sinh mã máy riêng biệt cho từng kiểu Generic lúc biên dịch.
- 📜 **Trait & Trait Object:** Đặc tính hành vi & Đối tượng đặc tính đa hình động (`dyn Trait`) qua bảng `vtable`.
- 🧭 **Smart Pointer:** Con trỏ thông minh sở hữu vùng nhớ và tự động quản lý tài nguyên.
- 🔓 **Interior Mutability:** Tính khả biến nội tại, cho phép sửa đổi dữ liệu qua tham chiếu bất biến (`RefCell`, `Mutex`).
- 🗑️ **RAII (Resource Acquisition Is Initialization):** Khởi tạo gắn liền với thu hồi tài nguyên tự động qua Trait `Drop`.
- ✅ **Soundness:** Tính chặt chẽ toán học đảm bảo mã Unsafe được đóng gói không bao giờ gây ra Undefined Behavior.

---

### 2️⃣ 🏆 Mười Nguyên Tắc Vàng Để Làm Chủ Ngôn Ngữ Rust

1. 🎧 **Đừng chiến đấu với Borrow Checker — hãy lắng nghe nó:** Thông báo lỗi của `rustc` là người thầy tận tâm nhất. Nó không gây khó dễ cho bạn, mà đang ngăn chặn một lỗi sập hệ thống nghiêm trọng trong tương lai.
2. 🔒 **Ưu tiên Bất biến (Immutability First):** Luôn dùng `let` làm mặc định và chỉ thêm `mut` khi thực sự cần thay đổi trạng thái.
3. 🤝 **Mượn (`&T`, `&str`) thay vì Sao chép (`.clone()`):** Đừng lạm dụng `.clone()` chỉ để lách qua Borrow Checker; hãy thiết kế luồng truyền tham chiếu rõ ràng.
4. 🌳 **Thiết kế dữ liệu theo cấu trúc Cây (Tree-like Ownership):** Hạn chế các cấu trúc trỏ vòng tròn phức tạp; nếu cần đồ thị, hãy cân nhắc dùng chỉ mục mảng (*Arena / Index-based Graph*) hoặc kết hợp `Rc` với `Weak`.
5. 🛡️ **Khai thác triệt để `Option<T>`, `Result<T, E>` và toán tử `?`:** Tuyệt đối không lạm dụng `.unwrap()` trong mã nguồn Production.
6. 🏆 **Mã hóa quy tắc nghiệp vụ vào Hệ thống Kiểu (Typestate & Newtype Pattern):** Biến các trạng thái bất hợp lệ thành lỗi biên dịch để chúng không bao giờ có thể xảy ra tại runtime.
7. 🔁 **Tận dụng sức mạnh của Iterators:** Chuỗi phương thức `.iter().filter().map().collect()` vừa trong sáng, an toàn, vừa được trình biên dịch tối ưu hóa vector hóa cực nhanh.
8. 🗂️ **Phân tách rõ `main.rs` và `lib.rs`:** Đưa toàn bộ logic nghiệp vụ vào `lib.rs` để dễ dàng viết Unit Tests, Integration Tests và Doctests.
9. 🚀 **Chọn đúng mô hình đồng thời:** Dùng `async/await` (`Tokio`) cho bài toán chờ đợi mạng I/O lớn; dùng OS Threads hoặc `rayon` cho bài toán tính toán nặng CPU; ưu tiên truyền thông điệp qua kênh (`mpsc`) hơn là chia sẻ khóa.
10. ⚠️ **Tối thiểu hóa và cô lập `unsafe`:** Chỉ dùng `unsafe` khi thực sự cần thiết (như FFI), luôn bọc trong một hàm Safe Rust và viết chú thích `// SAFETY: ...` chứng minh tính an toàn của khối lệnh.

---

> ### 📬 LIÊN HỆ & ĐÓNG GÓP
> Tài liệu **`RUST_OZ_V`** được biên soạn, chuẩn hóa và hoàn thiện bởi **Thái Việt**.  
> - **📧 Email:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)  
> - **🐙 GitHub:** [https://github.com/ozsx](https://github.com/ozsx)
> 
> *🎉 CHÚC BẠN CÓ MỘT HÀNH TRÌNH KHÁM PHÁ VÀ LÀM CHỦ NGÔN NGỮ LẬP TRÌNH RUST THẬT NHIỀU CẢM HỨNG VÀ THÀNH CÔNG RỰC RỠ! 🦀🚀*