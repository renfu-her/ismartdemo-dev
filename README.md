# RC168 iSmartDEMO - Flutter 電商應用

一個功能完整的 Flutter 跨平台電子商務應用程式，專為 RC168 電商平台設計。此專案展示了現代電商 App 的完整功能，包括商品瀏覽、購物車管理、用戶認證、訂單處理、多語言支援等核心功能。

---

## 📱 專案概觀

RC168 iSmartDEMO 是一個基於 Flutter 開發的專業電子商務應用程式，提供完整的線上購物體驗。此專案整合了 RC168 電商平台的 API，實現了從商品瀏覽到結帳的完整購物流程，並支援多種支付方式和用戶管理功能。

### 🎯 主要特色

- **完整的電商功能**：商品瀏覽、購物車、結帳、訂單管理
- **多語言支援**：繁體中文和英文介面
- **響應式設計**：適配不同螢幕尺寸的設備
- **現代化 UI/UX**：Material Design 3 設計語言
- **跨平台支援**：iOS、Android、Web、Desktop

---

## 🚀 主要功能

### 🏠 首頁功能
- **動態商品展示**：最新商品、特價商品、熱銷商品、精選商品
- **廣告橫幅輪播**：支援多張橫幅圖片輪播展示
- **分類導航**：快速瀏覽不同商品分類
- **搜尋功能**：全站商品搜尋

### 📦 商品功能
- **商品列表**：支援分類瀏覽、排序、篩選
- **商品詳情**：
  - 多圖輪播展示
  - 詳細商品描述（支援 HTML 渲染）
  - 多樣化商品選項（顏色、尺寸、日期等）
  - 即時價格計算
  - 庫存狀態顯示
- **商品分享**：支援複製連結和系統分享

### 🛒 購物功能
- **購物車管理**：
  - 添加/移除商品
  - 數量調整
  - 即時價格計算
  - 商品選項驗證
- **收藏夾**：用戶可收藏喜愛的商品
- **結帳流程**：
  - 地址管理
  - 支付方式選擇
  - 訂單確認

### 👤 用戶功能
- **用戶認證**：登入/註冊功能
- **個人資料管理**：修改個人資訊
- **訂單管理**：查看訂單歷史和詳情
- **地址管理**：新增、編輯、刪除收貨地址

### 💳 支付功能
- **多種支付方式**：支援銀行轉帳等支付方式
- **訂單追蹤**：查看訂單狀態和處理進度

### 🌐 其他功能
- **多語言支援**：繁體中文 (zh-TW) 和英文 (en-US)
- **響應式設計**：適配不同螢幕尺寸
- **離線支援**：本地數據緩存
- **錯誤處理**：完善的錯誤提示和處理機制

---

## 🛠 技術架構

### 核心技術
- **框架**：Flutter 3.7.0+
- **語言**：Dart
- **狀態管理**：Provider
- **網路請求**：Dio
- **本地存儲**：SharedPreferences

### 主要依賴套件
```yaml
# UI 元件
carousel_slider: ^5.0.0          # 輪播圖元件
font_awesome_flutter: ^10.7.0    # 圖標庫
flutter_html: ^3.0.0             # HTML 渲染

# 網路和數據
dio: ^5.8.0+1                    # HTTP 客戶端
http: ^1.2.0                     # HTTP 請求

# 狀態管理和本地化
provider: ^6.1.2                 # 狀態管理
flutter_localizations:           # 多語言支援
shared_preferences: ^2.2.2       # 本地存儲

# 平台整合
webview_flutter: ^4.7.0          # WebView 支援
url_launcher: ^6.2.5             # URL 啟動
share_plus: ^10.1.4              # 分享功能
permission_handler: ^11.4.0      # 權限管理

# 工具
flutter_launcher_icons: ^0.14.3   # App 圖標生成
path_provider: ^2.1.5            # 路徑管理
crypto: ^3.0.3                   # 加密功能
```

