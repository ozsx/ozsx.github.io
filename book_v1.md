# 🦀 RUST TOÀN TẬP 🚀
*📚 Tài liệu học tập toàn diện từ cơ bản đến chuyên sâu*

> 👤 **Tác giả:** **Thái Việt**  
> 📧 **Email liên hệ:** [ozsxe@icloud.com](mailto:ozsxe@icloud.com)  
> 🐙 **GitHub:** [github.com/ozsx](https://github.com/ozsx)  
> 🏷️ **Phiên bản:** 2024

---

## 🌟 LỜI NÓI ĐẦU & TRIẾT LÝ THIẾT KẾ CỦA RUST

Ngôn ngữ lập trình **Rust** được khởi xướng bởi Graydon Hoare tại Mozilla Research và ra mắt phiên bản 1.0 ổn định vào năm 2015. Rust được thiết kế để giải quyết bài toán nan giải tồn tại suốt hàng thập kỷ trong khoa học máy tính: **Làm thế nào để đạt được hiệu năng tối đa của ngôn ngữ hệ thống cấp thấp (như C/C++) mà vẫn đảm bảo tính an toàn bộ nhớ tuyệt đối (memory safety) và an toàn đa luồng (concurrency safety) mà không cần đến bộ thu gom rác (Garbage Collector - GC)?**

### 🏛️ Tam Trụ Cốt Lõi Của Rust:
1. 🛡️ **An toàn bộ nhớ tại thời điểm biên dịch (Compile-time Memory Safety):** Rust loại bỏ hoàn toàn các lỗi kinh điển như *Null Pointer Dereference*, *Use-After-Free*, *Double Free*, và *Buffer Overflow* thông qua hệ thống **Ownership (Quyền sở hữu)** và **Borrow Checker (Bộ kiểm tra mượn)**.
2. ⚡ **Trừu tượng hóa không chi phí (Zero-Cost Abstractions):** Các tính năng trừu tượng bậc cao như Generics, Traits, Closures, Iterators và Pattern Matching được biên dịch thành mã máy tối ưu hóa ngang bằng hoặc tốt hơn mã viết tay bằng C/C++. *"Những gì bạn không dùng thì không phải trả phí; những gì bạn dùng thì bạn không thể tự viết tốt hơn"* (Bjarne Stroustrup).
3. 🧵 **Lập trình đồng thời không sợ hãi (Fearless Concurrency):** Hệ thống kiểu dữ liệu và quyền sở hữu ngăn chặn lỗi xung đột dữ liệu đa luồng (*Data Races*) ngay từ lúc biên dịch. Nếu mã nguồn biên dịch thành công, nó được đảm bảo không xảy ra data race.

---

## 🗺️ MỤC LỤC TỔNG QUAN

- 🏁 **[PHẦN I: KHỞI ĐỘNG & NỀN TẢNG CỐT LÕI](#-phần-i-khởi-động--nền-tảng-cốt-lõi)**
  - 📦 [Chương 1: Bắt đầu với Rust & Hệ sinh thái Cargo](#-chương-1-bắt-đầu-với-rust--hệ-sinh-thái-cargo)
  - 🎮 [Chương 2: Dự án 1 — Trò chơi Đoán số (Guessing Game)](#-chương-2-dự-án-1--trò-chơi-đoán-số-guessing-game)
  - 🧱 [Chương 3: Các khái niệm Lập trình Phổ biến](#-chương-3-các-khái-niệm-lập-trình-phổ-biến)
- 🔐 **[PHẦN II: TRỌNG TÂM RUST — HỆ THỐNG QUYỀN SỞ HỮU](#-phần-ii-trọng-tâm-rust--hệ-thống-quyền-sở-hữu)**
  - ❤️ [Chương 4: Quyền sở hữu (Ownership) — Trái tim của Rust](#️-chương-4-quyền-sở-hữu-ownership--trái-tim-của-rust)
  - 🏗️ [Chương 5: Gom nhóm Dữ liệu Liên quan với Structs](#️-chương-5-gom-nhóm-dữ-liệu-liên-quan-với-structs)
  - 🎯 [Chương 6: Kiểu Liệt kê Enums & Khớp Mẫu Pattern Matching](#-chương-6-kiểu-liệt-kê-enums--khớp-mẫu-pattern-matching)
- 🗂️ **[PHẦN III: TỔ CHỨC DỰ ÁN, CẤU TRÚC DỮ LIỆU & XỬ LÝ LỖI](#️-phần-iii-tổ-chức-dự-án-cấu-trúc-dữ-liệu--xử-lý-lỗi)**
  - 🌳 [Chương 7: Quản lý Dự án với Packages, Crates và Modules](#-chương-7-quản-lý-dự-án-với-packages-crates-và-modules)
  - 🧰 [Chương 8: Các Cấu trúc Dữ liệu Tập hợp Phổ biến (Collections)](#-chương-8-các-cấu-trúc-dữ-liệu-tập-hợp-phổ-biến-collections)
  - 🛡️ [Chương 9: Cơ chế Xử lý Lỗi (Error Handling)](#️-chương-9-cơ-chế-xử-lý-lỗi-error-handling)
- 🧬 **[PHẦN IV: TRỪU TƯỢNG HÓA, KIỂM THỬ & DỰ ÁN MINIGREP](#-phần-iv-trừu-tượng-hóa-kiểm-thử--dự-án-minigrep)**
  - 🧩 [Chương 10: Kiểu Chung (Generics), Traits và Vòng đời (Lifetimes)](#-chương-10-kiểu-chung-generics-traits-và-vòng-đời-lifetimes)
  - 🧪 [Chương 11: Viết Kiểm thử Tự động (Automated Testing)](#-chương-11-viết-kiểm-thử-tự-động-automated-testing)
  - 🔍 [Chương 12: Dự án 2 — Xây dựng Công cụ Dòng lệnh minigrep](#-chương-12-dự-án-2--xây-dựng-công-cụ-dòng-lệnh-minigrep)
- ⚡ **[PHẦN V: LẬP TRÌNH HÀM, QUẢN LÝ BỘ NHỚ & ĐỒNG THỜI](#-phần-v-lập-trình-hàm-quản-lý-bộ-nhớ--đồng-thời)**
  - 🔄 [Chương 13: Lập trình Hàm: Closures và Iterators](#-chương-13-lập-trình-hàm-closures-và-iterators)
  - 🚢 [Chương 14: Thêm về Cargo và Crates.io](#-chương-14-thêm-về-cargo-và-cratesio)
  - 🧠 [Chương 15: Con trỏ Thông minh (Smart Pointers)](#-chương-15-con-trỏ-thông-minh-smart-pointers)
- 🏆 **[PHẦN VI: NÂNG CAO, DỰ ÁN WEB SERVER & CẨM NANG](#-phần-vi-nâng-cao-dự-án-web-server--cẩm-nang)**
  - 🧵 [Chương 16: Lập trình Đồng thời Không sợ hãi (Fearless Concurrency)](#-chương-16-lập-trình-đồng-thời-không-sợ-hãi-fearless-concurrency)
  - ⏳ [Chương 17: Lập trình Bất đồng bộ (Async / Await)](#-chương-17-lập-trình-bất-đồng-bộ-async--await)
  - 🎭 [Chương 18: Các Tính năng Hướng đối tượng của Rust (OOP)](#-chương-18-các-tính-năng-hướng-đối-tượng-của-rust-oop)
  - 🕸️ [Chương 19: Khớp Mẫu Nâng cao (Patterns and Matching)](#️-chương-19-khớp-mẫu-nâng-cao-patterns-and-matching)
  - 🧙‍♂️ [Chương 20: Các Tính năng Nâng cao (Advanced Features)](#️-chương-20-các-tính-năng-nâng-cao-advanced-features)
  - 🌐 [Chương 21: Dự án 3 — Xây dựng Multithreaded Web Server](#-chương-21-dự-án-3--xây-dựng-multithreaded-web-server)
- 📖 **[PHẦN VII: PHỤ LỤC & BẢNG TRA CỨU CHUẨN](#-phần-vii-phụ-lục--bảng-tra-cứu-chuẩn)**
  - 🔑 [Phụ lục A: Bảng Từ khóa Trong Rust (Keywords)](#-phụ-lục-a-bảng-từ-khóa-trong-rust-keywords)
  - 🔣 [Phụ lục B: Bảng Toán tử & Ký hiệu Cú pháp](#-phụ-lục-b-bảng-toán-tử--ký-hiệu-cú-pháp)
  - ⚙️ [Phụ lục C: Các Trait Có thể Tự động Dẫn xuất (Derivable Traits)](#️-phụ-lục-c-các-trait-có-thể-tự-động-dẫn-xuất-derivable-traits)
  - 🛠️ [Phụ lục D: Các Công cụ Phát triển Hữu ích trong Hệ sinh thái](#️-phụ-lục-d-các-công-cụ-phát-triển-hữu-ích-trong-hệ-sinh-thái)
  - 📅 [Phụ lục E: Các Phiên bản Rust Editions (2015, 2018, 2021, 2024)](#-phụ-lục-e-các-phiên-bản-rust-editions)
  - 🏷️ [Phụ lục F: Quy ước Đặt tên Chuẩn (Idiomatic Naming Conventions)](#️-phụ-lục-f-quy-ước-đặt-tên-chuẩn-idiomatic-naming-conventions)
  - 📚 [Phụ lục G: Từ điển Thuật ngữ Anh - Việt & Cẩm nang Rustacean](#-phụ-lục-g-từ-điển-thuật-ngữ-anh---việt--cẩm-nang-rustacean)
  
---

# 🏁 PHẦN I: KHỞI ĐỘNG & NỀN TẢNG CỐT LÕI

---

## 📦 CHƯƠNG 1: BẮT ĐẦU VỚI RUST & HỆ SINH THÁI CARGO

Rust không chỉ là một ngôn ngữ lập trình độc lập mà là một hệ sinh thái công cụ hiện đại, tối ưu và kiểm soát chất lượng chặt chẽ. Để bắt đầu, bạn cần nắm vững ba công cụ trụ cột: `rustup`, `rustc` và `cargo`.

### 🛠️ 1.1. Cài đặt Môi trường Rust qua `rustup`

`rustup` là công cụ chính thức quản lý các phiên bản trình biên dịch Rust và các công cụ liên quan. Nó hỗ trợ cài đặt, cập nhật, chuyển đổi linh hoạt giữa các kênh phát hành (*stable*, *beta*, *nightly*), và hỗ trợ biên dịch chéo (*cross-compilation*) cho nhiều hệ điều hành và vi xử lý khác nhau.

#### 💻 Hướng dẫn cài đặt theo từng hệ điều hành:

1. 🐧🍎 **Trên Linux hoặc macOS:**
   Mở terminal và thực thi lệnh cài đặt từ trang chủ chính thức của ngôn ngữ Rust (`rust-lang.org`). Bộ cài sẽ tự động thiết lập biến môi trường `PATH` để bạn có thể gọi `rustc` và `cargo` từ bất kỳ đâu.
   
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```

   *⚠️ Yêu cầu bắt buộc:* Cần có sẵn C compiler và Linker (trình liên kết mã).
   - Trên Ubuntu/Debian: `sudo apt update && sudo apt install build-essential`
   - Trên Fedora/RHEL: `sudo dnf groupinstall "Development Tools"`
   - Trên macOS: `xcode-select --install`

2. 🪟 **Trên Windows:**
   Truy cập trang web chính thức của Rust để tải về bộ cài đặt `rustup-init.exe`. Khi cài đặt, chọn mặc định kèm theo **Microsoft C++ Build Tools** (Visual Studio C++ build tools) để cung cấp Linker cần thiết cho môi trường Windows.

#### 🔍 Kiểm tra cài đặt và các lệnh quản trị thiết yếu:

```bash
# Kiểm tra phiên bản trình biên dịch Rust
rustc --version
# Output: rustc 1.85.0 (...)

# Kiểm tra phiên bản công cụ quản lý dự án Cargo
cargo --version
# Output: cargo 1.85.0 (...)

# Cập nhật toàn bộ toolchain Rust lên phiên bản mới nhất
rustup update

# Mở toàn bộ tài liệu chính thức ngoại tuyến (offline) trên trình duyệt web
rustup doc
```

---

### 👋 1.2. Chương trình "Hello, World!" Đầu Tiên

Học một ngôn ngữ mới luôn bắt đầu bằng chương trình in dòng chữ chào mừng. Qua bài học này, bạn sẽ hiểu bản chất biên dịch mã máy độc lập của Rust.

#### 📝 Quy ước đặt tên tập tin:
Trong Rust, tập tin mã nguồn luôn có phần mở rộng là `.rs`. Nếu tên file gồm nhiều từ, quy ước chuẩn (idiomatic Rust) là sử dụng dấu gạch dưới `snake_case`, ví dụ: `hello_world.rs`.

Tạo tập tin `main.rs` với nội dung sau:

```rust
// File: main.rs
// Hàm main là điểm bắt đầu (entry point) của mọi chương trình Rust thực thi
fn main() {
    println!("Hello, world!");
}
```

#### 🔬 Mổ xẻ chi tiết từng thành phần:
- 🔹 `fn main()`: Khai báo hàm `main`. Hàm `main` là hàm đặc biệt nhất, luôn là đoạn mã đầu tiên được thực thi khi chạy file nhị phân. Dấu ngoặc đơn `()` chứa danh sách tham số (ở đây không có tham số nào). Thân hàm nằm trọn trong cặp ngoặc nhọn `{}`.
- 🔹 `println!("Hello, world!");`: In chuỗi ký tự ra màn hình kèm ký tự xuống dòng. Dấu chấm than `!` ở sau tên `println` biểu thị rằng bạn đang gọi một **Macro**, không phải hàm thông thường. Macro cho phép kiểm tra định dạng chuỗi ngay tại thời điểm biên dịch.
- 🔹 Dấu chấm phẩy `;`: Đánh dấu kết thúc câu lệnh.

#### ⚙️ Biên dịch và Chạy:
Rust là ngôn ngữ biên dịch trước (Ahead-Of-Time compiled). Trình biên dịch `rustc` dịch thẳng mã nguồn thành tập tin nhị phân thực thi độc lập (executable binary):

```bash
# Biên dịch file main.rs thành file thực thi
rustc main.rs

# Chạy file nhị phân vừa tạo
# Trên Linux/macOS:
./main

# Trên Windows:
.\main.exe

# Kết quả in ra màn hình:
# Hello, world!
```

---

### 🚛 1.3. Hệ Thống Quản Lý Dự Án Cargo Chuyên Sâu

Trong các dự án thực tế, mã nguồn sẽ phân tán trên nhiều tập tin và tích hợp hàng chục thư viện ngoài (trong Rust gọi là **crates**). Bạn sẽ không gọi `rustc` trực tiếp mà luôn sử dụng **Cargo** — trình quản lý gói và hệ sinh thái build chính thức của Rust.

#### ✨ Khởi tạo dự án mới với Cargo:

```bash
cargo new hello_cargo
cd hello_cargo
```

Lệnh trên sẽ tự động khởi tạo cấu trúc thư mục chuẩn:

```text
hello_cargo/
├── .git/               # Khởi tạo sẵn git repository
├── .gitignore          # Cấu hình bỏ qua thư mục build /target
├── Cargo.toml          # Tập tin cấu hình metadata và dependencies
└── src/
    └── main.rs         # Mã nguồn chính của chương trình
```

#### 📄 Cấu trúc tập tin cấu hình `Cargo.toml`:
Tập tin này viết bằng định dạng TOML (*Tom's Obvious, Minimal Language*):

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2024"

[dependencies]
# Nơi khai báo các crate bên ngoài từ kho trung tâm Crates.io
```

- 📌 `[package]`: Khai báo thông tin dự án gồm tên gói, phiên bản phát hành theo chuẩn SemVer (`MAJOR.MINOR.PATCH`), và phiên bản ấn bản Rust (`edition`).
- 📌 `[dependencies]`: Danh sách các crate bên ngoài mà dự án phụ thuộc.

#### ⚡ Vòng đời các lệnh Cargo thiết yếu:
1. ✅ `cargo check`: Quét cú pháp và kiểm tra kiểu dữ liệu của mã nguồn cực nhanh mà không sinh mã máy thực thi. Trong quá trình lập trình hàng ngày, bạn sẽ chạy lệnh này liên tục để kiểm tra lỗi.
2. 🔨 `cargo build`: Biên dịch toàn bộ dự án ở chế độ phát triển (*debug mode*). Kết quả được lưu tại `target/debug/hello_cargo`. Quá trình này không bật tối ưu hóa mã để tăng tốc độ biên dịch và chèn thêm thông tin gỡ lỗi (*debug symbols*).
3. ▶️ `cargo run`: Tự động kiểm tra thay đổi, biên dịch nếu cần, và thực thi chương trình ngay lập tức.
4. 🚀 `cargo build --release`: Biên dịch dự án ở chế độ xuất bản thương mại (*release mode*). Trình biên dịch sẽ bật cờ tối ưu hóa cấp cao nhất (`opt-level = 3`), loại bỏ debug symbols, thực hiện inlining hàm và vector hóa để chương trình đạt tốc độ thực thi tối đa. Kết quả lưu tại `target/release/hello_cargo`.
5. 🔒 `Cargo.lock`: Khi bạn biên dịch dự án lần đầu có phụ thuộc, Cargo tự động tạo tập tin `Cargo.lock`. Tập tin này ghi lại chính xác mã băm (hash) và phiên bản của tất cả các crate phụ thuộc, đảm bảo tính chất **Reproducible Builds** (bất kỳ ai kéo code về máy đều tải chính xác 100% phiên bản thư viện giống bạn).

---

## 🎮 CHƯƠNG 2: DỰ ÁN 1 — TRÒ CHƠI ĐOÁN SỐ (GUESSING GAME)

Để biến lý thuyết thành kỹ năng thực tế, Chương 2 sẽ hướng dẫn bạn tự tay xây dựng một trò chơi tương tác qua dòng lệnh: **Chương trình sinh ra một số ngẫu nhiên bí mật từ 1 đến 100, và người chơi sẽ nhập các số dự đoán cho đến khi đoán trúng**.

Dự án này giúp bạn làm quen ngay với:
- ⌨️ Nhập/xuất chuẩn (`std::io`).
- 🔄 Biến bất biến và khả biến (`mut`).
- 📦 Thêm crate ngoài qua `Cargo.toml`.
- 🎯 Khớp mẫu đa nhánh (`match`) và kiểu `Ordering`.
- 🛡️ Xử lý lỗi phục hồi được với `Result`.
- 🔁 Vòng lặp điều khiển `loop` và thoát vòng lặp với `break`.

### 📥 2.1. Thêm Crate `rand` vào `Cargo.toml`

Để sinh số ngẫu nhiên, chúng ta sử dụng thư viện chuẩn của cộng đồng là `rand`. Mở `Cargo.toml` và thêm vào mục dependencies:

```toml
[dependencies]
rand = "0.8.5"
```

Khi bạn chạy `cargo build`, Cargo sẽ kết nối đến registry trung tâm `crates.io`, tự động tải `rand` cùng toàn bộ cây phụ thuộc của nó về máy.

---

### 💻 2.2. Toàn Bộ Mã Nguồn Dự Án Hoàn Chỉnh (`src/main.rs`)

```rust
use std::io;                      // Nạp module nhập/xuất chuẩn từ thư viện std
use std::cmp::Ordering;           // Nạp enum so sánh: Less, Greater, Equal
use rand::Rng;                    // Nạp trait Rng để có phương thức gen_range

fn main() {
    println!("========================================");
    println!("  🎲 TRÒ CHƠI ĐOÁN SỐ BÍ MẬT (RUST) 🎲  ");
    println!("========================================");

    // Sinh số ngẫu nhiên bí mật trong khoảng [1, 100]
    // thread_rng() tạo bộ sinh số cục bộ trên luồng hiện tại
    // gen_range(1..=100) sử dụng cú pháp Inclusive Range (bao gồm cả 1 và 100)
    let secret_number = rand::thread_rng().gen_range(1..=100);

    // Vòng lặp vô hạn loop cho phép người chơi đoán liên tục đến khi đúng
    loop {
        println!("\n👉 Vui lòng nhập số dự đoán của bạn (từ 1 đến 100):");

        // Khai báo biến 'guess' có thể thay đổi được (mutable)
        // String::new() tạo một chuỗi rỗng có thể co giãn trên Heap
        let mut guess = String::new();

        // Đọc dữ liệu từ bàn phím vào biến guess
        // &mut guess truyền vào một tham chiếu khả biến để hàm ghi đè dữ liệu
        io::stdin()
            .read_line(&mut guess)
            .expect("Lỗi: Không thể đọc dữ liệu từ bàn phím!");

        // Kỹ thuật Shadowing: Tái sử dụng tên biến 'guess' để ép kiểu từ String sang u32
        // trim() loại bỏ khoảng trắng và ký tự xuống dòng
        // parse() chuyển chuỗi ký tự thành kiểu số
        // match xử lý enum Result trả về từ parse():
        // - Ok(num): Gán số hợp lệ vào biến guess
        // - Err(_): Bỏ qua lỗi gõ phím sai, yêu cầu người chơi nhập lại
        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => {
                println!(">> ⚠️ Cảnh báo: Vui lòng nhập một số nguyên dương hợp lệ!");
                continue; // Chuyển sang vòng lặp tiếp theo
            }
        };

        println!("🎯 Bạn đã đoán: {}", guess);

        // So sánh số người chơi đoán với số bí mật
        // cmp() trả về enum Ordering (Less, Greater, hoặc Equal)
        // match bắt buộc phải kiểm tra vét cạn (exhaustive) mọi khả năng
        match guess.cmp(&secret_number) {
            Ordering::Less => println!(">> 📉 Kết quả: Quá nhỏ! Hãy thử số lớn hơn."),
            Ordering::Greater => println!(">> 📈 Kết quả: Quá lớn! Hãy thử số nhỏ hơn."),
            Ordering::Equal => {
                println!("========================================");
                println!(" 🎉 CHÚC MỪNG! BẠN ĐÃ ĐOÁN CHÍNH XÁC: {} ", secret_number);
                println!("========================================");
                break; // Thoát khỏi vòng lặp loop, kết thúc chương trình
            }
        }
    }
}
```

---

### 🔍 2.3. Giải Thích Chuyên Sâu Từng Khái Niệm Trong Dự Án 1

#### 1. 🔒 Tại sao phải dùng `let mut guess` thay vì `let guess`?
Trong Rust, mọi biến mặc định đều là **Bất biến (Immutable)**. Nếu bạn viết `let guess = String::new();` và sau đó truyền `&mut guess` vào `read_line`, trình biên dịch sẽ từ chối dịch với lỗi:
`cannot borrow immutable local variable guess as mutable`.
Triết lý của Rust là: *Bất biến là mặc định, khả biến phải rõ ràng*. Bạn chỉ thêm `mut` khi thực sự cần thay đổi giá trị.

#### 2. 🔗 Tham chiếu khả biến `&mut guess`:
Ký tự `&` biểu thị đây là một **Tham chiếu (Reference)** — cho phép hàm `read_line` truy cập và chỉnh sửa vùng nhớ của `guess` mà không cần chiếm quyền sở hữu (ownership) của biến. Ký tự `mut` sau dấu `&` chỉ rõ đây là tham chiếu có quyền ghi.

#### 3. 🛡️ Kiểu dữ liệu `Result` và phương thức `.expect()`:
`read_line` trả về một kiểu dữ liệu đặc biệt là `Result<usize, std::io::Error>`. `Result` là một enum có hai nhánh:
- `Ok(value)`: Tác vụ I/O thành công, chứa số byte đã đọc.
- `Err(error)`: Tác vụ thất bại, chứa thông tin lỗi hệ thống.
Nếu bạn không gọi `.expect()` hoặc không xử lý `Result`, trình biên dịch `rustc` sẽ cảnh báo: *`unused std::result::Result that must be used`*. Rust buộc lập trình viên phải chủ động đối mặt với lỗi tiềm ẩn ngay lúc viết code.

#### 4. 👥 Kỹ thuật Che bóng biến (Shadowing):
Để ý đoạn mã:
```rust
let mut guess = String::new(); // guess là kiểu String
// ...
let guess: u32 = match guess.trim().parse() { ... }; // guess trở thành kiểu u32
```
Thay vì phải tạo hai biến với tên vụng về như `guess_str` và `guess_number`, Rust cho phép ta khai báo lại biến `guess` bằng từ khóa `let`. Kỹ thuật này gọi là **Shadowing**. Biến mới sẽ che bóng biến cũ và có quyền đổi kiểu dữ liệu hoàn toàn khác.

---

## 🧱 CHƯƠNG 3: CÁC KHÁI NIỆM LẬP TRÌNH PHỔ BIẾN

Chương này đi sâu vào các khối xây dựng nền tảng của mọi chương trình Rust: biến, kiểu dữ liệu, hàm và luồng điều khiển.

### 🔒 3.1. Biến (Variables) và Tính Khả Biến (Mutability)

Trong Rust, biến mặc định là bất biến:

```rust
fn main() {
    let x = 5;
    println!("Giá trị của x là: {x}");
    // x = 6; // ❌ LỖI BIÊN DỊCH: cannot assign twice to immutable variable `x`
}
```

Khi cần thay đổi, sử dụng từ khóa `mut`:

```rust
fn main() {
    let mut x = 5;
    println!("Giá trị ban đầu của x: {x}");
    x = 6; // ✅ Hợp lệ vì x được khai báo với mut
    println!("Giá trị sau khi đổi của x: {x}");
}
```

#### 📌 Hằng số (Constants):
Hằng số được khai báo bằng từ khóa `const`. Khác với biến bất biến:
- Không bao giờ được phép dùng `mut`.
- Bắt buộc phải chú thích kiểu dữ liệu rõ ràng (Type Annotation).
- Chỉ có thể được gán bằng một biểu thức hằng số có thể tính toán được ngay lúc biên dịch (*constant expression*), không thể gán bằng kết quả của hàm gọi tại runtime.
- Có thể khai báo ở bất kỳ phạm vi nào, kể cả phạm vi toàn cục (*global scope*).

```rust
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

#### ⚖️ Che bóng biến (Shadowing) vs Khả biến (`mut`):
| Tiêu chí | Khả biến (`let mut x`) | Che bóng biến (`let x = ...; let x = ...;`) |
| :--- | :--- | :--- |
| **Đổi giá trị** | ✅ Được | ✅ Được |
| **Đổi kiểu dữ liệu** | ❌ **Không được** (giữ nguyên kiểu ban đầu) | ✅ **Được phép** (tạo biến hoàn toàn mới) |
| **Tính bất biến** | Biến vẫn có thể bị sửa tiếp sau này | Biến mới mặc định bất biến sau phép gán `let` |

```rust
// Shadowing đổi kiểu dữ liệu từ chuỗi sang độ dài (usize):
let spaces = "   ";
let spaces = spaces.len(); // ✅ Hợp lệ!

// Nhưng nếu dùng mut:
let mut spaces = "   ";
// spaces = spaces.len(); // ❌ LỖI BIÊN DỊCH: mismatched types! Mong đợi &str nhưng nhận usize
```

---

### 🔢 3.2. Các Kiểu Dữ Liệu Trong Rust (Data Types)

Rust là ngôn ngữ **kiểm tra kiểu tĩnh (Statically Typed)**: mọi biến đều phải xác định được kiểu dữ liệu tại thời điểm biên dịch. Nếu trình biên dịch không thể tự suy luận kiểu (*Type Inference*), bạn phải cung cấp chú thích kiểu.

#### 🔹 A. Các Kiểu Vô Hướng (Scalar Types):

1. **Số nguyên (Integers):**
   - Có dấu (*signed*, lưu được số âm): `i8`, `i16`, `i32`, `i64`, `i128`, `isize`.
   - Không dấu (*unsigned*, chỉ lưu số không âm): `u8`, `u16`, `u32`, `u64`, `u128`, `usize`.
   - `isize` và `usize` có kích thước phụ thuộc vào kiến trúc máy tính (32-bit trên máy 32-bit, 64-bit trên máy 64-bit), thường dùng để đánh chỉ mục mảng.
   - Mặc định số nguyên trong Rust là `i32`.

   *⚠️ Hiện tượng tràn số nguyên (Integer Overflow):*
   - Trong chế độ debug: Rust kiểm tra và làm chương trình dừng khẩn cấp (**panic**) tại runtime nếu xảy ra tràn số.
   - Trong chế độ release (`--release`): Rust thực hiện phép tính vòng bù hai (*two's complement wrapping*). Ví dụ: `u8` có giá trị `255` khi cộng `1` sẽ quay về `0`.
   - Để xử lý tràn số rõ ràng, bạn có thể dùng các phương thức: `wrapping_add`, `checked_add` (trả về `None` nếu tràn), `overflowing_add`, hoặc `saturating_add` (chạm trần giá trị tối đa).

2. **Số thực dấu phẩy động (Floating-Point Numbers):**
   - `f32` (độ chính xác đơn - single precision, 32 bit).
   - `f64` (độ chính xác kép - double precision, 64 bit). Mặc định là `f64` vì các CPU hiện đại xử lý tốc độ tương đương `f32` nhưng cho độ chính xác cao hơn rất nhiều.

3. **Kiểu Logic (Boolean):**
   - Từ khóa `bool`: nhận hai giá trị `true` hoặc `false`, chiếm 1 byte bộ nhớ.

4. **Kiểu Ký Tự (Character):**
   - Từ khóa `char`: đặt trong dấu nháy đơn `'a'`, chiếm **4 bytes** bộ nhớ.
   - Đại diện cho một giá trị vô hướng Unicode (*Unicode Scalar Value*), hỗ trợ biểu diễn mọi ký tự tiếng Việt có dấu, ký tự Trung/Hàn, và cả biểu tượng cảm xúc Emoji (ví dụ: `'🦀'`).

#### 🔸 B. Các Kiểu Phức Hợp (Compound Types):

1. **Bộ giá trị (Tuple):**
   - Gom nhóm nhiều giá trị với **nhiều kiểu dữ liệu khác nhau** thành một đơn vị duy nhất.
   - Có kích thước cố định sau khi khai báo.

```rust
let tup: (i32, f64, u8) = (500, 6.4, 1);

// Kỹ thuật phân rã Destructuring:
let (x, y, z) = tup;
println!("Giá trị y là: {y}");

// Truy xuất trực tiếp bằng chỉ mục dấu chấm:
let five_hundred = tup.0;
let six_point_four = tup.1;

// Tuple rỗng () gọi là Unit Type (đại diện cho việc không có giá trị trả về)
```

2. **Mảng (Array):**
   - Gom nhóm nhiều phần tử có **cùng một kiểu dữ liệu**.
   - Mảng trong Rust có **độ dài cố định** và được cấp phát trực tiếp trên **Ngăn xếp (Stack)**.
   - Định dạng kiểu: `[Type; Size]`.

```rust
let a: [i32; 5] = [1, 2, 3, 4, 5];

// Khởi tạo mảng gồm 5 phần tử đều có giá trị 0:
let zeros = [0; 5]; // Tương đương [0, 0, 0, 0, 0]

// Truy xuất phần tử bằng chỉ mục:
let first = a[0];
let second = a[1];

// 🛡️ An toàn bộ nhớ: Nếu bạn truy xuất a[10], Rust sẽ panic tại runtime 
// thay vì đọc vùng nhớ rác nguy hiểm như trong C/C++!
```

---

### ⚙️ 3.3. Hàm (Functions) — Phân Biệt Câu Lệnh và Biểu Thức

Hàm được khai báo bằng `fn`. Tham số hàm bắt buộc phải có chú thích kiểu dữ liệu:

```rust
fn print_labeled_measurement(value: i32, unit_label: char) {
    println!("Đo lường: {value}{unit_label}");
}
```

#### ⚖️ Phân biệt Statement (Câu lệnh) vs Expression (Biểu thức):
Đây là một trong những đặc điểm khác biệt lớn nhất giữa Rust và các ngôn ngữ như C, C++, Java hay Python:
- **Câu lệnh (Statement):** Thực hiện một hành động nhưng **KHÔNG trả về giá trị**. Do đó, bạn không thể gán một câu lệnh `let` cho một biến khác (ví dụ: `let x = (let y = 6);` là lỗi cú pháp).
- **Biểu thức (Expression):** Luôn tính toán và **trả về một giá trị**. Khối lệnh `{}` có thể đóng vai trò là một biểu thức!

```rust
fn main() {
    let y = {
        let x = 3;
        x + 1 // 💡 Biểu thức trả về giá trị 4 (KHÔNG có dấu chấm phẩy ở cuối!)
    };
    println!("Giá trị của y là: {y}"); // In ra 4
}
```
*🌟 Quy tắc vàng:* Nếu bạn thêm dấu chấm phẩy `;` vào cuối dòng `x + 1;`, nó sẽ biến thành một câu lệnh và trả về kiểu `()`, làm phép gán thất bại!

#### 📤 Hàm có giá trị trả về:
Dùng ký hiệu mũi tên `->` để khai báo kiểu trả về. Dòng cuối cùng của hàm là biểu thức trả về không có dấu chấm phẩy:

```rust
fn five() -> i32 {
    5 // Tương đương: return 5;
}

fn plus_one(x: i32) -> i32 {
    x + 1 // Không có dấu chấm phẩy
}
```

---

### 🔀 3.4. Luồng Điều Khiển (Control Flow)

#### 1. Biểu thức điều kiện `if`:
Điều kiện trong `if` bắt buộc phải là kiểu `bool`. Rust không tự động ép kiểu số nguyên thành boolean như C (ví dụ: `if number` sẽ báo lỗi biên dịch).

```rust
let number = 6;

if number % 4 == 0 {
    println!("Chia hết cho 4");
} else if number % 3 == 0 {
    println!("Chia hết cho 3");
} else {
    println!("Không chia hết cho 4 hoặc 3");
}
```

*💡 Sử dụng `if` như một biểu thức gán:*
```rust
let condition = true;
// Hai nhánh if và else bắt buộc phải trả về cùng một kiểu dữ liệu:
let number = if condition { 5 } else { 6 };
```

#### 2. 🔁 Vòng lặp `loop`:
Lặp vô hạn cho đến khi gặp `break`. Đặc biệt, `break` trong `loop` có thể trả về một giá trị:

```rust
let mut counter = 0;

let result = loop {
    counter += 1;
    if counter == 10 {
        break counter * 2; // Trả về giá trị 20 và gán vào biến result
    }
};
println!("Kết quả là: {result}");
```

*🏷️ Nhãn vòng lặp (Loop Labels):* Dùng để điều khiển thoát các vòng lặp lồng nhau:
```rust
'outer: loop {
    println!("Vòng lặp ngoài");
    loop {
        println!("Vòng lặp trong");
        break 'outer; // Thoát hẳn khỏi vòng lặp ngoài!
    }
}
```

#### 3. 🔄 Vòng lặp `while`:
Lặp lại chừng nào điều kiện còn đúng:
```rust
let mut number = 3;
while number != 0 {
    println!("{number}!");
    number -= 1;
}
println!("🚀 HOÀN THÀNH!");
```

#### 4. ➡️ Vòng lặp `for`:
Duyệt qua các phần tử của tập hợp hoặc một dải số. Đây là vòng lặp được sử dụng phổ biến và an toàn nhất trong Rust:

```rust
let a = [10, 20, 30, 40, 50];
for element in a {
    println!("Giá trị: {element}");
}

// Lặp qua dải số đếm ngược từ 3 về 1:
for number in (1..4).rev() {
    println!("{number}!");
}
```

---

# 🔐 PHẦN II: TRỌNG TÂM RUST — HỆ THỐNG QUYỀN SỞ HỮU

---

## ❤️ CHƯƠNG 4: QUYỀN SỞ HỮU (OWNERSHIP) — TRÁI TIM CỦA RUST

**Quyền sở hữu (Ownership)** là tính năng độc đáo và đột phá nhất của Rust. Nó cho phép Rust đảm bảo an toàn bộ nhớ tuyệt đối tại thời điểm biên dịch mà không cần đến một bộ thu gom rác (*Garbage Collector - GC*) chạy ngầm làm chậm hiệu năng, cũng không đòi hỏi lập trình viên phải cấp phát và giải phóng bộ nhớ thủ công như C/C++ (*malloc/free*).

---

### 🧠 4.1. Kiến Trúc Bộ Nhớ: Ngăn Xếp (Stack) vs Đống (Heap)

Để hiểu sâu về Ownership, trước hết ta phải phân biệt rõ cách hệ điều hành tổ chức bộ nhớ tiến trình:

```text
+-----------------------------------------------------------------+
|                        KIẾN TRÚC BỘ NHỚ                         |
+------------------------------------+----------------------------+
|      🥞 NGĂN XẾP (STACK)           |       🗄️ ĐỐNG (HEAP)       |
+------------------------------------+----------------------------+
| - Cơ chế LIFO (Vào sau ra trước)   | - Không gian nhớ tự do lớn |
| - Kích thước cố định lúc compile   | - Kích thước động lúc run  |
| - Tốc độ truy xuất cực nhanh       | - Tốc độ truy xuất chậm hơn|
| - Tự động thu hồi khi thoát hàm    | - Cần quản lý vòng đời     |
+------------------------------------+----------------------------+
```

1. 🥞 **Ngăn xếp (Stack):** Lưu trữ dữ liệu có kích thước đã biết trước và cố định tại thời điểm biên dịch (ví dụ: các số nguyên `i32`, `bool`, `char`, mảng cố định, con trỏ). Dữ liệu được đẩy vào và lấy ra theo thứ tự *Last In, First Out*. Do CPU truy cập tuần tự theo đỉnh ngăn xếp nên tốc độ là tối đa.
2. 🗄️ **Đống (Heap):** Lưu trữ dữ liệu có kích thước không cố định hoặc có thể co giãn lúc chạy (ví dụ: `String`, `Vec<T>`). Khi yêu cầu cấp phát bộ nhớ trên Heap, hệ điều hành sẽ tìm một ô nhớ trống đủ lớn, đánh dấu là đang sử dụng và trả về một **con trỏ** chứa địa chỉ ô nhớ đó. Con trỏ này có kích thước cố định nên nó được lưu trên Stack!

---

### 🏆 4.2. Ba Quy Tắc Vàng Của Ownership

Mọi chương trình Rust đều phải tuân thủ nghiêm ngặt 3 quy tắc sau:

1. 🥇 **Mỗi giá trị trong Rust đều có một biến duy nhất làm chủ sở hữu (Owner) của nó.**
2. 🥈 **Tại một thời điểm bất kỳ, chỉ có DUY NHẤT MỘT chủ sở hữu.**
3. 🥉 **Khi biến chủ sở hữu đi ra khỏi phạm vi hoạt động (Scope), giá trị của nó sẽ tự động bị hủy và bộ nhớ được giải phóng ngay lập tức.**

#### 🔭 Phạm vi biến (Variable Scope):
Phạm vi là vùng trong mã nguồn mà một biến được xem là hợp lệ:

```rust
{                      // s chưa xuất hiện ở đây
    let s = "hello";   // s bắt đầu hợp lệ từ dòng này
    // thao tác với s...
}                      // scope kết thúc, s không còn hợp lệ nữa!
```

---

### 🚚 4.3. Kiểu `String` và Cơ Chế Dịch Chuyển (Move Semantics)

Chuỗi ký tự dạng chuỗi cứng `&str` được ghi trực tiếp vào mã máy nhị phân nên có kích thước cố định và bất biến. Để xử lý chuỗi có thể nhập từ bàn phím hoặc chỉnh sửa linh hoạt, Rust cung cấp kiểu `String` lưu trữ trên Heap.

```rust
let mut s = String::from("hello");
s.push_str(", world!"); // nối thêm chuỗi
println!("{s}"); // In ra: hello, world!
```

#### 🔬 Phân tích bố cục bộ nhớ của `String`:
Một biến `String` thực chất bao gồm 3 trường lưu trên **Stack** (chiếm 24 bytes trên kiến trúc 64-bit):
- **`ptr`**: Con trỏ trỏ đến vùng nhớ chứa nội dung chuỗi trên Heap.
- **`len`**: Độ dài nội dung hiện tại (tính bằng byte).
- **`capacity`**: Tổng dung lượng bộ nhớ đã xin cấp phát trên Heap.

```text
Stack (Biến s1)                    Heap
+----------+-------+               +-----+---+---+---+---+---+
| Tên      | Giá trị|              |Index| 0 | 1 | 2 | 3 | 4 |
+----------+-------+               +-----+---+---+---+---+---+
| ptr      |   *---+-------------> |Val  | h | e | l | l | o |
| len      |   5   |               +-----+---+---+---+---+---+
| capacity |   5   |
+----------+-------+
```

#### ⚖️ Sự khác biệt giữa Shallow Copy và Move Semantics:
Hãy xem đoạn mã sau:

```rust
let s1 = String::from("hello");
let s2 = s1; // ❓ ĐIỀU GÌ XẢY RA Ở ĐÂY?
```

Trong các ngôn ngữ khác (như C++ hoặc Python), phép gán này sao chép con trỏ trên Stack (Shallow Copy). Cả `s1` và `s2` đều cùng trỏ vào một vùng nhớ trên Heap. Khi cả hai biến đi ra khỏi scope, hệ thống sẽ cố gắng giải phóng cùng một vùng nhớ hai lần (**Double Free Error**) — một lỗ hổng bảo mật cực kỳ nghiêm trọng dẫn đến hỏng bộ nhớ!

**🛡️ Giải pháp của Rust:** Rust thực hiện sao chép con trỏ trên Stack nhưng **VÔ HIỆU HÓA HOÀN TOÀN** biến `s1`. Hành động này gọi là **Dịch chuyển quyền sở hữu (Move)**.

```rust
let s1 = String::from("hello");
let s2 = s1; // Quyền sở hữu chuyển sang s2. s1 bị vô hiệu hóa!

// println!("{s1}"); // ❌ LỖI BIÊN DỊCH: borrow of moved value: `s1`
println!("{s2}");    // ✅ Hợp lệ!
```

Trình biên dịch `rustc` bảo vệ bạn ngay từ lúc gõ code. Không có chi phí copy bộ nhớ Heap, và không có nguy cơ Double Free!

#### 🧬 Sao chép sâu với `.clone()`:
Nếu bạn thực sự muốn nhân bản dữ liệu trên Heap:

```rust
let s1 = String::from("hello");
let s2 = s1.clone(); // Cấp phát thêm một vùng nhớ mới trên Heap
println!("s1 = {s1}, s2 = {s2}"); // ✅ Cả hai đều hợp lệ
```

#### ⚡ Trait `Copy` dành cho dữ liệu trên Stack:
Các kiểu dữ liệu có kích thước cố định hoàn toàn nằm trên Stack (như `i32`, `f64`, `bool`, `char`, hoặc tuple chứa các kiểu này) được cài đặt trait `Copy`. Với các kiểu này, phép gán `let y = x;` sẽ tự động sao chép giá trị mà không làm mất hiệu lực của `x`.

---

### 🔄 4.4. Quyền Sở Hữu Trong Hàm

Khi truyền một biến vào hàm, hành vi cũng giống như phép gán:
- Nếu kiểu dữ liệu nằm trên Heap (như `String`), quyền sở hữu sẽ bị **Move** vào hàm. Sau khi hàm kết thúc, giá trị bị giải phóng, biến ban đầu không thể dùng lại được nữa!
- Nếu muốn giữ lại giá trị, hàm phải trả lại quyền sở hữu, hoặc chúng ta dùng cơ chế **Mượn (Borrowing)**.

```rust
fn main() {
    let s = String::from("hello");
    takes_ownership(s); // Quyền sở hữu của s chuyển vào hàm
    // println!("{s}"); // ❌ LỖI: s không còn hợp lệ!

    let x = 5;
    makes_copy(x);      // x được sao chép
    println!("{x}");    // ✅ Hợp lệ vì i32 có trait Copy
}

fn takes_ownership(some_string: String) {
    println!("{some_string}");
} // some_string ra khỏi scope, hàm drop được gọi, bộ nhớ được giải phóng!

fn makes_copy(some_integer: i32) {
    println!("{some_integer}");
}
```

---

### 🤝 4.5. Cơ Chế Mượn (Borrowing) và Tham Chiếu (References)

Thay vì chuyển giao quyền sở hữu, Rust cho phép ta tạo một **Tham chiếu (Reference)** trỏ đến giá trị mà không sở hữu nó. Hành động tạo tham chiếu gọi là **Mượn (Borrowing)**.

#### 1. 👁️ Tham chiếu bất biến (`&T`):
Cho phép đọc giá trị nhưng không được phép chỉnh sửa:

```rust
fn calculate_length(s: &String) -> usize {
    s.len()
} // s đi ra khỏi scope, nhưng vì nó chỉ mượn (không sở hữu), không có gì bị giải phóng!
```

#### 2. ✏️ Tham chiếu khả biến (`&mut T`):
Cho phép sửa đổi giá trị đang mượn:

```rust
fn main() {
    let mut s = String::from("hello");
    change(&mut s);
    println!("{s}"); // In ra: hello, world!
}

fn change(some_string: &mut String) {
    some_string.push_str(", world!");
}
```

#### 3. 📜 Quy Tắc Bất Biến Của Borrow Checker:
Đây là quy tắc cốt lõi giúp Rust loại trừ lỗi xung đột dữ liệu đa luồng (**Data Races**):
> **Tại một thời điểm bất kỳ trong cùng một phạm vi, bạn chỉ có thể có:**
> - **HOẶC là vô số tham chiếu bất biến (`&T`).**
> - **HOẶC là DUY NHẤT MỘT tham chiếu khả biến (`&mut T`).**

*🧪 Thử nghiệm vi phạm quy tắc:*
```rust
let mut s = String::from("hello");

let r1 = &s;     // ✅ Hợp lệ: mượn bất biến 1
let r2 = &s;     // ✅ Hợp lệ: mượn bất biến 2
// let r3 = &mut s; // ❌ LỖI BIÊN DỊCH: cannot borrow `s` as mutable because it is also borrowed as immutable

println!("{r1}, {r2}");
```

*💡 Non-Lexical Lifetimes (NLL):*
Trình biên dịch Rust thông minh xác định phạm vi của tham chiếu kết thúc tại vị trí cuối cùng nó được dùng:
```rust
let mut s = String::from("hello");

let r1 = &s;
let r2 = &s;
println!("{r1}, {r2}"); // Lần sử dụng cuối cùng của r1 và r2

// ✅ Từ dòng này trở đi, r1 và r2 không còn được dùng nữa,
// nên tạo tham chiếu khả biến ở đây hoàn toàn hợp lệ!
let r3 = &mut s;
r3.push_str("!");
println!("{r3}");
```

#### 4. 🚫 Ngăn chặn Con trỏ Lơ Lửng (Dangling References):
Trong C/C++, nếu bạn trả về một con trỏ trỏ đến một biến cục bộ trong hàm, con trỏ đó sẽ trỏ vào vùng nhớ rác khi hàm kết thúc. Trong Rust, Borrow Checker sẽ từ chối biên dịch ngay lập tức:

```rust
// fn dangle() -> &String {
//     let s = String::from("hello");
//     &s // ❌ LỖI BIÊN DỊCH: returns a reference to data owned by the current function
// }
```

---

### 🍰 4.6. Kiểu Lát Cắt (Slices)

Lát cắt (**Slice**) là một tham chiếu đến một chuỗi phần tử liên tiếp trong một tập hợp dữ liệu mà không chiếm quyền sở hữu của tập hợp đó.

#### ✂️ Lát cắt chuỗi (`&str`):
Lát cắt chuỗi lưu trữ con trỏ tới byte bắt đầu và số lượng byte (`len`):

```rust
let s = String::from("hello world");

let hello: &str = &s[0..5];  // Từ chỉ mục 0 đến 4
let world: &str = &s[6..11]; // Từ chỉ mục 6 đến 10

// Cú pháp rút gọn:
let slice1 = &s[..2];  // Tương đương &s[0..2]
let slice2 = &s[3..];  // Tương đương &s[3..len]
let slice3 = &s[..];   // Lấy toàn bộ chuỗi
```

*🏆 Quy ước thiết kế hàm tối ưu:*
Khi viết hàm nhận tham số chuỗi, hãy luôn dùng kiểu `&str` thay vì `&String`. Khi đó, hàm có thể nhận cả chuỗi cứng `&str` lẫn `String` (thông qua cơ chế tự động ép kiểu Deref Coercion):

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

---

## 🏗️ CHƯƠNG 5: GOM NHÓM DỮ LIỆU LIÊN QUAN VỚI STRUCTS

**Struct (Cấu trúc dữ liệu)** cho phép bạn nhóm nhiều giá trị liên quan có các kiểu dữ liệu khác nhau lại thành một kiểu dữ liệu tùy chỉnh có ý nghĩa nghiệp vụ rõ ràng.

### 📐 5.1. Khai Báo và Khởi Tạo Struct

```rust
struct User {
    active: bool,
    username: String,
    email: String,
    sign_in_count: u64,
}

fn main() {
    let mut user1 = User {
        active: true,
        username: String::from("rustacean123"),
        email: String::from("user@example.com"),
        sign_in_count: 1,
    };

    // Truy xuất và sửa đổi trường dữ liệu:
    user1.email = String::from("new_email@example.com");
}
```

#### ⚡ Cú pháp viết tắt khởi tạo trường (Field Init Shorthand):
Khi tên tham số trùng với tên trường của struct:

```rust
fn build_user(email: String, username: String) -> User {
    User {
        active: true,
        username, // Tương đương: username: username
        email,    // Tương đương: email: email
        sign_in_count: 1,
    }
}
```

#### 🔄 Cú pháp cập nhật struct (Struct Update Syntax):
Tạo một instance mới kế thừa các trường từ instance cũ bằng cú pháp `..`:

```rust
let user2 = User {
    email: String::from("another@example.com"),
    ..user1 // Các trường còn lại lấy từ user1 (chú ý: username bị move!)
};
```

#### 📦 Các dạng Struct đặc biệt:
1. **Tuple Structs:** Struct không có tên trường, chỉ có kiểu dữ liệu. Thường dùng để tạo các kiểu mới (*Newtype Pattern*):
   ```rust
   struct Color(i32, i32, i32);
   struct Point(i32, i32, i32);
   let black = Color(0, 0, 0);
   let origin = Point(0, 0, 0);
   ```
2. **Unit-Like Structs:** Struct không có bất kỳ trường nào (`struct AlwaysEqual;`). Thường dùng khi cần triển khai một Trait trên một kiểu mà không cần lưu trữ dữ liệu.

---

### 📏 5.2. Ví Dụ Thực Hành: Chương Trình Đo Đạc Hình Chữ Nhật

Hãy xem sự tiến hóa từ mã nguồn vụng về đến mã nguồn chuẩn mực trong Rust:

```rust
#[derive(Debug)] // Cho phép in struct bằng {:?} hoặc {:#?}
struct Rectangle {
    width: u32,
    height: u32,
}

// Khối triển khai phương thức và hàm liên kết cho Rectangle
impl Rectangle {
    // Phương thức (Method): Tham số đầu tiên luôn là &self (mượn bất biến)
    fn area(&self) -> u32 {
        self.width * self.height
    }

    // Phương thức kiểm tra có chứa vừa hình chữ nhật khác không
    fn can_hold(&self, other: &Rectangle) -> bool {
        self.width > other.width && self.height > other.height
    }

    // Hàm liên kết (Associated Function) - không nhận self làm tham số
    // Đóng vai trò là Constructor (hàm khởi tạo)
    fn square(size: u32) -> Self {
        Self {
            width: size,
            height: size,
        }
    }
}

fn main() {
    let rect1 = Rectangle { width: 30, height: 50 };
    let rect2 = Rectangle { width: 10, height: 40 };
    let sq = Rectangle::square(25); // Gọi hàm liên kết bằng toán tử ::

    println!("📐 Diện tích rect1: {}", rect1.area());
    println!("🔍 rect1 có chứa được rect2 không? {}", rect1.can_hold(&rect2));
    
    // In gỡ lỗi struct:
    println!("📦 Hình vuông tạo mới: {:#?}", sq);
    
    // Macro dbg! in thông tin ra stderr kèm số dòng và trả về quyền sở hữu:
    dbg!(&rect1);
}
```

---

## 🎯 CHƯƠNG 6: KIỂU LIỆT KÊ ENUMS & KHỚP MẪU PATTERN MATCHING

Structs giúp bạn gom nhóm các trường cùng tồn tại đồng thời, trong khi **Enum (Enumeration)** cho phép bạn định nghĩa một kiểu dữ liệu có thể là **MỘT TRONG NHIỀU** biến thể khả dĩ.

### 🏷️ 6.1. Định Nghĩa Enum Mang Dữ Liệu

Trong Rust, Enum mạnh mẽ hơn rất nhiều so với C/C++ hay Java: mỗi biến thể của Enum có thể chứa dữ liệu với các kiểu khác nhau!

```rust
enum Message {
    Quit,                       // Không chứa dữ liệu
    Move { x: i32, y: i32 },    // Chứa một struct ẩn danh
    Write(String),              // Chứa một String
    ChangeColor(i32, i32, i32), // Chứa ba số nguyên
}

impl Message {
    fn call(&self) {
        // Có thể định nghĩa phương thức trên Enum giống hệt Struct!
    }
}
```

---

### 🛡️ 6.2. Enum Chuẩn `Option<T>` — Vũ Khí Loại Bỏ Lỗi Null

Rust không có giá trị `null`. Nhà khoa học máy tính Tony Hoare (người phát minh ra null vào năm 1965) đã gọi null là *"Sai lầm tỷ đô"* vì nó là nguyên nhân của vô số lỗi crash và hổng bảo mật.

Để biểu diễn khái niệm một giá trị "có thể có hoặc không có", thư viện chuẩn Rust cung cấp enum `Option<T>`:

```rust
enum Option<T> {
    None,    // Biểu thị không có giá trị
    Some(T), // Biểu thị có giá trị kiểu T
}
```

`Option<T>` được nạp sẵn vào mọi chương trình (prelude). Bạn có thể dùng trực tiếp `Some(5)` hoặc `None` mà không cần tiền tố `Option::`.
*💡 Sức mạnh của `Option<T>`:* Bạn không thể cộng trực tiếp một số `i8` với một `Option<i8>`. Trình biên dịch bắt buộc bạn phải kiểm tra và xử lý trường hợp `None` trước khi có thể lấy được dữ liệu bên trong `Some`!

---

### 🔀 6.3. Cấu Trúc Điều Khiển Khớp Mẫu `match`

`match` cho phép so sánh một giá trị với một loạt các mẫu (patterns) và thực thi mã tương ứng.

```rust
#[derive(Debug)]
enum UsState {
    Alabama,
    Alaska,
}

enum Coin {
    Penny,
    Nickel,
    Dime,
    Quarter(UsState), // Biến thể chứa dữ liệu
}

fn value_in_cents(coin: Coin) -> u8 {
    match coin {
        Coin::Penny => {
            println!("🪙 Đồng xu may mắn!");
            1
        }
        Coin::Nickel => 5,
        Coin::Dime => 10,
        Coin::Quarter(state) => {
            println!("🪙 Đồng 25 xu phát hành từ bang: {state:?}!");
            25
        }
    }
}
```

#### 🔄 Xử lý `Option<T>` bằng `match`:
```rust
fn plus_one(x: Option<i32>) -> Option<i32> {
    match x {
        None => None,
        Some(i) => Some(i + 1),
    }
}
```

#### ✅ Tính Vét Cạn (Exhaustiveness) và Ký hiệu Giữ Chỗ `_`:
Trong Rust, các nhánh của `match` bắt buộc phải bao quát hết 100% mọi khả năng có thể xảy ra. Nếu bỏ sót dù chỉ 1 trường hợp, chương trình sẽ không thể biên dịch!
Khi bạn không muốn liệt kê tất cả các giá trị:

```rust
let dice_roll = 9;
match dice_roll {
    3 => add_fancy_hat(),
    7 => remove_fancy_hat(),
    _ => (), // _ đại diện cho mọi trường hợp còn lại; () là không làm gì cả
}
```

---

### ⚡ 6.4. Luồng Điều Khiển Rút Gọn: `if let` và `let else`

#### 🔹 Cú pháp `if let`:
Khi bạn chỉ quan tâm đến DUY NHẤT một mẫu và muốn bỏ qua tất cả các trường hợp còn lại:

```rust
let config_max = Some(3u8);

// Thay vì viết match cồng kềnh:
if let Some(max) = config_max {
    println!("Giá trị tối đa được cấu hình là: {max}");
}
```

#### 🔸 Cú pháp `let else` (Chuẩn hiện đại):
Dùng để gán giá trị nếu khớp mẫu, ngược lại thì thoát khỏi hàm hoặc vòng lặp ngay lập tức (*early return*), giúp code không bị lồng nhiều tầng ngoặc nhọn:

```rust
fn process_number(opt: Option<i32>) {
    let Some(number) = opt else {
        println!("⚠️ Không có giá trị, thoát hàm!");
        return;
    };

    // 'number' ở đây là kiểu i32 bình thường, sẵn sàng sử dụng!
    println!("✅ Số nhận được là: {number}");
}
```

---

# 🗂️ PHẦN III: TỔ CHỨC DỰ ÁN, CẤU TRÚC DỮ LIỆU & XỬ LÝ LỖI

---

## 🌳 CHƯƠNG 7: QUẢN LÝ DỰ ÁN VỚI PACKAGES, CRATES VÀ MODULES

Khi chương trình mở rộng, việc gom toàn bộ mã nguồn vào một file duy nhất sẽ dẫn đến thảm họa bảo trì. Rust cung cấp một hệ thống phân cấp tổ chức mã nguồn tinh vi, bao gồm: **Packages**, **Crates**, **Modules**, và **Paths**.

### 🏛️ 7.1. Cấu Trúc Phân Cấp: Packages và Crates

- 🧱 **Crate:** Là đơn vị biên dịch nhỏ nhất trong Rust. Một Crate có thể sinh ra một file thực thi nhị phân (*Binary Crate*) hoặc một thư viện mã dùng chung (*Library Crate*).
  - *Binary Crate:* Phải chứa hàm `main`. Điểm khởi đầu mặc định là file `src/main.rs`.
  - *Library Crate:* Không có hàm `main`, định nghĩa các chức năng chia sẻ cho các dự án khác. Điểm khởi đầu mặc định là file `src/lib.rs`.
- 📦 **Package:** Được định nghĩa bởi một file `Cargo.toml`. Một Package:
  - Có thể chứa **tối đa một** Library Crate (`src/lib.rs`).
  - Có thể chứa **vô số** Binary Crate (`src/main.rs`, hoặc các file đặt trong thư mục `src/bin/*.rs`).

---

### 🔐 7.2. Định Nghĩa Cây Module (Module Tree)

Module giúp bạn nhóm các hàm, struct, enum liên quan và kiểm soát tính riêng tư (*Privacy Boundary*).

```rust
// File: src/lib.rs

// Khai báo module nhà hàng
mod front_of_house {
    // Module con quản lý việc tiếp khách
    pub mod hosting {
        pub fn add_to_waitlist() {}
        fn seat_at_table() {} // 🔒 Không có 'pub' -> Mặc định là private!
    }

    mod serving {
        fn take_order() {}
        fn serve_order() {}
        fn take_payment() {}
    }
}
```

#### 🔑 Quy Tắc Riêng Tư (Privacy Rules):
1. 🔒 **Mặc định là Riêng tư (Private):** Mọi thực thể (hàm, phương thức, struct, enum, module) mặc định đều là private đối với module cha của nó.
2. 👁️ **Quyền truy cập:** Các module con luôn có quyền nhìn thấy và sử dụng các mục của module cha của nó. Ngược lại, module cha không thể nhìn thấy các mục private của module con trừ khi được gắn từ khóa `pub`.
3. ⚖️ **Struct vs Enum:**
   - Với Struct: Gắn `pub struct` chỉ làm tên struct công khai. Mỗi trường bên trong vẫn là private trừ khi được gắn `pub` riêng lẻ (ví dụ: `pub name: String`).
   - Với Enum: Gắn `pub enum` sẽ tự động công khai **toàn bộ các biến thể** bên trong!

---

### 🧭 7.3. Đường Dẫn (Paths) và Từ Khóa `use`

Để gọi một hàm từ module khác, bạn có hai cách chỉ định đường dẫn:
- **Đường dẫn tuyệt đối (Absolute Path):** Bắt đầu từ gốc crate bằng từ khóa `crate` (ví dụ: `crate::front_of_house::hosting::add_to_waitlist()`).
- **Đường dẫn tương đối (Relative Path):** Bắt đầu từ phạm vi hiện tại bằng `self`, `super` (truy cập module cha, tương đương `..` trong đường dẫn thư mục), hoặc tên định danh trực tiếp.

#### 🔗 Đưa đường dẫn vào phạm vi với `use`:
Để tránh phải gõ lại đường dẫn dài dòng:

```rust
use crate::front_of_house::hosting;

pub fn eat_at_restaurant() {
    hosting::add_to_waitlist(); // Ngắn gọn và rõ ràng!
}
```

*💡 Quy ước chuẩn (Idiomatic Use Paths):*
- Với hàm: Nên đưa module cha vào scope (`use ...::hosting;`) rồi gọi `hosting::add_to_waitlist()`. Điều này làm rõ ràng rằng hàm không được định nghĩa tại file hiện tại.
- Với Struct, Enum: Nên đưa trực tiếp kiểu vào scope (`use std::collections::HashMap;`).

#### 📤 Tái xuất khẩu (Re-exporting) bằng `pub use`:
Khi bạn viết thư viện, cấu trúc module nội bộ có thể phân chia sâu, nhưng bạn muốn người dùng thư viện có thể truy cập các hàm cốt lõi một cách tiện lợi nhất:

```rust
pub use crate::front_of_house::hosting;
// Người bên ngoài có thể gọi: your_crate::hosting::add_to_waitlist()
```

---

### 📂 7.4. Tổ Chức Mã Nguồn Thành Nhiều File Chuẩn Hiện Đại

Khi module `front_of_house` lớn lên, ta tách nó ra thành file riêng:

1. Trong `src/lib.rs`: Chỉ cần khai báo `mod front_of_house;` (Cargo sẽ tự tìm file cùng tên).
2. Tạo file `src/front_of_house.rs`: Chứa nội dung module `front_of_house`.
3. Nếu `front_of_house` có module con `hosting`: Tạo thư mục `src/front_of_house/` và đặt file `src/front_of_house/hosting.rs` vào đó.

```text
src/
├── lib.rs
├── front_of_house.rs
└── front_of_house/
    └── hosting.rs
```

---

## 🧰 CHƯƠNG 8: CÁC CẤU TRÚC DỮ LIỆU TẬP HỢP PHỔ BIẾN (COLLECTIONS)

Khác với mảng và tuple có kích thước cố định nằm trên Stack, các tập hợp dữ liệu trong chương này lưu trữ dữ liệu trên **Heap**, cho phép co giãn kích thước linh hoạt lúc chạy.

### 📈 8.1. Vector: `Vec<T>` — Danh Sách Động

Vector lưu trữ nhiều giá trị có cùng một kiểu dữ liệu liên tiếp nhau trong bộ nhớ.

```rust
// Khởi tạo vector rỗng (cần chú thích kiểu hoặc push để suy luận):
let mut v: Vec<i32> = Vec::new();

// Khởi tạo nhanh bằng macro vec!:
let v2 = vec![1, 2, 3];

// Thêm phần tử:
v.push(5);
v.push(6);
v.push(7);
```

#### 🔍 Đọc phần tử và Xử lý Giới hạn Biên:
Có hai cách truy xuất phần tử của vector:

```rust
let v = vec![1, 2, 3, 4, 5];

// Cách 1: Chỉ mục trực tiếp (gây panic nếu chỉ mục vượt biên!)
let third: &i32 = &v[2];
println!("Phần tử thứ ba là: {third}");

// Cách 2: Phương thức .get() trả về Option<&T> (an toàn tuyệt đối)
match v.get(2) {
    Some(third) => println!("Phần tử thứ ba là: {third}"),
    None => println!("Không tồn tại phần tử ở chỉ mục này!"),
}
```

#### 🛡️ Quy Tắc Borrow Checker Với Vector:
Đoạn mã sau sẽ bị trình biên dịch từ chối:

```rust
let mut v = vec![1, 2, 3, 4, 5];
let first = &v[0]; // Mượn bất biến phần tử đầu tiên

// v.push(6); // ❌ LỖI BIÊN DỊCH: cannot borrow `v` as mutable because it is also borrowed as immutable

println!("Phần tử đầu: {first}");
```
*❓ Tại sao?* Vì khi bạn `push(6)`, nếu dung lượng vector không đủ, Rust sẽ phải cấp phát một vùng nhớ mới lớn hơn ở vị trí khác trên Heap, sao chép toàn bộ dữ liệu sang đó và giải phóng vùng nhớ cũ. Khi đó, tham chiếu `first` sẽ trở thành **con trỏ lơ lửng** trỏ vào vùng nhớ đã bị giải phóng! Borrow Checker ngăn chặn lỗi này ngay lúc biên dịch.

#### 📦 Lưu trữ nhiều kiểu dữ liệu trong Vector qua Enum:
```rust
enum SpreadsheetCell {
    Int(i32),
    Float(f64),
    Text(String),
}

let row = vec![
    SpreadsheetCell::Int(3),
    SpreadsheetCell::Text(String::from("blue")),
    SpreadsheetCell::Float(10.12),
];
```

---

### 🔤 8.2. Chuỗi Ký Tự UTF-8: `String`

Trong Rust, `String` là một vector bọc quanh một chuỗi các byte hợp lệ theo chuẩn mã hóa **UTF-8**.

#### 🛠️ Thao tác với chuỗi:
```rust
let mut s = String::from("foo");
s.push_str("bar"); // Nối chuỗi &str
s.push('!');       // Thêm một ký tự đơn char

// Ghép chuỗi tiện lợi bằng macro format!:
let s1 = String::from("tic");
let s2 = String::from("tac");
let s3 = String::from("toe");
let s = format!("{s1}-{s2}-{s3}"); // s = "tic-tac-toe" mà không chiếm quyền sở hữu của s1, s2, s3!
```

#### ❓ Tại Sao Rust Không Cho Phép Đánh Chỉ Mục Chuỗi Kiểu `s[0]`?
Trong nhiều ngôn ngữ, bạn có thể lấy ký tự đầu bằng `s[0]`. Trong Rust, điều này bị **CẤM HOÀN TOÀN**.
Lý do: UTF-8 mã hóa ký tự với độ dài biến thiên từ **1 đến 4 bytes**:
- Từ tiếng Anh `"hello"` có 5 chữ cái, chiếm đúng 5 bytes.
- Nhưng chữ tiếng Việt `"xin chào"` hay tiếng Nga `"Здравствуйте"` mỗi ký tự chiếm 2 hoặc nhiều bytes hơn.
Nếu Rust cho phép truy cập `s[0]`, nó sẽ trả về byte đầu tiên chứ không phải một ký tự hoàn chỉnh, dẫn đến ký tự bị vỡ và tạo lỗ hổng bảo mật.

#### 🔬 Ba Góc Nhìn Về Chuỗi Trong Rust:
Chuỗi tiếng Việt: `"Việt"`
1. **Bytes:** `[86, 105, 225, 187, 135, 116]` (6 bytes).
2. **Scalar Values (Ký tự Unicode `char`):** `['V', 'i', 'ệ', 't']` (4 ký tự).
3. **Grapheme Clusters (Chữ cái mắt người nhìn thấy):** `"V"`, `"i"`, `"ệ"`, `"t"`.

```rust
// Duyệt theo ký tự char:
for c in "Việt".chars() {
    println!("{c}");
}

// Duyệt theo byte thô:
for b in "Việt".bytes() {
    println!("{b}");
}
```

---

### 🗺️ 8.3. Bảng Băm: `HashMap<K, V>`

`HashMap` lưu trữ các cặp khóa - giá trị (*Key - Value*) với thời gian tìm kiếm trung bình là `O(1)` thông qua một hàm băm (*Hashing Function*).

```rust
use std::collections::HashMap;

let mut scores = HashMap::new();
scores.insert(String::from("Blue"), 10);
scores.insert(String::from("Yellow"), 50);

// Truy xuất giá trị bằng .get():
let team_name = String::from("Blue");
let score = scores.get(&team_name).copied().unwrap_or(0);
println!("Điểm của đội Blue: {score}");

// Duyệt qua toàn bộ bảng băm:
for (key, value) in &scores {
    println!("{key}: {value}");
}
```

#### ⚡ Cập nhật Giá trị Thông minh với Entry API:
```rust
let mut scores = HashMap::new();
scores.insert(String::from("Blue"), 10);

// Chỉ thêm nếu khóa chưa tồn tại:
scores.entry(String::from("Yellow")).or_insert(50);
scores.entry(String::from("Blue")).or_insert(50); // Không làm gì vì Blue đã có 10!

// Ứng dụng: Đếm số lần xuất hiện của từ trong đoạn văn:
let text = "hello world wonderful world";
let mut map = HashMap::new();

for word in text.split_whitespace() {
    // or_insert trả về một tham chiếu khả biến &mut V đến giá trị trong ô nhớ
    let count = map.entry(word).or_insert(0);
    *count += 1; // Giải tham chiếu (dereference) để cộng dồn
}
println!("{map:?}"); // {"world": 2, "hello": 1, "wonderful": 1}
```

---

## 🛡️ CHƯƠNG 9: CƠ CHẾ XỬ LÝ LỖI (ERROR HANDLING)

Rust không sử dụng cơ chế Ngoại lệ (*Exceptions*) như Java, C# hay Python. Triết lý của Rust là phân biệt rạch ròi hai loại lỗi:
1. 💥 **Lỗi không thể phục hồi (Unrecoverable Errors):** Thường do bug lập trình viên (truy xuất mảng ngoài biên, chia cho 0). Dùng macro `panic!`.
2. 🔄 **Lỗi có thể phục hồi (Recoverable Errors):** Lỗi ngoại cảnh dự đoán trước được (không tìm thấy file, mất kết nối mạng, sai định dạng). Dùng kiểu trả về `Result<T, E>`.

### 💥 9.1. Lỗi Không Thể Phục Hồi Với `panic!`

Khi macro `panic!` được kích hoạt, chương trình sẽ in thông báo lỗi, gỡ cuộn ngăn xếp (*unwinding stack*), dọn dẹp các tài nguyên bộ nhớ và dừng chương trình.

```rust
fn main() {
    // panic!("Hệ thống gặp sự cố nghiêm trọng!");
}
```

#### 🕵️ Bật Backtrace để truy vết vị trí lỗi:
Đặt biến môi trường khi chạy terminal:
```bash
RUST_BACKTRACE=1 cargo run
```
Trình biên dịch sẽ in toàn bộ ngăn xếp hàm đã gọi dẫn tới vị trí crash chính xác từng dòng file.

---

### 🔄 9.2. Lỗi Có Thể Phục Hồi Với `Result<T, E>`

Được định nghĩa trong thư viện chuẩn:

```rust
enum Result<T, E> {
    Ok(T),  // ✅ Thành công, chứa kết quả T
    Err(E), // ❌ Thất bại, chứa thông tin lỗi E
}
```

#### 🎯 Xử lý mở tập tin:
```rust
use std::fs::File;
use std::io::ErrorKind;

fn main() {
    let greeting_file_result = File::open("hello.txt");

    let greeting_file = match greeting_file_result {
        Ok(file) => file,
        Err(error) => match error.kind() {
            // Nếu lỗi do file chưa tồn tại -> tự động tạo mới!
            ErrorKind::NotFound => match File::create("hello.txt") {
                Ok(fc) => fc,
                Err(e) => panic!("Không thể tạo file: {e:?}"),
            },
            other_error => {
                panic!("Gặp sự cố khi mở file: {other_error:?}");
            }
        },
    };
}
```

#### 🛠️ Các phương thức tiện ích rút gọn:
- `.unwrap()`: Nếu là `Ok`, trả về giá trị bên trong. Nếu là `Err`, tự động gọi `panic!`.
- `.expect("Thông điệp")`: Tương tự `unwrap`, nhưng in ra thông điệp giải thích ngữ cảnh lỗi rõ ràng hơn nhiều.
```rust
let f = File::open("config.json").expect("Lỗi: Không tìm thấy file cấu hình config.json!");
```

---

### ❓ 9.3. Lan Truyền Lỗi (Propagating Errors) & Toán Tử `?`

Khi viết một hàm gặp lỗi, thay vì tự ý xử lý hoặc panic, cách tiếp cận chuẩn mực là trả lỗi về cho hàm gọi nó tự quyết định.

Rust cung cấp toán tử **`?`** giúp viết code xử lý lỗi ngắn gọn và thanh lịch:

```rust
use std::fs::File;
use std::io::{self, Read};

// Hàm đọc username từ file:
fn read_username_from_file() -> Result<String, io::Error> {
    let mut username = String::new();
    
    // Toán tử ? làm hai việc:
    // 1. Nếu là Ok(file), giải nén file và tiếp tục.
    // 2. Nếu là Err(e), RETURN NGAY LẬP TỨC khỏi hàm với giá trị Err(e)!
    File::open("username.txt")?.read_to_string(&mut username)?;

    Ok(username)
}
```

#### ⚙️ Bản chất của toán tử `?` và Trait `From`:
Toán tử `?` tự động gọi hàm `From::from` để chuyển đổi kiểu lỗi từ kiểu của thư viện con sang kiểu lỗi trả về của hàm cha, giúp bạn dễ dàng thống nhất kiểu lỗi trong toàn bộ ứng dụng.

---

### ⚖️ 9.4. Khi Nào Nên Dùng `panic!` vs `Result`?

| Tình huống | Lựa chọn khuyến nghị | Lý do |
| :--- | :--- | :--- |
| 🧪 Viết mã mẫu, prototype, test | `unwrap()`, `expect()`, `panic!` | Giúp code ngắn gọn, tập trung vào logic chính. |
| 📦 Thư viện dùng chung (Library code) | Luôn trả về `Result<T, E>` | Để người dùng thư viện tự quyết định cách xử lý lỗi. |
| 🚨 Vi phạm bất biến nghiêm trọng (Contract violation) | `panic!` | Trạng thái chương trình đã hỏng, tiếp tục chạy sẽ gây nguy hiểm. |
| 🛡️ Xác thực dữ liệu người dùng nhập | Tạo Custom Type + trả `Result` | Kiểm soát dữ liệu hợp lệ ngay tại biên tiếp nhận. |

---

# 🧬 PHẦN IV: TRỪU TƯỢNG HÓA, KIỂM THỬ & DỰ ÁN MINIGREP

---

## 🧩 CHƯƠNG 10: KIỂU CHUNG (GENERICS), TRAITS VÀ VÒNG ĐỜI (LIFETIMES)

Ba tính năng trong chương này tạo nên sức mạnh biểu đạt vượt trội của Rust: **Generics** giúp tái sử dụng mã nguồn cho nhiều kiểu dữ liệu; **Traits** định nghĩa các hành vi trừu tượng; và **Lifetimes** giúp trình biên dịch kiểm soát tính an toàn của các tham chiếu mà không cần Garbage Collector.

### 🧩 10.1. Kiểu Chung (Generics) — Trừu Tượng Hóa Không Chi Phí

Generics cho phép bạn viết các hàm, struct, enum hoạt động trên nhiều kiểu dữ liệu khác nhau mà không phải viết lặp lại mã.

#### 1. Generics trong Định nghĩa Hàm:
```rust
// Hàm tìm phần tử lớn nhất trong một lát cắt:
// T: PartialOrd yêu cầu kiểu T phải có khả năng so sánh lớn/nhỏ
fn largest<T: std::cmp::PartialOrd>(list: &[T]) -> &T {
    let mut largest = &list[0];

    for item in list {
        if item > largest {
            largest = item;
        }
    }
    largest
}
```

#### 2. Generics trong Struct và Enum:
```rust
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
```

#### 3. 🚀 Bản Chất Hiệu Năng: Cơ Chế Đơn Hình Hóa (Monomorphization):
Rust xử lý Generics bằng kỹ thuật **Monomorphization** tại thời điểm biên dịch. Trình biên dịch quét toàn bộ mã nguồn, tìm tất cả các kiểu dữ liệu cụ thể được dùng với Generic, và sinh ra mã máy riêng biệt cho từng kiểu đó.
*⚡ Hệ quả:* Sử dụng Generics trong Rust hoàn toàn **KHÔNG CÓ OVERHEAD tại runtime**. Mã chạy nhanh ngang bằng mã viết tay cho từng kiểu riêng biệt (*Zero-Cost Abstractions*)!

---

### 📜 10.2. Traits: Định Nghĩa Hành Vi Chung

**Trait** trong Rust tương tự như *Interface* trong Java/C#, cho phép định nghĩa một tập hợp các phương thức mà một kiểu dữ liệu phải cài đặt để thể hiện hành vi đó.

#### 📝 Khai báo và Cài đặt Trait:
```rust
pub trait Summary {
    // Phương thức bắt buộc phải cài đặt
    fn summarize_author(&self) -> String;

    // Cài đặt mặc định (Default Implementation)
    fn summarize(&self) -> String {
        format!("(Đọc thêm từ tác giả {}...)", self.summarize_author())
    }
}

pub struct NewsArticle {
    pub headline: String,
    pub location: String,
    pub author: String,
    pub content: String,
}

impl Summary for NewsArticle {
    fn summarize_author(&self) -> String {
        format!("@{}", self.author)
    }
}
```

#### ⛓️ Trait Bounds — Ràng Buộc Kiểu:
```rust
// Cú pháp rút gọn với impl Trait:
pub fn notify(item: &impl Summary) {
    println!("Tin mới: {}", item.summarize());
}

// Cú pháp Trait Bound đầy đủ:
pub fn notify_full<T: Summary>(item: &T) {
    println!("Tin mới: {}", item.summarize());
}

// Nhiều ràng buộc với dấu +:
pub fn notify_multi<T: Summary + std::fmt::Display>(item: &T) {}

// Mệnh đề where giúp làm sạch chữ ký hàm:
fn some_function<T, U>(t: &T, u: &U) -> i32
where
    T: std::fmt::Display + Clone,
    U: Clone + std::fmt::Debug,
{
    0
}
```

#### 🌟 Blanket Implementations:
Rust cho phép cài đặt một Trait cho bất kỳ kiểu nào thỏa mãn một Trait khác. Ví dụ trong thư viện chuẩn:
```rust
impl<T: std::fmt::Display> ToString for T {
    // Tự động có phương thức .to_string() cho bất kỳ ai cài đặt Display!
}
```

---

### ⏳ 10.3. Kiểm Soát Vòng Đời Tham Chiếu Với Lifetimes (`'a`)

Mọi tham chiếu trong Rust đều có một **Vòng đời (Lifetime)** — là khoảng thời gian mà tham chiếu đó hợp lệ. Hầu hết thời gian, trình biên dịch tự động suy luận lifetime. Tuy nhiên, khi một hàm nhận nhiều tham chiếu và trả về một tham chiếu, Rust bắt buộc bạn phải chú thích lifetime rõ ràng.

#### 🛡️ Mục đích: Triệt tiêu hoàn toàn Lỗi Con trỏ Lơ lửng (Dangling Pointer):
Hãy xem hàm tìm chuỗi có độ dài lớn hơn:

```rust
// ❌ LỖI NẾU KHÔNG CÓ CHÚ THÍCH LIFETIME:
// fn longest(x: &str, y: &str) -> &str { ... }

// ✅ HỢP LỆ VỚI CHÚ THÍCH LIFETIME 'a:
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() {
        x
    } else {
        y
    }
}
```

#### 💡 Ý nghĩa thực sự của cú pháp `'a`:
- Ký hiệu `'a` **KHÔNG** làm thay đổi thời gian sống thực tế của bất kỳ biến nào.
- Nó chỉ ra cho Borrow Checker biết một giao ước: **Giá trị trả về sẽ tồn tại chừng nào mà CẢ HAI tham chiếu `x` và `y` đều còn hợp lệ** (nói cách khác, lifetime của kết quả bằng giao điểm thời gian sống của `x` và `y`).

#### 🏗️ Lifetimes trong Khai báo Struct:
Nếu một struct chứa một trường là tham chiếu, struct đó bắt buộc phải có chú thích lifetime:
```rust
struct ImportantExcerpt<'a> {
    part: &'a str, // Struct này không thể sống lâu hơn tham chiếu mà nó trỏ tới!
}
```

#### 📏 Ba Quy Tắc Suy Đoán Vòng Đời Tự Động (Lifetime Elision Rules):
Trình biên dịch tự động suy luận lifetime theo 3 bước:
1. **Quy tắc 1:** Mỗi tham số là tham chiếu sẽ được gán một lifetime riêng biệt (`fn foo<'a, 'b>(x: &'a i32, y: &'b i32)`).
2. **Quy tắc 2:** Nếu chỉ có DUY NHẤT một tham chiếu đầu vào, lifetime đó sẽ được tự động gán cho toàn bộ tham chiếu đầu ra (`fn foo<'a>(x: &'a i32) -> &'a i32`).
3. **Quy tắc 3:** Nếu là phương thức của struct (có tham số `&self` hoặc `&mut self`), lifetime của `self` sẽ được tự động gán cho toàn bộ tham chiếu đầu ra.

#### ♾️ Vòng đời tĩnh `'static`:
Tham chiếu mang lifetime `'static` có thể sống suốt toàn bộ thời gian chạy của chương trình. Mọi chuỗi ký tự cứng (*String Literals*) đều có lifetime `'static`:
```rust
let s: &'static str = "Tôi tồn tại vĩnh viễn trong file thực thi nhị phân!";
```

---

## 🧪 CHƯƠNG 11: VIẾT KIỂM THỬ TỰ ĐỘNG (AUTOMATED TESTING)

Rust tích hợp sẵn hệ thống kiểm thử tự động mạnh mẽ mà không cần cài thêm bất kỳ framework bên ngoài nào.

### 🔬 11.1. Giải Phẫu Một Hàm Kiểm Thử

```rust
// src/lib.rs

pub fn add(a: i32, b: i32) -> i32 {
    a + b
}

// Module kiểm thử đơn vị, chỉ được biên dịch khi chạy cargo test
#[cfg(test)]
mod tests {
    use super::*; // Kéo toàn bộ hàm của module cha vào phạm vi test

    #[test]
    fn it_works() {
        let result = add(2, 2);
        assert_eq!(result, 4); // So sánh bằng
    }

    #[test]
    fn test_custom_message() {
        let result = add(3, 3);
        assert_ne!(result, 5, "Lỗi: 3 + 3 không thể bằng 5!");
    }

    #[test]
    #[should_panic(expected = "chia cho 0")]
    fn test_panic() {
        panic!("Phép tính chia cho 0 không hợp lệ!");
    }
}
```

---

### 💻 11.2. Điều Khiển Kiểm Thử Với `cargo test`

```bash
# Chạy toàn bộ các bài kiểm thử
cargo test

# Chạy các test tuần tự trên 1 luồng duy nhất (khi các test dùng chung tài nguyên):
cargo test -- --test-threads=1

# Hiển thị các lệnh println! ngay cả khi test PASS:
cargo test -- --show-output

# Chạy đích danh một bài test theo tên:
cargo test it_works

# Đánh dấu bỏ qua test tốn thời gian: #[ignore]
# Chạy riêng các test đã bị ignore:
cargo test -- --ignored
```

---

### ⚖️ 11.3. Cấu Trúc: Unit Tests vs Integration Tests

- 🧩 **Unit Tests (Kiểm thử đơn vị):** Đặt ngay trong `src/` cùng với mã nguồn, trong khối `#[cfg(test)]`. Đặc quyền: Có thể gọi và kiểm tra trực tiếp cả các hàm `private` nội bộ!
- 🔗 **Integration Tests (Kiểm thử tích hợp):** Đặt trong thư mục riêng `tests/` ở thư mục gốc của dự án. Cargo sẽ coi mỗi file trong `tests/*.rs` như một crate độc lập từ bên ngoài, chỉ có thể gọi các API `pub` của thư viện.

```text
my_project/
├── Cargo.toml
├── src/
│   └── lib.rs               # Chứa unit tests ở cuối file
└── tests/
    └── integration_test.rs  # Chứa integration tests
```

---

## 🔍 CHƯƠNG 12: DỰ ÁN 2 — XÂY DỰNG CÔNG CỤ DÒNG LỆNH MINIGREP

Trong chương này, chúng ta sẽ xây dựng một phiên bản rút gọn của công cụ tìm kiếm văn bản kinh điển `grep` (*globally search a regular expression and print*). Dự án này kết hợp toàn bộ kiến thức về: Xử lý I/O, Structs, Traits, Xử lý lỗi với `Result`, Tách module chuẩn kiến trúc và Phát triển hướng kiểm thử (TDD).

### 📁 12.1. Cấu Trúc Dự Án Tách Biệt

```text
minigrep/
├── Cargo.toml
├── poem.txt            # File văn bản mẫu để tìm kiếm
└── src/
    ├── main.rs         # Chỉ tiếp nhận input và xử lý lỗi khởi chạy
    └── lib.rs          # Chứa toàn bộ logic nghiệp vụ và kiểm thử
```

📄 Tạo file văn bản `poem.txt`:
```text
I'm nobody! Who are you?
Are you nobody, too?
Then there's a pair of us - don't tell!
They'd banish us, you know.

How dreary to be somebody!
How public, like a frog
To tell your name the livelong day
To an admiring bog!
```

---

### 📚 12.2. Mã Nguồn Module Thư Viện (`src/lib.rs`)

```rust
use std::error::Error;
use std::fs;
use std::env;

// Struct chứa cấu hình tìm kiếm
pub struct Config {
    pub query: String,
    pub file_path: String,
    pub ignore_case: bool,
}

impl Config {
    // Hàm khởi tạo cấu hình từ tham số dòng lệnh
    pub fn build(args: &[String]) -> Result<Config, &'static str> {
        if args.len() < 3 {
            return Err("Thiếu tham số! Cú pháp: minigrep <từ_khóa> <đường_dẫn_file>");
        }

        let query = args[1].clone();
        let file_path = args[2].clone();

        // Kiểm tra biến môi trường IGNORE_CASE (nếu có đặt -> không phân biệt hoa thường)
        let ignore_case = env::var("IGNORE_CASE").is_ok();

        Ok(Config {
            query,
            file_path,
            ignore_case,
        })
    }
}

// Hàm thực thi logic chính của chương trình
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

// Thuật toán tìm kiếm phân biệt chữ hoa/thường
pub fn search<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let mut results = Vec::new();
    for line in contents.lines() {
        if line.contains(query) {
            results.push(line);
        }
    }
    results
}

// Thuật toán tìm kiếm không phân biệt chữ hoa/thường
pub fn search_case_insensitive<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    let query_lower = query.to_lowercase();
    let mut results = Vec::new();
    for line in contents.lines() {
        if line.to_lowercase().contains(&query_lower) {
            results.push(line);
        }
    }
    results
}

// Bộ kiểm thử tự động TDD
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

### 🚀 12.3. Mã Nguồn File Điểm Khởi Đầu (`src/main.rs`)

File `main.rs` được thiết kế cực kỳ tinh gọn, đóng vai trò là lớp điều phối:

```rust
use std::env;
use std::process;
use minigrep::Config;

fn main() {
    // Thu thập tham số dòng lệnh thành vector
    let args: Vec<String> = env::args().collect();

    // Khởi tạo cấu hình, nếu có lỗi thì in ra stderr và thoát với mã lỗi 1
    let config = Config::build(&args).unwrap_or_else(|err| {
        eprintln!("⚠️ Sự cố khi phân tích tham số: {err}");
        process::exit(1);
    });

    // Thực thi chương trình, bắt lỗi runtime nếu xảy ra
    if let Err(e) = minigrep::run(config) {
        eprintln!("❌ Lỗi ứng dụng: {e}");
        process::exit(1);
    }
}
```

#### 💻 Chạy thử nghiệm công cụ `minigrep`:
```bash
# 1. Chạy tìm kiếm thông thường (phân biệt hoa thường):
cargo run -- to poem.txt
# Output:
# Are you nobody, too?
# How dreary to be somebody!

# 2. Chạy tìm kiếm không phân biệt hoa thường bằng biến môi trường:
IGNORE_CASE=1 cargo run -- to poem.txt
# Output:
# Are you nobody, too?
# How dreary to be somebody!
# To tell your name the livelong day
# To an admiring bog!

# 3. Chạy khi thiếu tham số để kiểm tra luồng báo lỗi qua eprintln!:
cargo run
# Output ra stderr:
# ⚠️ Sự cố khi phân tích tham số: Thiếu tham số! Cú pháp: minigrep <từ_khóa> <đường_dẫn_file>
```

---

# ⚡ PHẦN V: LẬP TRÌNH HÀM, QUẢN LÝ BỘ NHỚ & ĐỒNG THỜI

---

## 🔄 CHƯƠNG 13: LẬP TRÌNH HÀM: CLOSURES VÀ ITERATORS

Thiết kế của Rust chịu ảnh hưởng sâu sắc từ phong cách lập trình hàm (*Functional Programming*). Hai tính năng cốt lõi là **Closures** (hàm ẩn danh có thể bắt biến từ môi trường) và **Iterators** (chuỗi xử lý dữ liệu lười biếng). Cả hai đều tuân thủ nguyên lý *Zero-Cost Abstraction*.

### 🎣 13.1. Closures: Hàm Ẩn Danh Bắt Ngữ Cảnh

Closure là một hàm không có tên, có thể được lưu trữ trong biến, truyền làm tham số cho hàm khác, và có khả năng **bắt giữ (capture) các giá trị từ phạm vi mà nó được định nghĩa**.

#### 📝 Cú pháp Closure:
```rust
// Khai báo hàm bình thường:
fn  add_one_v1   (x: u32) -> u32 { x + 1 }

// Các cách viết Closure tương đương:
let add_one_v2 = |x: u32| -> u32 { x + 1 };
let add_one_v3 = |x|             { x + 1 }; // Trình biên dịch tự suy luận kiểu
let add_one_v4 = |x|               x + 1  ; // Thân hàm 1 dòng có thể bỏ ngoặc nhọn
```

#### 🎭 Ba Cách Bắt Biến Từ Môi Trường và Các Trait `Fn`:
Một closure bắt các biến từ môi trường xung quanh theo 3 cách, tương ứng với 3 Trait trong thư viện chuẩn:

1. 🥇 **`FnOnce`:** Chiếm quyền sở hữu (*Takes ownership*) của các biến bị bắt. Vì quyền sở hữu chỉ có thể chuyển giao một lần, closure này chỉ có thể được gọi DUY NHẤT một lần.
2. 🥈 **`FnMut`:** Mượn tham chiếu khả biến (*Mutably borrows*) các biến. Closure có thể thay đổi trạng thái của môi trường xung quanh và có thể gọi nhiều lần.
3. 🥉 **`Fn`:** Mượn tham chiếu bất biến (*Immutably borrows*) các biến. Closure chỉ đọc dữ liệu và có thể được gọi đồng thời nhiều lần.

#### 🚚 Từ khóa `move`:
Nếu bạn muốn bắt buộc closure phải chiếm quyền sở hữu toàn bộ các giá trị mà nó sử dụng từ môi trường (thường dùng khi chuyển closure sang một Thread mới chạy ngầm), hãy thêm từ khóa `move`:

```rust
let list = vec![1, 2, 3];
println!("Trước khi định nghĩa closure: {list:?}");

// Từ khóa 'move' buộc list phải chuyển hẳn quyền sở hữu vào trong closure
let only_borrows = move || println!("Từ closure: {list:?}");

only_borrows();
// println!("{list:?}"); // ❌ LỖI BIÊN DỊCH: borrow of moved value: `list`
```

---

### 🔁 13.2. Iterators: Bộ Lặp Tinh Tế và Tối Ưu

Trong Rust, **Iterator** là một đối tượng cho phép bạn duyệt qua một chuỗi các phần tử. Đặc điểm quan trọng nhất: **Iterators là lười biếng (Lazy)** — việc tạo iterator không tốn chi phí tính toán cho đến khi bạn thực sự gọi các phương thức tiêu thụ nó!

#### ⚙️ Trait `Iterator` Trong Thư Viện Chuẩn:
Mọi iterator đều phải cài đặt Trait sau:
```rust
pub trait Iterator {
    type Item; // Kiểu của phần tử trả về (Associated Type)
    fn next(&mut self) -> Option<Self::Item>;
}
```

#### 🛠️ Ba Phương Thức Tạo Iterator:
- `v.iter()`: Duyệt qua các phần tử dưới dạng tham chiếu bất biến `&T`.
- `v.iter_mut()`: Duyệt qua các phần tử dưới dạng tham chiếu khả biến `&mut T`.
- `v.into_iter()`: Chiếm quyền sở hữu và duyệt qua các giá trị `T` (vector ban đầu bị tiêu thụ).

#### 🔄 Các Phương Thức Chuyển Đổi (Iterator Adapters):
Các phương thức này không thực thi ngay mà trả về một iterator mới:
- `map(|x| ...)`: Biến đổi từng phần tử.
- `filter(|x| ...)`: Lọc các phần tử thỏa mãn điều kiện.
- `zip(...)`: Ghép đôi hai iterator thành các tuple.

#### 📥 Các Phương Thức Tiêu Thụ (Consuming Adapters):
Các phương thức này kích hoạt iterator chạy và thu thập kết quả:
- `.sum()`: Tính tổng các phần tử.
- `.collect()`: Gom toàn bộ phần tử của iterator vào một tập hợp mới (như `Vec<T>`, `HashMap`).

```rust
let v1: Vec<i32> = vec![1, 2, 3];

// Chuỗi xử lý phong cách hàm (Functional Pipeline):
let v2: Vec<i32> = v1.iter()
    .map(|x| x + 1)      // Tăng mỗi phần tử lên 1
    .filter(|x| *x > 2)  // Chỉ giữ lại số lớn hơn 2
    .collect();          // Thu thập kết quả vào vector mới: [3, 4]
```

---

### ✨ 13.3. Tái Cấu Trúc Dự Án `minigrep` Bằng Iterators

So sánh hàm `search` nguyên bản (dùng vòng lặp for thủ công) và phiên bản tái cấu trúc bằng Iterator:

```rust
// 🏆 PHIÊN BẢN GỌN GÀNG VÀ CHUẨN IDIOMATIC RUST:
pub fn search<'a>(query: &str, contents: &'a str) -> Vec<&'a str> {
    contents
        .lines()
        .filter(|line| line.contains(query))
        .collect()
}
```

#### ⚡ Tối ưu hóa hàm `Config::build`:
Thay vì mượn một slice và gọi `.clone()` tốn kém, ta truyền trực tiếp iterator `std::env::Args` và tiêu thụ từng tham số bằng `.next()`:

```rust
impl Config {
    pub fn build(mut args: impl Iterator<Item = String>) -> Result<Config, &'static str> {
        args.next(); // Bỏ qua phần tử đầu tiên (tên chương trình)

        let query = match args.next() {
            Some(arg) => arg,
            None => return Err("Thiếu tham số tìm kiếm!"),
        };

        let file_path = match args.next() {
            Some(arg) => arg,
            None => return Err("Thiếu đường dẫn file!"),
        };

        let ignore_case = std::env::var("IGNORE_CASE").is_ok();

        Ok(Config { query, file_path, ignore_case })
    }
}
```

Khi đó, trong `src/main.rs`, ta xóa bỏ bước `.collect()` tạo vector trung gian và truyền trực tiếp `env::args()` vào `Config::build`:

```rust
fn main() {
    // Truyền trực tiếp quyền sở hữu bộ lặp env::args() vào Config::build:
    let config = Config::build(env::args()).unwrap_or_else(|err| {
        eprintln!("⚠️ Sự cố khi phân tích tham số: {err}");
        process::exit(1);
    });

    if let Err(e) = minigrep::run(config) {
        eprintln!("❌ Lỗi ứng dụng: {e}");
        process::exit(1);
    }
}
```

---

## 🚢 CHƯƠNG 14: THÊM VỀ CARGO VÀ CRATES.IO

Cargo không chỉ quản lý build đơn giản mà còn hỗ trợ cấu hình tối ưu hóa chuyên sâu, kiểm thử tài liệu tự động và phát hành thư viện lên kho mã nguồn mở quốc tế.

### ⚙️ 14.1. Tùy Biến Bản Build Với Release Profiles

Trong `Cargo.toml`, bạn có thể can thiệp sâu vào các tham số tối ưu hóa của trình biên dịch:

```toml
[profile.dev]
opt-level = 0     # Biên dịch nhanh nhất, không tối ưu (mặc định cho debug)

[profile.release]
opt-level = 3     # Tối ưu hóa tối đa tốc độ thực thi
lto = true        # Bật Link-Time Optimization (tối ưu hóa toàn diện giữa các crate)
codegen-units = 1 # Giảm song song hóa lúc sinh mã để tối ưu hóa biên dịch sâu hơn
panic = "abort"   # Dừng ngay khi panic thay vì unwinding, giúp giảm kích thước file nhị phân
strip = true      # Loại bỏ toàn bộ debug symbols, giảm kích thước file thực thi đáng kể
```

---

### 📝 14.2. Viết Tài Liệu Chuẩn & Documentation Tests (Doctests)

Rust hỗ trợ viết tài liệu trực tiếp trong mã nguồn bằng cú pháp chú thích `///` (hỗ trợ Markdown hoàn chỉnh):

````rust
/// Cộng thêm một vào số nguyên được truyền vào.
///
/// # Ví dụ
///
/// ```
/// use my_crate::add_one;
///
/// let arg = 5;
/// let answer = add_one(arg);
///
/// assert_eq!(6, answer);
/// ```
pub fn add_one(x: i32) -> i32 {
    x + 1
}
````

#### 🧪 Tính Năng Thần Kỳ: Documentation Tests:
Khi bạn chạy lệnh:
```bash
cargo test
```
Cargo sẽ tự động tìm kiếm toàn bộ các đoạn mã nằm trong các khối ```` ``` ```` của tài liệu `///` và **biên dịch, chạy chúng như một bài kiểm thử thực sự**!
*💡 Lợi ích vô giá:* Tài liệu hướng dẫn của bạn sẽ không bao giờ bị lỗi thời hoặc sai lệch cú pháp so với mã nguồn thực tế.

---

### 🏢 14.3. Quản Lý Đa Dự Án Với Cargo Workspaces

Khi xây dựng một hệ thống lớn gồm nhiều dịch vụ hoặc thư viện con, bạn sử dụng **Cargo Workspace** để dùng chung một thư mục biên dịch `target/` và một tập tin `Cargo.lock`.

Cấu trúc file `Cargo.toml` ở thư mục gốc:
```toml
[workspace]
members = [
    "adder",      # Binary crate
    "add_one",    # Library crate
]
```

---

## 🧠 CHƯƠNG 15: CON TRỎ THÔNG MINH (SMART POINTERS)

Trong khi con trỏ thông thường (tham chiếu `&`) chỉ mượn dữ liệu, **Con trỏ thông minh (Smart Pointer)** là các cấu trúc dữ liệu sở hữu vùng nhớ mà nó trỏ tới, đồng thời cung cấp thêm các chức năng quản lý tài nguyên và siêu dữ liệu (metadata).

Con trỏ thông minh trong Rust dựa trên hai Trait nền tảng:
- 🎯 **`Deref`:** Cho phép instance của con trỏ thông minh hành xử giống như một tham chiếu thông thường để có thể áp dụng các toán tử giải tham chiếu `*`.
- 🗑️ **`Drop`:** Tùy biến mã dọn dẹp khi giá trị đi ra khỏi phạm vi (*RAII pattern*).

---

### 📦 15.1. `Box<T>`: Cấp Phát Dữ Liệu Trên Heap

`Box<T>` là con trỏ thông minh đơn giản nhất, cho phép lưu trữ dữ liệu trên **Heap** trong khi con trỏ trỏ tới nó được lưu trên **Stack**.

```rust
fn main() {
    let b = Box::new(5); // Cấp phát số nguyên 5 trên Heap
    println!("b = {b}");
} // Khi b ra khỏi scope, bộ nhớ Heap của nó tự động được giải phóng
```

#### 🔄 Trường Hợp Điển Hình: Kiểu Dữ Liệu Đệ Quy (Recursive Types):
Tại thời điểm biên dịch, Rust cần biết chính xác kích thước của mọi kiểu dữ liệu. Với các kiểu đệ quy (như danh sách liên kết *Cons List*), kích thước về mặt lý thuyết là vô hạn, nên trình biên dịch sẽ báo lỗi.

```rust
// ❌ LỖI: recursive type `List` has infinite size
// enum List {
//     Cons(i32, List),
//     Nil,
// }

// ✅ GIẢI PHÁP: Sử dụng Box<T> vì Box luôn có kích thước cố định (kích thước của 1 con trỏ)
#[derive(Debug)]
enum List {
    Cons(i32, Box<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let list = Cons(1, Box::new(Cons(2, Box::new(Cons(3, Box::new(Nil))))));
    println!("{list:?}");
}
```

---

### 🎯 15.2. Trait `Deref` và Ép Kiểu Ngầm (Deref Coercion)

Cài đặt Trait `Deref` cho phép bạn tùy biến hành vi của toán tử giải tham chiếu `*`:

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
```

#### ✨ Cơ Chế Deref Coercion Thần Kỳ:
Khi bạn truyền một tham chiếu của kiểu dữ liệu cài đặt `Deref` vào một hàm đòi hỏi một kiểu khác, Rust sẽ tự động gọi chuỗi phương thức `.deref()` liên tiếp cho đến khi khớp với kiểu mong muốn mà không gây bất kỳ chi phí hiệu năng runtime nào:
```rust
fn hello(name: &str) {
    println!("Xin chào, {name}!");
}

let m = MyBox::new(String::from("Rust"));
// &m là kiểu &MyBox<String> -> tự động ép thành &String -> tự động ép thành &str:
hello(&m);
```

---

### 🗑️ 15.3. Trait `Drop` và Dọn Dẹp Tài Nguyên Tự Động

Trait `Drop` cho phép bạn can thiệp vào khoảnh khắc một giá trị chuẩn bị đi ra khỏi phạm vi hoạt động:

```rust
struct CustomSmartPointer {
    data: String,
}

impl Drop for CustomSmartPointer {
    fn drop(&mut self) {
        println!("🗑️ Đang dọn dẹp vùng nhớ của CustomSmartPointer chứa dữ liệu `{}`!", self.data);
    }
}

fn main() {
    let c = CustomSmartPointer { data: String::from("dữ liệu của tôi") };
    
    // Nếu muốn giải phóng sớm trước khi hết hàm:
    // c.drop(); // ❌ LỖI: explicit destructor calls not allowed!
    drop(c);     // ✅ Dùng hàm std::mem::drop hợp lệ
    
    println!("CustomSmartPointer đã bị giải phóng trước dòng này.");
}
```

---

### 🤝 15.4. `Rc<T>`: Con Trỏ Đếm Tham Chiếu (Reference Counting)

Trong hầu hết các trường hợp, một giá trị chỉ có một chủ sở hữu duy nhất. Tuy nhiên, trong các cấu trúc dữ liệu đồ thị (*Graphs*) hoặc cây phân cấp, một nút con có thể có **nhiều cha cùng trỏ vào**, đồng nghĩa với việc nó có nhiều chủ sở hữu cùng lúc.

`Rc<T>` duy trì một biến đếm số lượng tham chiếu đang cùng sở hữu vùng nhớ:
- Gọi `Rc::clone(&a)` sẽ **tăng biến đếm thêm 1** mà không sao chép dữ liệu sâu trên Heap.
- Khi một biến sở hữu ra khỏi scope, biến đếm giảm đi 1.
- Khi biến đếm giảm về đúng 0, vùng nhớ trên Heap mới chính thức bị giải phóng.

```rust
use std::rc::Rc;

enum List {
    Cons(i32, Rc<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let a = Rc::new(Cons(5, Rc::new(Cons(10, Rc::new(Nil)))));
    println!("Số tham chiếu sau khi tạo a = {}", Rc::strong_count(&a));

    let b = Cons(3, Rc::clone(&a)); // b cùng sở hữu a
    println!("Số tham chiếu sau khi tạo b = {}", Rc::strong_count(&a));

    {
        let c = Cons(4, Rc::clone(&a)); // c cùng sở hữu a
        println!("Số tham chiếu sau khi tạo c = {}", Rc::strong_count(&a));
    } // c ra khỏi scope, biến đếm giảm đi 1

    println!("Số tham chiếu sau khi c bị hủy = {}", Rc::strong_count(&a));
}
```
*⚠️ LƯU Ý CỐT TỬ:* `Rc<T>` **CHỈ HOẠT ĐỘNG TRÊN MÔI TRƯỜNG ĐƠN LUỒNG (Single-Threaded)**. Nếu muốn dùng trên đa luồng, bạn bắt buộc phải dùng `Arc<T>`!

---

### 🔓 15.5. `RefCell<T>` và Mô Hình Tính Khả Biến Bên Trong (Interior Mutability)

**Interior Mutability (Tính khả biến bên trong)** là một mẫu thiết kế cho phép bạn chỉnh sửa dữ liệu ngay cả khi bạn đang giữ một tham chiếu bất biến đến dữ liệu đó.

#### ⚖️ So sánh `Box<T>`, `Rc<T>` và `RefCell<T>`:
| Tính năng | `Box<T>` | `Rc<T>` | `RefCell<T>` |
| :--- | :--- | :--- | :--- |
| **Số chủ sở hữu** | 1 chủ sở hữu | Nhiều chủ sở hữu | 1 chủ sở hữu |
| **Kiểu mượn** | Bất biến hoặc khả biến | Chỉ đọc bất biến | Bất biến hoặc khả biến |
| **Thời điểm kiểm tra quy tắc mượn** | **Lúc biên dịch (Compile-time)** | **Lúc biên dịch (Compile-time)** | **Lúc chạy (Runtime)** |

Với `RefCell<T>`, nếu bạn vi phạm quy tắc mượn (ví dụ mượn hai tham chiếu khả biến cùng lúc), chương trình sẽ **panic tại runtime** thay vì báo lỗi lúc biên dịch!

#### 🔗 Kết hợp quyền lực `Rc<RefCell<T>>`:
Cho phép vừa có nhiều chủ sở hữu, vừa có thể chỉnh sửa dữ liệu bên trong:

```rust
use std::cell::RefCell;
use std::rc::Rc;

#[derive(Debug)]
enum List {
    Cons(Rc<RefCell<i32>>, Rc<List>),
    Nil,
}

use List::{Cons, Nil};

fn main() {
    let value = Rc::new(RefCell::new(5));

    let a = Rc::new(Cons(Rc::clone(&value), Rc::new(Nil)));
    let b = Cons(Rc::new(RefCell::new(3)), Rc::clone(&a));
    let c = Cons(Rc::new(RefCell::new(4)), Rc::clone(&a));

    // Sửa đổi giá trị bên trong thông qua borrow_mut():
    *value.borrow_mut() += 10;

    println!("a sau khi sửa: {a:?}");
    println!("b sau khi sửa: {b:?}");
    println!("c sau khi sửa: {c:?}");
}
```

---

### 🛡️ 15.6. Vòng Lặp Tham Chiếu Làm Rò Rỉ Bộ Nhớ & Giải Pháp Với `Weak<T>`

Nếu hai `Rc<RefCell<T>>` trỏ chéo vào nhau, biến đếm số tham chiếu của chúng sẽ không bao giờ giảm về 0, dẫn tới hiện tượng **Rò rỉ bộ nhớ (Memory Leak)** ngay cả trong Safe Rust.

**✅ Giải pháp:** Chuyển một trong hai chiều tham chiếu thành **Tham chiếu yếu (`Weak<T>`)** bằng cách gọi `Rc::downgrade(&a)`:
- `Weak<T>` chỉ tăng biến đếm `weak_count`, **không ngăn cản** việc giải phóng giá trị khi `strong_count` về 0.
- Khi cần truy cập dữ liệu từ `Weak<T>`, gọi phương thức `.upgrade()` để nhận về một `Option<Rc<T>>` (nếu giá trị đã bị giải phóng thì trả về `None`).

---

# 🏆 PHẦN VI: NÂNG CAO, DỰ ÁN WEB SERVER & CẨM NANG

---

## 🧵 CHƯƠNG 16: LẬP TRÌNH ĐỒNG THỜI KHÔNG SỢ HÃI (FEARLESS CONCURRENCY)

Xử lý đồng thời an toàn và hiệu quả là một trong những mục tiêu thiết kế ban đầu quan trọng nhất của Rust. Thông thường trong C/C++ hay Java, lập trình đa luồng cực kỳ nguy hiểm vì rất dễ phát sinh lỗi **Xung đột dữ liệu (Data Races)** — xảy ra khi hai luồng cùng truy cập một ô nhớ, ít nhất một luồng có quyền ghi và không có cơ chế đồng bộ hóa.

Trong Rust, hệ thống kiểu dữ liệu và hệ thống kiểm tra quyền sở hữu (*Ownership & Borrowing*) đảm bảo rằng: **Nếu mã nguồn đa luồng của bạn biên dịch thành công, nó được đảm bảo không chứa Data Race!**

---

### ⚡ 16.1. Tạo Luồng Riêng Biệt Với `thread::spawn`

Rust sử dụng mô hình luồng 1:1, nghĩa là một luồng trong Rust tương ứng trực tiếp với một luồng của hệ điều hành (*OS Thread*).

```rust
use std::thread;
use std::time::Duration;

fn main() {
    // Khởi tạo một luồng mới
    let handle = thread::spawn(|| {
        for i in 1..5 {
            println!("🔹 Hi từ luồng con: {i}");
            thread::sleep(Duration::from_millis(1));
        }
    });

    for i in 1..3 {
        println!("🔸 Hi từ luồng chính: {i}");
        thread::sleep(Duration::from_millis(1));
    }

    // handle.join() chặn luồng chính cho đến khi luồng con kết thúc hoàn toàn
    handle.join().unwrap();
}
```

#### 🚚 Sử Dụng Closure `move` Với Luồng:
Để sử dụng dữ liệu từ luồng chính trong luồng con, bạn phải thêm từ khóa `move` để chuyển giao quyền sở hữu. Trình biên dịch sẽ ngăn chặn triệt để tình huống luồng con truy cập một biến đã bị luồng chính giải phóng!

```rust
use std::thread;

let v = vec![1, 2, 3];

// 'move' chuyển quyền sở hữu của v sang luồng mới:
let handle = thread::spawn(move || {
    println!("Vector trong luồng con: {v:?}");
});

handle.join().unwrap();
```

---

### 📨 16.2. Truyền Thông Điệp Qua Kênh (Message Passing Channels)

Triết lý nổi tiếng của cộng đồng lập trình hệ thống hiện đại là:
> 💬 *"Đừng giao tiếp bằng cách chia sẻ bộ nhớ; hãy chia sẻ bộ nhớ bằng cách giao tiếp."*

Rust cung cấp kênh truyền dữ liệu **`mpsc`** (*Multiple Producer, Single Consumer* — Nhiều người gửi, Một người nhận):

```rust
use std::sync::mpsc;
use std::thread;
use std::time::Duration;

fn main() {
    // Tạo kênh truyền dữ liệu: tx (Transmitter - Bên gửi), rx (Receiver - Bên nhận)
    let (tx, rx) = mpsc::channel();

    // Nhân bản bộ phát tx để có nhiều luồng cùng gửi thông điệp:
    let tx1 = tx.clone();
    thread::spawn(move || {
        let vals = vec![
            String::from("xin"),
            String::from("chào"),
            String::from("từ"),
            String::from("luồng 1"),
        ];

        for val in vals {
            tx1.send(val).unwrap(); // send() chuyển giao quyền sở hữu của val qua kênh!
            thread::sleep(Duration::from_millis(200));
        }
    });

    thread::spawn(move || {
        let vals = vec![
            String::from("thêm"),
            String::from("tin"),
            String::from("từ"),
            String::from("luồng 2"),
        ];

        for val in vals {
            tx.send(val).unwrap();
            thread::sleep(Duration::from_millis(200));
        }
    });

    // Bên nhận rx có thể duyệt như một iterator, tự động dừng khi mọi tx đều bị hủy:
    for received in rx {
        println!("📩 Đã nhận thông điệp: {received}");
    }
}
```
*🛡️ Tính An Toàn Tuyệt Đối:* Khi bạn gọi `tx.send(val)`, quyền sở hữu của biến `val` lập tức bị chuyển qua kênh. Nếu bạn cố gắng đọc hay sửa `val` ở các dòng tiếp theo trên luồng gửi, trình biên dịch sẽ chặn đứng với lỗi `use of moved value`!

---

### 🔒 16.3. Chia Sẻ Trạng Thái Đồng Thời: `Arc<Mutex<T>>`

Khi bắt buộc nhiều luồng phải cùng truy cập và sửa đổi một vùng nhớ chung, ta sử dụng cặp đôi quyền lực:
- 🔐 **`Mutex<T>` (Mutual Exclusion):** Cho phép khóa vùng nhớ để tại một thời điểm chỉ có DUY NHẤT một luồng được phép truy cập. Khi gọi `.lock()`, nó trả về một `MutexGuard` (tự động giải phóng khóa khi ra khỏi scope thông qua trait `Drop`).
- ⚛️ **`Arc<T>` (Atomic Reference Counting):** Tương tự `Rc<T>` nhưng sử dụng các phép toán nguyên tử cấp phần cứng (*atomic operations*), đảm bảo việc tăng giảm biến đếm an toàn tuyệt đối trên đa luồng.

```rust
use std::sync::{Arc, Mutex};
use std::thread;

fn main() {
    // Bọc biến đếm trong Mutex, sau đó bọc trong Arc để chia sẻ đa luồng:
    let counter = Arc::new(Mutex::new(0));
    let mut handles = vec![];

    // Khởi tạo 10 luồng cùng tăng giá trị biến đếm:
    for _ in 0..10 {
        let counter = Arc::clone(&counter);
        let handle = thread::spawn(move || {
            // lock() chặn luồng đến khi chiếm được khóa
            let mut num = counter.lock().unwrap();
            *num += 1;
        }); // Khi num ra khỏi scope, khóa Mutex tự động được mở!
        handles.push(handle);
    }

    for handle in handles {
        handle.join().unwrap();
    }

    println!("🎯 Kết quả biến đếm cuối cùng: {}", *counter.lock().unwrap()); // 10
}
```

---

### 🛡️ 16.4. Các Trait Mở Rộng: `Send` và `Sync`

Hệ sinh thái đồng thời của Rust không bị khóa cứng trong ngôn ngữ mà được trừu tượng hóa qua hai Trait đánh dấu (*Marker Traits*):
- 📤 **`Send`:** Đánh dấu rằng quyền sở hữu của kiểu dữ liệu này có thể được **chuyển giao an toàn giữa các luồng**. Hầu hết mọi kiểu trong Rust đều là `Send`, ngoại trừ các con trỏ như `Rc<T>` (vì `Rc` không đếm nguyên tử).
- 🔄 **`Sync`:** Đánh dấu rằng kiểu dữ liệu này an toàn khi được **nhiều luồng cùng truy cập đồng thời qua tham chiếu** (`&T`). Nói cách khác, kiểu `T` là `Sync` khi và chỉ khi `&T` là `Send`. `RefCell<T>` không phải là `Sync`, nhưng `Mutex<T>` là `Sync`.

---

## ⏳ CHƯƠNG 17: LẬP TRÌNH BẤT ĐỒNG BỘ (ASYNC / AWAIT)

Lập trình bất đồng bộ (*Asynchronous Programming*) cho phép một chương trình xử lý hàng chục nghìn kết nối mạng hoặc tác vụ I/O đồng thời trên một số lượng luồng hệ điều hành rất nhỏ, giúp tiết kiệm bộ nhớ và giảm thiểu chi phí chuyển đổi ngữ cảnh (*Context Switch*).

### ⚖️ 17.1. So Sánh: Threads (Đa Luồng) vs Async (Bất Đồng Bộ)

| Tiêu chí | Threads (Đa luồng OS) | Async Tasks (Tác vụ bất đồng bộ) |
| :--- | :--- | :--- |
| **Bản chất** | Luồng quản lý bởi Kernel hệ điều hành | Luồng ảo nhẹ (*Green Threads*) quản lý bởi Runtime |
| **Chi phí bộ nhớ** | Nặng (Mỗi thread tốn từ 1MB đến vài MB stack) | Rất nhẹ (Mỗi task chỉ tốn vài trăm bytes) |
| **Khả năng mở rộng** | Giới hạn (vài nghìn threads) | Cực lớn (hàng trăm nghìn tasks đồng thời) |
| **Phù hợp nhất với** | Tác vụ nặng tính toán CPU (*CPU-bound*) | Tác vụ chờ đợi mạng, đọc ghi đĩa (*I/O-bound*) |

---

### 🔮 17.2. Bản Chất: Trait `Future` và Cơ Chế Kéo (Poll-Based)

Không giống JavaScript hay C# (nơi các Promise tự động chạy ngay khi tạo ra), trong Rust, **Future là hoàn toàn lười biếng (Lazy)**: Một Future sẽ không thực thi bất kỳ dòng lệnh nào cho đến khi nó được thăm dò bằng phương thức `.poll()`.

```rust
pub trait Future {
    type Output;
    // Phương thức thăm dò trạng thái tiến độ:
    fn poll(self: Pin<&mut Self>, cx: &mut Context<'_>) -> Poll<Self::Output>;
}

pub enum Poll<T> {
    Ready(T), // ✅ Tác vụ đã hoàn thành, trả về kết quả T
    Pending,  // ⏳ Tác vụ đang chờ I/O, nhường CPU cho tác vụ khác
}
```

- 📌 **`Pin` và `Unpin`:** Cố định vị trí của Future trong bộ nhớ để đảm bảo an toàn cho các cấu trúc dữ liệu tự tham chiếu (*Self-Referential Structs*) khi bị tạm dừng.
- 🔔 **`Waker`:** Khi tác vụ I/O phần cứng sẵn sàng dữ liệu, `Waker` sẽ đánh thức tác vụ và yêu cầu Executor thăm dò lại.

---

### 🚀 17.3. Cú Pháp `async fn` và `.await` Với Tokio Runtime

Rust không tích hợp sẵn bộ thực thi async (*Executor/Runtime*) trong thư viện chuẩn để giữ ngôn ngữ tinh gọn. Cộng đồng sử dụng runtime tiêu chuẩn công nghiệp là **`tokio`**.

Khai báo trong `Cargo.toml`:
```toml
[dependencies]
tokio = { version = "1", features = ["full"] }
```

Mã nguồn thực thi bất đồng bộ:

```rust
// Macro biến hàm main thành async với tokio runtime
#[tokio::main]
async fn main() {
    println!("🚀 Bắt đầu tác vụ...");

    // Gọi đồng thời hai tác vụ bất đồng bộ:
    let task1 = fetch_data(1);
    let task2 = fetch_data(2);

    // tokio::join! chờ cả hai tác vụ hoàn thành song song:
    let (res1, res2) = tokio::join!(task1, task2);

    println!("✅ Kết quả: {res1} và {res2}");
}

async fn fetch_data(id: u32) -> String {
    // tokio::time::sleep không chặn luồng của hệ điều hành!
    tokio::time::sleep(tokio::time::Duration::from_millis(500)).await;
    format!("Dữ liệu từ nguồn #{id}")
}
```

---

## 🎭 CHƯƠNG 18: CÁC TÍNH NĂNG HƯỚNG ĐỐI TƯỢNG CỦA RUST (OOP)

### 🏛️ 18.1. Rust Định Nghĩa Lại Lập Trình Hướng Đối Tượng

- 📦 **Đối tượng chứa Dữ liệu và Hành vi:** Có. Structs và Enums chứa dữ liệu; các khối `impl` cung cấp hành vi và phương thức.
- 🔒 **Tính Đóng Gói (Encapsulation):** Có. Kiểm soát chặt chẽ qua ranh giới Module và từ khóa `pub`.
- 🧩 **Tính Kế Thừa (Inheritance):** **KHÔNG**. Rust không hỗ trợ kế thừa lớp (Class Inheritance) để tránh các căn bệnh kinh điển như phân cấp lớp phức tạp và bài toán đa kế thừa (*Diamond Problem*). Thay vào đó, Rust khuyến khích triết lý: **Ưu tiên Tổ hợp hơn Kế thừa (Composition over Inheritance)** và sử dụng **Traits** để chia sẻ hành vi.

---

### 🎨 18.2. Đa Hình Với Trait Objects (`dyn Trait`)

Khi bạn muốn một tập hợp chứa các đối tượng có **nhiều kiểu dữ liệu khác nhau** nhưng cùng cài đặt một Trait chung (ví dụ: một giao diện GUI chứa cả `Button`, `TextField`, `Slider`):

```rust
// Định nghĩa Trait vẽ giao diện
pub trait Draw {
    fn draw(&self);
}

// Struct Screen chứa một vector các Trait Objects: Box<dyn Draw>
pub struct Screen {
    pub components: Vec<Box<dyn Draw>>,
}

impl Screen {
    pub fn run(&self) {
        for component in &self.components {
            component.draw(); // Gọi hàm draw đa hình lúc chạy!
        }
    }
}

// Cài đặt cho Button:
pub struct Button {
    pub width: u32,
    pub height: u32,
    pub label: String,
}

impl Draw for Button {
    fn draw(&self) {
        println!("🔘 Vẽ Button: {}", self.label);
    }
}

// Cài đặt cho SelectBox:
pub struct SelectBox {
    pub width: u32,
    pub height: u32,
    pub options: Vec<String>,
}

impl Draw for SelectBox {
    fn draw(&self) {
        println!("📋 Vẽ SelectBox với {} tùy chọn", self.options.len());
    }
}

fn main() {
    let screen = Screen {
        components: vec![
            Box::new(SelectBox {
                width: 75,
                height: 50,
                options: vec![String::from("Có"), String::from("Không")],
            }),
            Box::new(Button {
                width: 50,
                height: 10,
                label: String::from("Xác nhận"),
            }),
        ],
    };

    screen.run();
}
```

#### 🔬 Bản Chất Bộ Nhớ: Dynamic Dispatch và Bảng Hàm Ảo (vtable):
`Box<dyn Draw>` là một **Con trỏ béo (Fat Pointer)** chiếm 16 bytes trên Stack, bao gồm:
1. Con trỏ trỏ tới dữ liệu thực tế của đối tượng trên Heap.
2. Con trỏ trỏ tới **vtable (Bảng hàm ảo)** chứa địa chỉ các con trỏ hàm tương ứng của Trait đó. Khi gọi `.draw()`, chương trình sẽ tra bảng vtable tại runtime.

---

### 🏆 18.3. Mẫu Thiết Kế Trạng Thái Chuẩn Rustacean: Typestate Pattern

Thay vì cài đặt State Pattern kiểu cũ với con trỏ động, các lập trình viên Rust chuyên nghiệp sử dụng **Typestate Pattern**: biến các trạng thái của đối tượng thành các kiểu Struct riêng biệt.

*💡 Lợi ích đột phá:* Trình biên dịch sẽ **ngăn chặn hoàn toàn các hành vi sai trạng thái ngay tại thời điểm biên dịch**! Ví dụ: Bạn không thể gọi phương thức `publish()` trên một bài viết chưa được duyệt (`Draft`), code sẽ từ chối biên dịch thay vì văng lỗi lúc chạy!

```rust
// Trạng thái Nháp (chưa có phương thức lấy nội dung):
pub struct DraftPost {
    content: String,
}

// Trạng thái Đã Xuất Bản (mới có phương thức đọc nội dung):
pub struct PublishedPost {
    content: String,
}

impl DraftPost {
    pub fn new(content: &str) -> DraftPost {
        DraftPost { content: String::from(content) }
    }

    // Chuyển trạng thái từ DraftPost sang PublishedPost (tiêu thụ self cũ):
    pub fn publish(self) -> PublishedPost {
        PublishedPost { content: self.content }
    }
}

impl PublishedPost {
    pub fn content(&self) -> &str {
        &self.content
    }
}

fn main() {
    let draft = DraftPost::new("Học Rust chuyên sâu");
    // draft.content(); // ❌ LỖI BIÊN DỊCH: Bài nháp không tồn tại hàm content()!

    let post = draft.publish();
    println!("📰 Bài viết đã xuất bản: {}", post.content()); // ✅ Hợp lệ!
}
```

---

## 🕸️ CHƯƠNG 19: KHỚP MẪU NÂNG CAO (PATTERNS AND MATCHING)

**Pattern (Mẫu)** là một cú pháp đặc biệt trong Rust dùng để so khớp với cấu trúc của các kiểu dữ liệu, cho phép phân rã (*destructuring*) dữ liệu phức tạp thành các biến đơn giản một cách an toàn và tường minh.

### 📍 19.1. Tất Cả Các Nơi Pattern Có Thể Xuất Hiện

1. 🎯 **Nhánh `match`:** Nơi phổ biến nhất, yêu cầu phải kiểm tra vét cạn 100% các khả năng.
2. ⚡ **Cú pháp `if let`:** Dùng khi chỉ kiểm tra 1 mẫu khả dĩ.
3. 🔄 **Vòng lặp `while let`:** Tiếp tục lặp chừng nào giá trị vẫn còn khớp với mẫu (ví dụ: rút dần phần tử từ một stack).
4. 🔁 **Vòng lặp `for`:** Phân rã tuple trong iterator: `for (index, value) in v.iter().enumerate()`.
5. 📌 **Câu lệnh `let`:** Mọi câu lệnh `let` thực chất đều là một pattern! Ví dụ: `let (x, y, z) = (1, 2, 3);`.
6. 📥 **Tham số hàm:** `fn print_coordinates(&(x, y): &(i32, i32)) { ... }`.

---

### ⚖️ 19.2. Phân Biệt: Refutable vs Irrefutable Patterns

- ✅ **Irrefutable (Không thể thất bại):** Là các mẫu luôn luôn khớp với mọi giá trị có thể có.
  *Ví dụ:* `let x = 5;`. Câu lệnh `let`, tham số hàm và vòng lặp `for` **chỉ chấp nhận** mẫu Irrefutable!
- ❓ **Refutable (Có thể thất bại):** Là các mẫu có thể không khớp với một số giá trị cụ thể.
  *Ví dụ:* Mẫu `Some(x)` có thể không khớp nếu giá trị là `None`. Cú pháp `if let` và `while let` sinh ra chuyên để xử lý các mẫu Refutable.

---

### 🧩 19.3. Cú Pháp Khớp Mẫu Chi Tiết

#### 1. Khớp nhiều giá trị và Dải giá trị:
```rust
let x = 3;
match x {
    1 | 2 => println!("Một hoặc hai"),
    3..=5 => println!("Từ ba đến năm"), // Dải số bao gồm cả 3 và 5
    _ => println!("Trường hợp khác"),
}
```

#### 2. Phân rã Structs, Enums và Tuples:
```rust
struct Point { x: i32, y: i32 }
let p = Point { x: 0, y: 7 };

match p {
    Point { x, y: 0 } => println!("Nằm trên trục hoành tại x = {x}"),
    Point { x: 0, y } => println!("Nằm trên trục tung tại y = {y}"),
    Point { x, y } => println!("Tọa độ: ({x}, {y})"),
}
```

#### 3. Bỏ qua giá trị với `_` và Cú pháp Rút gọn `..`:
```rust
let numbers = (2, 4, 8, 16, 32);

// Bỏ qua giá trị ở giữa bằng ..:
match numbers {
    (first, .., last) => {
        println!("Đầu: {first}, Cuối: {last}");
    }
}
```

#### 4. Điều kiện phụ Match Guards:
Thêm một điều kiện `if` vào sau mẫu để lọc giá trị:
```rust
let num = Some(4);

match num {
    Some(x) if x % 2 == 0 => println!("Số chẵn: {x}"),
    Some(x) => println!("Số lẻ: {x}"),
    None => (),
}
```

#### 5. Ràng buộc giá trị với toán tử `@` (*at bindings*):
Toán tử `@` cho phép bạn **vừa kiểm tra giá trị có nằm trong một dải hay không, vừa gán giá trị đó vào một biến mới** trong cùng một biểu thức:

```rust
enum Message {
    Hello { id: i32 },
}

let msg = Message::Hello { id: 5 };

match msg {
    Message::Hello {
        // Kiểm tra id trong khoảng [3, 7] và gán giá trị đó vào biến id_variable:
        id: id_variable @ 3..=7,
    } => println!("Tìm thấy id trong phạm vi hợp lệ: {id_variable}"),
    Message::Hello { id: 10..=12 } => {
        println!("Tìm thấy id trong phạm vi khác mà không cần lưu biến");
    }
    Message::Hello { id } => println!("Id bất kỳ khác: {id}"),
}
```

---

## 🧙‍♂️ CHƯƠNG 20: CÁC TÍNH NĂNG NÂNG CAO (ADVANCED FEATURES)

Chương này dành cho các kỹ sư hệ thống cần kiểm soát toàn diện kiến trúc phần cứng, viết FFI kết nối với C/C++, hoặc xây dựng các thư viện metaprogramming.

### ⚠️ 20.1. Unsafe Rust — 5 Siêu Năng Lực

Mặc định, mọi dòng code chúng ta học từ đầu đến giờ đều nằm trong **Safe Rust**. Safe Rust được đảm bảo an toàn bộ nhớ 100% bởi trình biên dịch. Tuy nhiên, phần cứng máy tính về bản chất vốn không an toàn! Khi bạn cần viết hệ điều hành, trình điều khiển thiết bị (drivers), hoặc tương tác bộ nhớ cấp thấp, bạn cần đến **Unsafe Rust**.

Để bước vào Unsafe Rust, ta sử dụng khối lệnh `unsafe { ... }`. Trong khối này, bạn có **5 siêu năng lực**:

1. 📌 **Giải tham chiếu con trỏ thô (Raw Pointers):**
   Con trỏ thô `*const T` (bất biến) và `*mut T` (khả biến) không có kiểm tra lifetime, có thể là null, và không tuân thủ quy tắc mượn. Việc tạo con trỏ thô là an toàn; chỉ có **giải tham chiếu (`*ptr`) mới là Unsafe**!
   ```rust
   let mut num = 5;
   let r1 = &num as *const i32;
   let r2 = &mut num as *mut i32;

   unsafe {
       println!("r1 trỏ tới: {}", *r1);
       *r2 = 10;
   }
   ```
2. ⚡ **Gọi hàm hoặc phương thức không an toàn (`unsafe fn`):** Các hàm này có những yêu cầu an toàn về bộ nhớ mà trình biên dịch không thể tự kiểm tra, đòi hỏi lập trình viên phải tự đảm bảo các điều kiện tiên quyết trước khi gọi.
3. 🛠️ **Triển khai một Trait không an toàn (`unsafe trait`):** Ví dụ như tự cài đặt `Send` hoặc `Sync` cho các kiểu tùy chỉnh.
4. 🌐 **Đọc hoặc chỉnh sửa biến tĩnh khả biến (`static mut`):** Do tiềm ẩn nguy cơ Data Race nếu nhiều luồng cùng truy cập.
5. 🗃️ **Truy cập các trường của một `union`:** Thường dùng để tương tác với các cấu trúc C union.

#### 🔌 Giao Tiếp Ngoại Ngữ (FFI — Foreign Function Interface):
Gọi một hàm từ thư viện C:
```rust
unsafe extern "C" {
    fn abs(input: i32) -> i32;
}

fn main() {
    unsafe {
        println!("Giá trị tuyệt đối của -3 theo C: {}", abs(-3));
    }
}
```

---

### 🧩 20.2. Traits Nâng Cao

#### 1. 🔗 Kiểu Liên Kết (Associated Types) vs Generics:
Kiểu liên kết kết nối một kiểu giữ chỗ (*placeholder type*) vào trong định nghĩa Trait:
```rust
pub trait Iterator {
    type Item; // Associated Type
    fn next(&mut self) -> Option<Self::Item>;
}
```
*❓ Tại sao không dùng Generics `trait Iterator<Item>`?* Bởi vì nếu dùng Generic, một kiểu có thể cài đặt `Iterator<String>`, `Iterator<i32>`, `Iterator<u8>` đồng thời, buộc lập trình viên phải chú thích kiểu mỗi khi gọi hàm. Với Associated Type, mỗi kiểu chỉ có thể cài đặt Trait đó **đúng một lần duy nhất**!

#### 2. ➕ Nạp Chồng Toán Tử (Operator Overloading) Với `std::ops`:
Rust không cho phép bạn tự sáng chế ra toán tử mới, nhưng cho phép bạn nạp chồng các toán tử có sẵn (như `+`, `-`, `*`) bằng cách cài đặt Trait tương ứng trong `std::ops`:

```rust
use std::ops::Add;

#[derive(Debug, Copy, Clone, PartialEq)]
struct Point { x: i32, y: i32 }

// Nạp chồng toán tử + cho struct Point:
impl Add for Point {
    type Output = Point;

    fn add(self, other: Point) -> Point {
        Point {
            x: self.x + other.x,
            y: self.y + other.y,
        }
    }
}
```

#### 3. 🎯 Cú Pháp Định Danh Đầy Đủ (Fully Qualified Syntax):
Khi hai Trait khác nhau cùng định nghĩa một phương thức có tên trùng nhau trên cùng một Struct:
```rust
// <Type as Trait>::function(receiver, args...);
```

#### 4. 📦 Newtype Pattern:
Quy tắc **Orphan Rule** của Rust quy định: Bạn chỉ có thể cài đặt một Trait cho một Kiểu nếu HOẶC Trait đó, HOẶC Kiểu đó được định nghĩa trong chính crate của bạn.
Để vượt qua quy tắc này (ví dụ: muốn cài đặt `Display` của thư viện chuẩn lên `Vec<String>` của thư viện chuẩn), ta dùng **Newtype Pattern** bọc kiểu ngoài trong một Tuple Struct cục bộ:
```rust
use std::fmt;

struct Wrapper(Vec<String>);

impl fmt::Display for Wrapper {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "[{}]", self.0.join(", "))
    }
}
```

---

### 🪄 20.3. Macros Trong Rust

Khác với hàm truyền thống (nhận giá trị lúc chạy), **Macro** là một công cụ lập trình siêu hình (*Metaprogramming*): nó nhận mã nguồn làm đầu vào và **sinh ra thêm mã nguồn** ngay tại thời điểm biên dịch, trước khi trình biên dịch kiểm tra kiểu!

#### 1. 📜 Macro Khai Báo (Declarative Macros với `macro_rules!`):
Hoạt động tương tự biểu thức so khớp `match` trên cây cú pháp:

```rust
#[macro_export]
macro_rules! my_vec {
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
```

#### 2. ⚙️ Macro Thủ Tục (Procedural Macros):
Hoạt động như một plugin của trình biên dịch, nhận vào một luồng token (`TokenStream`) và trả về một luồng token mới:
- **Custom Derive Macros:** Tự động sinh mã khi viết `#[derive(MyTrait)]`.
- **Attribute-like Macros:** Tạo các thuộc tính tùy chỉnh: `#[route(GET, "/users")]`.
- **Function-like Macros:** Phân tích cú pháp biểu thức tùy chỉnh lúc biên dịch.

---

## 🌐 CHƯƠNG 21: DỰ ÁN 3 — XÂY DỰNG MULTITHREADED WEB SERVER

Trong dự án tốt nghiệp này, chúng ta sẽ tự tay xây dựng một máy chủ web đa luồng (*Multithreaded Web Server*) từ con số 0 chỉ bằng thư viện chuẩn `std`, không dùng bất kỳ framework web nào!

Dự án này là sự kết hợp hoàn hảo của:
- 🔌 Lập trình mạng Socket TCP (`std::net`).
- 📄 Giao thức HTTP/1.1 (Request line, Headers, Body, HTTP Status Codes).
- 🧵 Quản lý đồng thời an toàn với kiến trúc **ThreadPool** tự xây dựng.
- 📨 Kênh truyền thông điệp nội bộ `mpsc::channel`.
- 🔒 Chia sẻ tài nguyên đa luồng với `Arc<Mutex<T>>`.
- 🛑 Đóng hệ thống an toàn (*Graceful Shutdown*) bằng Trait `Drop`.

---

### 📁 21.1. Cấu Trúc Dự Án Web Server

```text
web_server/
├── Cargo.toml
├── hello.html          # Trang HTML trả về khi thành công 200 OK
├── 404.html            # Trang HTML trả về khi không tìm thấy trang
└── src/
    ├── main.rs         # Lắng nghe kết nối TCP và điều phối tác vụ
    └── lib.rs          # Module ThreadPool quản lý các Worker threads
```

📄 Nội dung file `hello.html`:
```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="utf-8">
    <title>Xin chào từ Rust Web Server!</title>
  </head>
  <body>
    <h1>🦀 Thành Công!</h1>
    <p>Yêu cầu HTTP của bạn đã được xử lý bởi Rust Multithreaded Web Server.</p>
  </body>
</html>
```

📄 Nội dung file `404.html`:
```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="utf-8">
    <title>404 Không Tìm Thấy</title>
  </head>
  <body>
    <h1>❌ Lỗi 404!</h1>
    <p>Trang web bạn yêu cầu không tồn tại trên hệ thống.</p>
  </body>
</html>
```

---

### ⚙️ 21.2. Module `ThreadPool` Đa Luồng Chuẩn Mực (`src/lib.rs`)

```rust
use std::sync::{mpsc, Arc, Mutex};
use std::thread;

// Kiểu đóng gói một công việc cần thực thi:
// Là một closure nhận quyền sở hữu (FnOnce), an toàn chuyển qua thread (Send),
// và có lifetime tồn tại đủ lâu ('static)
type Job = Box<dyn FnOnce() + Send + 'static>;

pub struct ThreadPool {
    workers: Vec<Worker>,
    sender: Option<mpsc::Sender<Job>>,
}

impl ThreadPool {
    /// Khởi tạo một ThreadPool mới với số lượng luồng xác định.
    ///
    /// # Panics
    /// Hàm sẽ panic nếu `size` nhỏ hơn hoặc bằng 0.
    pub fn new(size: usize) -> ThreadPool {
        assert!(size > 0, "Số lượng luồng trong ThreadPool phải lớn hơn 0!");

        let (sender, receiver) = mpsc::channel();

        // Bọc đầu thu receiver trong Arc và Mutex để các Worker có thể chia sẻ an toàn:
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

    /// Tiếp nhận một công việc mới và đẩy vào hàng đợi cho các worker xử lý
    pub fn execute<F>(&self, f: F)
    where
        F: FnOnce() + Send + 'static,
    {
        let job = Box::new(f);
        // Gửi công việc qua kênh cho worker nào đang rảnh tiếp nhận:
        self.sender.as_ref().unwrap().send(job).unwrap();
    }
}

// Cài đặt Graceful Shutdown qua Trait Drop:
impl Drop for ThreadPool {
    fn drop(&mut self) {
        // Hủy sender trước để ngắt kết nối kênh, làm các worker thoát khỏi vòng lặp nhận tin:
        drop(self.sender.take());

        println!("🛑 Đang đóng toàn bộ các worker threads an toàn...");

        for worker in &mut self.workers {
            println!("⏳ Đang chờ worker #{} hoàn thành công việc...", worker.id);

            // Thu hồi luồng bằng join():
            if let Some(thread) = worker.thread.take() {
                thread.join().unwrap();
            }
        }

        println!("✅ Toàn bộ Web Server đã được đóng an toàn (Graceful Shutdown)!");
    }
}

// Cấu trúc đại diện cho một luồng Worker làm việc ngầm
struct Worker {
    id: usize,
    thread: Option<thread::JoinHandle<()>>,
}

impl Worker {
    fn new(id: usize, receiver: Arc<Mutex<mpsc::Receiver<Job>>>) -> Worker {
        let thread = thread::spawn(move || loop {
            // lock() để lấy quyền truy cập kênh:
            let message = receiver.lock().unwrap().recv();

            match message {
                Ok(job) => {
                    println!("👷 Worker #{id} tiếp nhận công việc; đang xử lý...");
                    job(); // Thực thi công việc!
                }
                Err(_) => {
                    // Kênh đã bị đóng (do sender bị drop lúc server shutdown)
                    println!("👋 Worker #{id} nhận tín hiệu ngắt kênh; đang dừng luồng.");
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

---

### 🚀 21.3. Mã Nguồn Lắng Nghe Mạng (`src/main.rs`)

```rust
use std::fs;
use std::io::{prelude::*, BufReader};
use std::net::{TcpListener, TcpStream};
use std::thread;
use std::time::Duration;
use web_server::ThreadPool;

fn main() {
    // Lắng nghe kết nối TCP trên cổng 7878 cục bộ:
    let listener = TcpListener::bind("127.0.0.1:7878").unwrap();
    
    // Khởi tạo ThreadPool với 4 luồng xử lý song song:
    let pool = ThreadPool::new(4);

    println!("=======================================================");
    println!(" 🌐 Web Server đang chạy tại cổng: 7878                ");
    println!(" 🛑 Nhấn ngắt tiến trình để kiểm tra Graceful Shutdown ");
    println!("=======================================================");

    // incoming() trả về một iterator qua các luồng kết nối TcpStream.
    // 💡 Mẹo: Có thể dùng listener.incoming().take(2) để server tự động dừng
    // sau 2 request nhằm kiểm tra cơ chế dọn dẹp tự động (Drop / Graceful Shutdown).
    for stream in listener.incoming() {
        let stream = stream.unwrap();

        // Đẩy tác vụ xử lý kết nối vào ThreadPool:
        pool.execute(|| {
            handle_connection(stream);
        });
    }

    println!("Đang tắt máy chủ web...");
}

fn handle_connection(mut stream: TcpStream) {
    let buf_reader = BufReader::new(&stream);
    
    // Đọc dòng đầu tiên của HTTP Request (Request Line):
    let request_line = buf_reader.lines().next().unwrap().unwrap();

    // Định tuyến (Routing) dựa trên đường dẫn yêu cầu:
    let (status_line, filename) = match &request_line[..] {
        "GET / HTTP/1.1" => ("HTTP/1.1 200 OK", "hello.html"),
        // Kịch bản mô phỏng tác vụ chậm 5 giây để kiểm tra khả năng đa luồng:
        "GET /sleep HTTP/1.1" => {
            thread::sleep(Duration::from_secs(5));
            ("HTTP/1.1 200 OK", "hello.html")
        }
        _ => ("HTTP/1.1 404 NOT FOUND", "404.html"),
    };

    let contents = fs::read_to_string(filename).unwrap();
    let length = contents.len();

    // Định dạng HTTP Response chuẩn:
    let response = format!("{status_line}\r\nContent-Length: {length}\r\n\r\n{contents}");

    // Gửi phản hồi về trình duyệt của người dùng:
    stream.write_all(response.as_bytes()).unwrap();
}
```

---

# 📖 PHẦN VII: PHỤ LỤC & BẢNG TRA CỨU CHUẨN

---

## 🔑 PHỤ LỤC A: BẢNG TỪ KHÓA TRONG RUST (KEYWORDS)

### 1. 📌 Các Từ Khóa Đang Sử Dụng:
- `as`: Ép kiểu dữ liệu nguyên thủy hoặc đổi tên đường dẫn `use`.
- `async`: Biến một khối lệnh hoặc hàm thành trả về `Future`.
- `await`: Tạm dừng hàm async cho đến khi Future sẵn sàng.
- `break`: Thoát ngay lập tức khỏi vòng lặp (có thể trả về giá trị).
- `const`: Định nghĩa hằng số tại thời điểm biên dịch.
- `continue`: Bỏ qua phần còn lại và chuyển sang lần lặp kế tiếp.
- `crate`: Chỉ định gốc của cây module trong đường dẫn module.
- `dyn`: Đánh dấu kiểu phân phối động của một Trait Object (`dyn Trait`).
- `else`: Nhánh rẽ khi điều kiện `if` sai.
- `enum`: Định nghĩa một kiểu dữ liệu liệt kê nhiều biến thể.
- `extern`: Liên kết với các hàm hoặc thư viện bên ngoài (FFI).
- `false`: Giá trị logic sai của kiểu `bool`.
- `fn`: Khai báo hàm hoặc kiểu con trỏ hàm.
- `for`: Duyệt qua các phần tử của một iterator hoặc triển khai Trait.
- `if`: Biểu thức rẽ nhánh điều kiện.
- `impl`: Khối triển khai các phương thức hoặc Trait cho một kiểu.
- `in`: Nằm trong cú pháp vòng lặp `for var in iterator`.
- `let`: Khai báo và gán giá trị cho một biến.
- `loop`: Vòng lặp vô hạn.
- `match`: Biểu thức so khớp mẫu đa nhánh.
- `mod`: Khai báo một module.
- `move`: Buộc closure chiếm quyền sở hữu các biến bị bắt từ môi trường.
- `mut`: Biểu thị tính khả biến (cho phép thay đổi giá trị) của biến hoặc tham chiếu.
- `pub`: Đánh dấu một thực thể là công khai (Public).
- `ref`: Mượn tham chiếu đến trường dữ liệu trong pattern matching.
- `return`: Trả về giá trị sớm từ một hàm.
- `Self`: Bí danh kiểu đại diện cho chính kiểu đang triển khai trong khối `impl`.
- `self`: Tham số đại diện cho đối tượng hiện tại của phương thức.
- `static`: Biến toàn cục có thời gian sống vĩnh viễn suốt chương trình.
- `struct`: Khai báo một cấu trúc dữ liệu.
- `super`: Tham chiếu đến module cha của module hiện tại.
- `trait`: Khai báo một tập hợp các hành vi trừu tượng.
- `true`: Giá trị logic đúng của kiểu `bool`.
- `type`: Định nghĩa một bí danh kiểu mới hoặc kiểu liên kết (*Associated Type*).
- `union`: Khai báo kiểu union tương thích C.
- `unsafe`: Đánh dấu khối mã hoặc hàm không an toàn để kích hoạt 5 siêu năng lực.
- `use`: Đưa các đường dẫn bên ngoài vào phạm vi hiện tại.
- `where`: Mệnh đề ràng buộc Trait Bound ở cuối chữ ký hàm.
- `while`: Vòng lặp điều kiện.

### 2. 🔒 Từ Khóa Dự Phòng (Reserved Keywords):
`abstract`, `become`, `box`, `do`, `final`, `gen` (từ Rust 2024), `macro`, `override`, `priv`, `typeof`, `unsized`, `virtual`, `yield`, `try`.

### 3. 🏷️ Định Danh Thô (Raw Identifiers `r#`):
Nếu bạn cần đặt tên biến hoặc hàm trùng với một từ khóa của Rust (ví dụ biến `match` nhận từ API bên ngoài), dùng tiền tố `r#`:
```rust
let r#match = "kết quả";
```

---

## 🔣 PHỤ LỤC B: BẢNG TOÁN TỬ & KÝ HIỆU CÚ PHÁP

| Ký hiệu | Ý nghĩa trong ngữ cảnh Rust |
| :--- | :--- |
| `!` | Gọi macro (như `println!`) hoặc kiểu Never Type (`!`). |
| `?` | Toán tử lan truyền lỗi trong hàm trả về `Result` hoặc `Option`. |
| `&` | Mượn tham chiếu bất biến, hoặc toán tử bit AND. |
| `&mut` | Mượn tham chiếu khả biến có quyền ghi. |
| `*` | Toán tử giải tham chiếu (*Dereference*), hoặc con trỏ thô `*const T`. |
| `.` | Truy xuất trường của struct hoặc gọi phương thức (`rect.area()`). |
| `..` | Dải số nửa mở `0..5` (từ 0 đến 4), hoặc bỏ qua trường trong pattern. |
| `..=` | Dải số đóng `1..=5` (từ 1 đến 5). |
| `::` | Toán tử phân giải phạm vi đường dẫn (`std::io`, `Point::new`). |
| `->` | Khai báo kiểu trả về của hàm hoặc closure. |
| `=>` | Tách nhánh mẫu và khối lệnh trong biểu thức `match`. |
| `@` | Ràng buộc giá trị vào biến trong pattern matching. |
| `_` | Ký tự giữ chỗ bỏ qua giá trị hoặc mẫu vét cạn. |

---

## ⚙️ PHỤ LỤC C: CÁC TRAIT CÓ THỂ TỰ ĐỘNG DẪN XUẤT (DERIVABLE TRAITS)

Bằng cách thêm thuộc tính `#[derive(...)]` trước struct hoặc enum, trình biên dịch sẽ tự động sinh mã cài đặt chuẩn cho các Trait:

- 🔍 **`Debug`:** Cho phép in cấu trúc bằng định dạng `{:?}` và `{:#?}`.
- 🧬 **`Clone`:** Cung cấp phương thức `.clone()` để sao chép sâu dữ liệu.
- ⚡ **`Copy`:** Cho phép sao chép bit giá trị trên Stack thay vì Move quyền sở hữu (yêu cầu kiểu phải cài `Clone` và mọi trường đều có `Copy`).
- ⚖️ **`PartialEq` & `Eq`:** Cho phép so sánh bằng (`==`, `!=`). `Eq` khẳng định tính chất phản xạ `x == x` tuyệt đối (số thực `f64` không có `Eq` vì `NaN != NaN`).
- 📊 **`PartialOrd` & `Ord`:** Cho phép so sánh lớn hơn/nhỏ hơn (`<`, `>`, `<=`, `>=`).
- #️⃣ **`Hash`:** Cho phép tính toán mã băm để làm khóa (`Key`) trong `HashMap` hoặc `HashSet`.
- 🏁 **`Default`:** Cung cấp giá trị khởi tạo mặc định cho kiểu thông qua hàm `Default::default()`.

---

## 🛠️ PHỤ LỤC D: CÁC CÔNG CỤ PHÁT TRIỂN HỮU ÍCH TRONG HỆ SINH THÁI

1. 🎨 **`rustfmt`:** Công cụ định dạng mã nguồn chuẩn tự động:
   ```bash
   cargo fmt
   ```
2. 📎 **`clippy`:** Linter siêu việt của Rust, phát hiện các đoạn code chưa tối ưu và gợi ý cách viết chuẩn idiom:
   ```bash
   cargo clippy
   ```
3. 🧠 **`rust-analyzer`:** Plugin Language Server Protocol (LSP) cung cấp tính năng tự động hoàn thành mã, phân tích kiểu tức thì trên VS Code và Neovim.
4. 🛡️ **`cargo-audit`:** Quét toàn bộ cây dependencies để cảnh báo các lỗ hổng đã được công bố trên RustSec.
5. 🔭 **`cargo-expand`:** Mở rộng toàn bộ macro để bạn nhìn thấy mã nguồn thực tế mà trình biên dịch đã sinh ra.

#### 🧰 Hệ Sinh Thái Thư Viện Thực Chiến (Production Crates Cần Biết)

| Lĩnh Vực | Tên Crate | Công Dụng Chính |
| :--- | :--- | :--- |
| 🔄 **Serialization** | `serde`, `serde_json` | Chuyển đổi Struct/Enum sang JSON, YAML, TOML cực nhanh. |
| ⏳ **Async Runtime** | `tokio` | Runtime bất đồng bộ tiêu chuẩn công nghiệp cho mạng & I/O. |
| 🛡️ **Xử lý lỗi** | `thiserror`, `anyhow` | Tạo lỗi tùy chỉnh cho thư viện (`thiserror`) và ứng dụng (`anyhow`). |
| 💻 **CLI Tool** | `clap` | Phân tích đối số dòng lệnh tự động qua Derive Macro. |
| 🌐 **Web / API** | `axum`, `actix-web` | Xây dựng RESTful API, WebSocket hiệu năng đỉnh cao. |
| 🗄️ **Database** | `sqlx`, `sea-orm` | Truy vấn SQL bất đồng bộ có kiểm tra cú pháp SQL lúc biên dịch. |
| 📊 **Logging** | `tracing`, `log` | Ghi nhật ký hệ thống có cấu trúc và theo dõi luồng thực thi. |

---

## 📅 PHỤ LỤC E: CÁC PHIÊN BẢN RUST EDITIONS

Rust cam kết tính **Ổn định không làm gãy mã nguồn cũ (Stability Without Stagnation)**. Cứ mỗi 3 năm một lần, Rust phát hành một **Edition** mới (2015, 2018, 2021, 2024):
- Edition cho phép đưa vào các từ khóa mới (như `async`, `await`, `gen`) mà không làm hỏng các crate cũ viết theo chuẩn trước.
- Các crate thuộc các Edition khác nhau hoàn toàn có thể biên dịch và liên kết liền mạch với nhau trong cùng một dự án!
- Để nâng cấp Edition dự án tự động:
  ```bash
  cargo fix --edition
  ```

#### 🚀 Các Điểm Mới Nổi Bật Trong Chuẩn Rust 2024 Edition (`rustc 1.85+`):
- 📌 **Quy tắc bắt giữ Lifetime mới cho `impl Trait` (RPIT Lifetime Capture Rules):** Mặc định kiểu trả về `-> impl Trait` sẽ tự động bắt giữ toàn bộ các tham số generic và lifetime trong chữ ký hàm, sử dụng cú pháp `+ use<'a, T>` khi cần chỉ định tường minh.
- 🛡️ **Siết chặt an toàn FFI & Unsafe:** Khối liên kết ngoại ngữ bắt buộc phải khai báo là `unsafe extern "C" { ... }`, đồng thời bật cảnh báo mặc định `unsafe_op_in_unsafe_fn` (yêu cầu vẫn phải viết khối `unsafe {}` tường minh bên trong hàm `unsafe fn`).
- 🔮 **Từ khóa dự trữ `gen`:** Bảo lưu từ khóa `gen` để phục vụ cho khối sinh dữ liệu tuần tự (*Generator blocks*).
- ⚡ **Chuẩn hóa `LazyLock` và `OnceLock`:** Khởi tạo biến tĩnh lười biếng an toàn đa luồng trực tiếp trong thư viện chuẩn (`std::sync::LazyLock`) mà không cần dùng thêm crate `lazy_static` hay `once_cell` bên ngoài.

---

## 🏷️ PHỤ LỤC F: QUY ƯỚC ĐẶT TÊN CHUẨN (IDIOMATIC NAMING CONVENTIONS)

| Thực thể | Quy ước đặt tên | Ví dụ chuẩn |
| :--- | :--- | :--- |
| 📦 **Packages / Crates** | `snake_case` hoặc `kebab-case` | `rand`, `serde_json`, `tokio` |
| 📁 **Modules** | `snake_case` | `front_of_house`, `network_io` |
| 🏗️ **Types (Struct, Enum, Trait)** | `UpperCamelCase` | `Rectangle`, `Option`, `Summary` |
| ⚙️ **Functions & Methods** | `snake_case` | `add_one`, `calculate_length` |
| 🔢 **Local Variables** | `snake_case` | `secret_number`, `user_input` |
| 📌 **Constants & Statics** | `SCREAMING_SNAKE_CASE` | `MAX_POINTS`, `BUFFER_SIZE` |
| 🧩 **Type Parameters (Generics)** | Chữ in hoa ngắn gọn | `T`, `U`, `Item`, `Key` |
| ⏳ **Lifetimes** | Chữ in thường ngắn | `'a`, `'b`, `'de`, `'static` |

---

## 📚 PHỤ LỤC G: TỪ ĐIỂN THUẬT NGỮ ANH - VIỆT & CẨM NANG RUSTACEAN

- 🔑 **Ownership:** Quyền sở hữu bộ nhớ.
- 🤝 **Borrowing:** Cơ chế mượn dữ liệu.
- 🔗 **Reference:** Tham chiếu.
- 🛡️ **Borrow Checker:** Bộ kiểm tra tính hợp lệ của việc mượn dữ liệu lúc biên dịch.
- 🚚 **Move Semantics:** Cơ chế dịch chuyển quyền sở hữu làm vô hiệu hóa biến cũ.
- 🚫 **Dangling Pointer / Reference:** Con trỏ hoặc tham chiếu lơ lửng trỏ vào vùng nhớ rác đã giải phóng.
- 💥 **Data Race:** Hiện tượng xung đột dữ liệu đa luồng.
- ⚡ **Zero-Cost Abstraction:** Trừu tượng hóa không làm phát sinh chi phí hiệu năng tại thời điểm chạy.
- 🚀 **Monomorphization:** Cơ chế đơn hình hóa, sinh mã máy riêng biệt cho từng kiểu Generic lúc biên dịch.
- ⛓️ **Trait Bound:** Ràng buộc điều kiện của kiểu dữ liệu phải thỏa mãn một Trait.
- 📏 **Lifetime Elision:** Các quy tắc tự động suy luận vòng đời của trình biên dịch.
- 🧠 **Smart Pointer:** Con trỏ thông minh có metadata và quản lý vòng đời tài nguyên.
- 🔓 **Interior Mutability:** Tính khả biến bên trong, cho phép sửa dữ liệu qua tham chiếu bất biến.
- 🎯 **Pattern Matching:** Khớp mẫu cấu trúc dữ liệu.
- 🧩 **Destructuring:** Kỹ thuật phân rã các cấu trúc dữ liệu phức tạp thành các biến đơn.
- 🗑️ **RAII (Resource Acquisition Is Initialization):** Mẫu thiết kế tự động giải phóng tài nguyên khi đối tượng đi ra khỏi phạm vi hoạt động.
- 🛑 **Graceful Shutdown:** Quy trình đóng máy chủ an toàn, chờ các tác vụ dở dang hoàn tất trước khi ngắt luồng.

---

### 🏆 Mười Nguyên Tắc Vàng Để Trở Thành Một Rustacean Giỏi

1. 🎧 **Lắng nghe trình biên dịch `rustc`:** Trình biên dịch Rust là người thầy tận tâm nhất. Hãy đọc kỹ phần `"help:"` và `"note:"` trong mỗi thông báo lỗi.
2. 🔒 **Ưu tiên Bất biến (Immutability):** Chỉ sử dụng `mut` khi thực sự cần thiết phải thay đổi dữ liệu.
3. 🤝 **Mượn (`&`) thay vì Sao chép (`clone`):** Hạn chế lạm dụng `.clone()` chỉ để vượt qua Borrow Checker; hãy học cách thiết kế luồng mượn tham chiếu hợp lý.
4. 🧠 **Hiểu rõ Stack và Heap:** Luôn tự hỏi: dữ liệu này đang nằm ở đâu trong bộ nhớ và ai là người sở hữu nó?
5. 🛡️ **Dùng `Option<T>` và `Result<T, E>`:** Không bao giờ cố gắng tìm cách tạo con trỏ null hay bỏ qua lỗi tiềm ẩn.
6. ❓ **Làm chủ toán tử `?`:** Giúp mã nguồn xử lý lỗi ngắn gọn, thanh lịch và không bị lồng ghép `match` phức tạp.
7. 🔁 **Tận dụng Iterators:** Chuỗi phương thức `map`, `filter`, `collect` vừa an toàn, dễ đọc, vừa được trình biên dịch tối ưu hóa cực nhanh.
8. 📜 **Thiết kế hệ thống dựa trên Traits:** Dùng Trait Bounds và Composition thay cho tư duy kế thừa lớp truyền thống.
9. 🗂️ **Tách biệt `main.rs` và `lib.rs`:** Đưa toàn bộ logic nghiệp vụ vào `lib.rs` để dễ dàng viết bài kiểm thử tự động (Unit Tests & Integration Tests).
10. 💪 **Kiên nhẫn vượt qua giai đoạn đầu:** Cảm giác "chiến đấu với Borrow Checker" là trải nghiệm mà mọi lập trình viên Rust đều trải qua. Khi đã nắm vững quy tắc sở hữu, việc viết mã an toàn tuyệt đối sẽ trở thành phản xạ tự nhiên của bạn!

---
*🎉 Chúc bạn có một hành trình khám phá và làm chủ ngôn ngữ Rust thật nhiều cảm hứng và thành công! 🦀🚀*