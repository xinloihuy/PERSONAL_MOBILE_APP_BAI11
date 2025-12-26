# Personal Mobile App Bai11

Ứng dụng quản lý danh sách cá nhân cho Android với chức năng xác thực người dùng và quản lý các mục danh sách.

## 📋 Mục lục

- [Tính năng](#tính-năng)
- [Yêu cầu](#yêu-cầu)
- [Cài đặt](#cài-đặt)
- [Cấu trúc Dự án](#cấu-trúc-dự-án)
- [Hướng dẫn Sử dụng](#hướng-dẫn-sử-dụng)
- [Công nghệ Sử dụng](#công-nghệ-sử-dụng)
- [Kiến trúc Ứng dụng](#kiến-trúc-ứng-dụng)
- [Cơ sở Dữ liệu](#cơ-sở-dữ-liệu)
- [Đóng góp](#đóng-góp)

## ✨ Tính năng

- **Xác thực người dùng**: Đăng nhập và đăng ký tài khoản
- **Quản lý danh sách**: Thêm, sửa, xóa các mục danh sách
- **Dữ liệu cá nhân**: Mỗi người dùng có danh sách riêng
- **Giao diện thân thiện**: Thiết kế đơn giản, dễ sử dụng
- **MVVM Pattern**: Kiến trúc hiện đại với ViewModel và LiveData

## 🔧 Yêu cầu

- **Android SDK**: API 24+ (Android 7.0)
- **Target SDK**: API 36 (Android 15)
- **Kotlin**: 1.9.x trở lên
- **Gradle**: 8.x trở lên

## 📥 Cài đặt

### 1. Clone Repository

```bash
git clone https://github.com/xinloihuy/PERSONAL_MOBILE_APP_BAI11
cd PERSONAL_MOBILE_APP_BAI11
```

### 2. Mở trong Android Studio

- Mở Android Studio
- Chọn "Open an Existing Project"
- Chọn thư mục dự án

### 3. Build Project

```bash
# Sử dụng Gradle Wrapper
./gradlew build

# Hoặc trên Windows
gradlew.bat build
```

### 4. Chạy Ứng dụng

- Kết nối thiết bị Android hoặc khởi động Android Emulator
- Nhấp vào "Run" trong Android Studio hoặc chạy:

```bash
./gradlew installDebug
```

## 📁 Cấu trúc Dự án

```
PERSONAL_MOBILE_APP_BAI11/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/myapplication/
│   │   │   │   ├── LoginActivity.kt          # Màn hình đăng nhập
│   │   │   │   ├── RegisterActivity.kt       # Màn hình đăng ký
│   │   │   │   ├── MainActivity.kt           # Màn hình chính
│   │   │   │   ├── ItemViewModel.kt          # ViewModel quản lý dữ liệu
│   │   │   │   ├── ItemViewModelFactory.kt   # Factory cho ViewModel
│   │   │   │   ├── ItemAdapter.kt            # Adapter cho RecyclerView
│   │   │   │   ├── Item.kt                   # Model dữ liệu
│   │   │   │   └── DBHelper.kt               # Helper cơ sở dữ liệu
│   │   │   ├── res/
│   │   │   │   ├── layout/                   # Layout XML
│   │   │   │   ├── drawable/                 # Tài nguyên hình ảnh
│   │   │   │   ├── values/                   # Tài nguyên chuỗi, màu sắc, kiểu
│   │   │   │   └── mipmap/                   # Biểu tượng ứng dụng
│   │   │   └── AndroidManifest.xml
│   │   ├── androidTest/                      # Bài kiểm tra thiết bị
│   │   └── test/                             # Bài kiểm tra đơn vị
│   ├── build.gradle.kts                      # Cấu hình Gradle
│   └── proguard-rules.pro
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

## 🚀 Hướng dẫn Sử dụng

### Đăng Nhập

1. Nhập tên người dùng và mật khẩu
2. Nhấp nút "Đăng nhập"
3. Nếu thông tin chính xác, sẽ chuyển đến màn hình chính

### Đăng Ký

1. Nhấp "Đăng ký" trên màn hình đăng nhập
2. Nhập tên người dùng và mật khẩu
3. Nhấp "Tạo tài khoản"

### Quản Lý Danh Sách

- **Thêm mục**: Nhập tên mục và nhấp "Thêm"
- **Sửa mục**: Nhấp biểu tượng sửa trên mục
- **Xóa mục**: Nhấp biểu tượng xóa trên mục

## 🛠️ Công nghệ Sử dụng

### Framework & Libraries

- **Kotlin**: Ngôn ngữ lập trình chính
- **AndroidX**: Thư viện hỗ trợ Android hiện đại
  - `androidx.appcompat`: Hỗ trợ tương thích ngược
  - `androidx.constraintlayout`: Bố cục ràng buộc
  - `androidx.lifecycle`: Quản lý vòng đời
  - `androidx.databinding`: Data Binding
  - `androidx.recyclerview`: Danh sách cuộn

- **Material Design**: Thành phần giao diện Material
- **SQLite**: Cơ sở dữ liệu cục bộ

### Build Tools

- **Gradle**: Công cụ xây dựng
- **Android Gradle Plugin**: Plugin xây dựng Android
- **ProGuard**: Tối ưu hóa và bảo vệ code

## 🏗️ Kiến trúc Ứng dụng

Ứng dụng sử dụng **MVVM Pattern** (Model-View-ViewModel):

```
View (Activity/Fragment)
    ↓
ViewModel (ItemViewModel)
    ↓
Repository/Model (DBHelper, Item)
    ↓
Database (SQLite)
```

### Các Thành phần Chính

| Thành phần | Mô tả |
|-----------|-------|
| **Activity** | Giao diện người dùng (LoginActivity, RegisterActivity, MainActivity) |
| **ViewModel** | Quản lý dữ liệu và logic ứng dụng |
| **Adapter** | Hiển thị dữ liệu trong RecyclerView |
| **DBHelper** | Quản lý truy cập cơ sở dữ liệu SQLite |
| **Data Binding** | Kết nối dữ liệu với giao diện |

## 💾 Cơ sở Dữ liệu

### Schema SQLite

**Bảng Users:**
```sql
CREATE TABLE users (
    username TEXT PRIMARY KEY,
    password TEXT
)
```

**Bảng Items:**
```sql
CREATE TABLE items (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    username TEXT
)
```

## 🔒 Bảo Mật

⚠️ **Lưu ý**: Ứng dụng này là dự án học tập. Trong sản xuất:
- Mã hóa mật khẩu (sử dụng BCrypt hoặc tương tự)
- Sử dụng HTTPS cho API
- Không lưu trữ dữ liệu nhạy cảm trong SharedPreferences
- Thực hiện xác thực phía máy chủ


## 📞 Hỗ Trợ

Nếu gặp vấn đề:

1. Kiểm tra tệp `logcat` trong Android Studio
2. Đảm bảo Java Version là 11 trở lên
3. Xóa bộ nhớ cache build: `./gradlew clean`
4. Xây dựng lại dự án: `./gradlew build`