### 專案結構
```
lib/
├── main.dart                    # 應用程式入口點
├── pages/                       # 頁面元件
│   ├── banner_page.dart         # 橫幅頁面
│   ├── cart_page.dart           # 購物車頁面
│   ├── category_page.dart       # 分類頁面
│   ├── checkout_page.dart       # 結帳頁面
│   ├── customer_profile_page.dart # 客戶資料頁面
│   ├── favorite_page.dart       # 收藏頁面
│   ├── login_page.dart          # 登入頁面
│   ├── order_detail_page.dart   # 訂單詳情頁面
│   ├── order_list_page.dart     # 訂單列表頁面
│   ├── product_detail_page.dart # 商品詳情頁面
│   ├── product_list_page.dart   # 商品列表頁面
│   ├── profile_page.dart        # 個人資料頁面
│   ├── register_page.dart       # 註冊頁面
│   └── search_page.dart         # 搜尋頁面
├── services/                    # 服務層
│   ├── api_service.dart         # API 服務
│   ├── ecpay_service.dart       # 金流服務
│   └── user_service.dart        # 用戶服務
└── widgets/                     # 可重用元件
```

---

## 🚀 開始使用

### 環境要求
- **Flutter SDK**：3.7.0 或更高版本
- **Dart SDK**：3.0.0 或更高版本
- **開發工具**：Android Studio / VS Code with Flutter plugin
- **設備**：實體設備或模擬器

### 安裝步驟

1. **克隆專案**
   ```bash
   git clone <repository-url>
   cd rc168-dev/test
   ```

2. **安裝依賴**
   ```bash
   flutter pub get
   ```

3. **配置 API**
   - 確保 `lib/services/api_service.dart` 中的 API 端點配置正確
   - 檢查 API Key 是否有效

4. **執行應用程式**
   ```bash
   flutter run
   ```

5. **生成 App 圖標**（可選）
   ```bash
   flutter pub run flutter_launcher_icons
   ```

### 平台特定設定

#### Android
- 最低 SDK 版本：21
- 目標 SDK 版本：33
- 支援 ARM64 架構

#### iOS
- 最低 iOS 版本：12.0
- 支援 iPhone 和 iPad

#### Web
- 支援現代瀏覽器
- 響應式設計適配桌面和行動裝置

---

## 🔧 開發指南

### 代碼規範
- 遵循 Flutter 官方代碼規範
- 使用 `flutter_lints` 進行代碼檢查
- 保持代碼註釋和文檔的完整性

### 狀態管理
- 使用 Provider 進行狀態管理
- 將業務邏輯與 UI 分離
- 保持狀態的可預測性和可測試性

### API 整合
- 所有 API 請求通過 `ApiService` 統一管理
- 實現錯誤處理和重試機制
- 支援離線數據緩存

### 本地化
- 支援繁體中文和英文
- 使用 `flutter_localizations` 進行本地化
- 日期、時間、數字格式本地化

---

## 📱 功能展示

### 主要頁面
1. **首頁**：商品展示、橫幅輪播、分類導航
2. **商品列表**：分類瀏覽、搜尋、排序、篩選
3. **商品詳情**：圖片輪播、選項選擇、加入購物車
4. **購物車**：商品管理、數量調整、價格計算
5. **結帳**：地址選擇、支付方式、訂單確認
6. **個人中心**：用戶資料、訂單歷史、設定

### 特色功能
- **響應式設計**：適配不同螢幕尺寸
- **多語言支援**：無縫切換語言
- **離線支援**：本地數據緩存
- **錯誤處理**：用戶友好的錯誤提示

---

## 🔮 未來規劃

### 短期目標
- [ ] 增加更多支付方式
- [ ] 優化圖片載入效能
- [ ] 增加推播通知功能
- [ ] 完善錯誤處理機制

### 長期目標
- [ ] 增加社交功能（評論、評分）
- [ ] 實現 AR 商品預覽
- [ ] 增加語音搜尋功能
- [ ] 支援更多語言

---

## 🤝 貢獻指南

我們歡迎所有形式的貢獻！請遵循以下步驟：

1. **Fork 專案**
2. **建立功能分支** (`git checkout -b feature/AmazingFeature`)
3. **提交變更** (`git commit -m 'Add some AmazingFeature'`)
4. **推送到分支** (`git push origin feature/AmazingFeature`)
5. **開啟 Pull Request**

### 貢獻類型
- 🐛 Bug 修復
- ✨ 新功能開發
- 📝 文檔改進
- 🎨 UI/UX 優化
- ⚡ 效能優化

---

## 📄 授權

本專案採用 MIT 授權條款。詳情請參閱 [LICENSE](LICENSE) 文件。

---

## 📞 聯絡資訊

- **專案維護者**：RC168 開發團隊
- **技術支援**：請透過 Issue 或 Pull Request 聯絡
- **商業合作**：請直接聯絡 RC168 團隊

---

## 🙏 致謝

感謝所有為此專案做出貢獻的開發者和測試者！

---

*最後更新：2024年12月*