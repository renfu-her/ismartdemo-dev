# iSmartDEMO - Flutter 電商應用

一個功能豐富的 Flutter 電商 App 範例，展示了商品瀏覽、多語言支援、API 整合、狀態管理等多種現代 App 開發實踐。

---

## 目錄
- [專案概觀](#專案概觀)
- [主要功能](#主要功能)
- [技術棧](#技術棧)
- [專案結構](#專案結構)
- [開始使用](#開始使用)
- [潛在改進方向](#潛在改進方向)
- [貢獻](#貢獻)
- [授權](#授權)

---

## 專案概觀

iSmartDEMO 是一個使用 Flutter 開發的跨平台電子商務應用程式。它提供了一個完整的購物體驗，包括瀏覽不同類別的商品、查看詳細資訊、管理購物車和收藏夾，並支援多種語言介面。此專案旨在展示如何在 Flutter 中整合後端 API、處理複雜的 UI 互動和狀態管理。

---

## 主要功能

-   **多樣化的首頁展示**：
    -   動態載入最新、特價、熱銷、推薦等多個商品區塊。
    -   區塊標題 (`home_title`) 和顯示狀態 (`home_status`) 由 API 控制。
    -   廣告橫幅輪播。
-   **產品瀏覽與詳情**：
    -   商品列表頁，可依分類或搜尋結果顯示。
    -   產品詳情頁：
        -   圖片輪播 (`CarouselSlider`)。
        -   豐富的產品描述（支援 HTML 渲染）。
        -   多樣化的產品選項（單選按鈕 - 顏色/尺寸、下拉選單、日期時間選擇）。
        -   選項與主圖片即時連動更新。
        -   動態計算並格式化顯示價格（處理原價、特價、選項加價）。
        -   根據 `dis_price` 狀態控制價格與購物車顯示。
        -   庫存狀態顯示。
-   **購物車與收藏**：
    -   用戶登入後可將商品加入購物車。
    -   購物車內可調整數量、查看總價。
    -   必填選項未選時提示用戶。
    -   用戶登入後可將商品加入/移除收藏夾。
-   **本地化與國際化**：
    -   支援繁體中文 (zh-TW) 和英文 (en-US) 語言。
    -   預設語言為繁體中文。
    -   日期與時間選擇器根據選定語言進行本地化顯示。
-   **用戶體驗**：
    -   商品分享功能（複製連結、系統分享）。
    -   統一的價格顯示格式。
    -   基礎的錯誤處理（API 請求、圖片載入）。
    -   Webview 元件用於顯示外部網頁內容。

---

## 技術棧

-   **框架**: Flutter (建議使用最新穩定版)
-   **語言**: Dart
-   **狀態管理**: `provider`
-   **網路請求**: `dio`
-   **UI 元件**: `carousel_slider`, `flutter_html`, `webview_flutter`
-   **本地化**: `flutter_localizations`
-   **本地存儲**: `shared_preferences`
-   **互動**: `url_launcher`, `share_plus`
-   **工具**: `flutter_launcher_icons`

詳細依賴請參閱 `pubspec.yaml`。

---

## 專案結構

```
lib/
├── main.dart                # App 入口, MaterialApp 設定, 首頁狀態管理
├── pages/                   # 各個獨立頁面 (Screen/View)
│   ├── home_page.dart         # (可能與 main.dart 中的 HomeContent 合併或作為容器)
│   ├── product_list_page.dart
│   ├── product_detail_page.dart
│   ├── cart_page.dart
│   ├── login_page.dart        # (假設存在)
│   └── ...                  # 其他頁面
├── services/                # 外部服務互動 (API, 本地存儲等)
│   ├── api_service.dart     # 處理所有後端 API 請求
│   └── user_service.dart    # 管理用戶登入狀態、收藏夾等
├── widgets/                 # 可重用的 UI 元件
│   ├── product_card.dart    # (範例)
│   └── ...
├── models/                  # 資料模型 (若有定義)
├── utils/                   # 通用工具函式 (如價格格式化)
assets/
├── images/                  # App 內使用的靜態圖片
├── ic_launcher.png          # App 啟動圖標原始檔
pubspec.yaml                 # 專案設定、依賴管理、資源宣告
README.md                    # 專案說明文件
```

---

## 開始使用

**環境要求:**

-   Flutter SDK (請參考 [官方安裝指南](https://flutter.dev/docs/get-started/install))
-   Dart SDK (隨 Flutter 安裝)
-   開發工具 (Android Studio / VS Code with Flutter plugin)
-   實體設備或模擬器

**安裝與執行:**

1.  **取得專案:**
    ```bash
    git clone <YOUR_REPOSITORY_URL>
    cd iSmartDEMO
    ```

2.  **安裝依賴:**
    ```bash
    flutter pub get
    ```

3.  **執行 App:**
    ```bash
    flutter run
    ```

4.  **(可選) 生成 App 圖標:** (若 `assets/ic_launcher.png` 有修改)
    ```bash
    flutter pub run flutter_launcher_icons
    ```

---

## 潛在改進方向

此專案雖功能完善，但仍有以下可持續優化的方向：

1.  **狀態管理精煉**: 對於複雜頁面（如 `ProductDetailPage` 或 `HomeContent`），考慮將更多 UI 狀態和業務邏輯遷移到 `Provider` 或其他狀態管理方案 (如 Riverpod, Bloc)，減少 `setState` 的使用，提高可測試性和可維護性。
2.  **錯誤處理強化**: 建立更一致、用戶友好的錯誤處理機制，例如統一的 API 錯誤提示、網絡異常處理、空狀態顯示等。
3.  **代碼模組化**: 將大型 Widget（如 `ProductDetailPage` 中的選項區塊、首頁的各個商品列表）拆分成更小的、獨立的 Widget，提高代碼複用性和可讀性。
4.  **測試覆蓋**: 增加單元測試（針對 Service、Utils）和 Widget 測試（針對核心 UI 元件和頁面），確保代碼品質與功能穩定。
5.  **依賴更新**: 定期使用 `flutter pub outdated` 檢查並更新依賴套件。
6.  **效能優化**: 對於長列表或複雜計算，評估是否存在效能瓶頸，並進行相應優化。

---

## 貢獻

歡迎透過 Pull Request 或 Issue 為此專案做出貢獻。

1.  Fork 此儲存庫。
2.  建立您的 Feature 分支 (`git checkout -b feature/AmazingFeature`)。
3.  提交您的變更 (`git commit -m 'Add some AmazingFeature'`)。
4.  將變更推送到分支 (`git push origin feature/AmazingFeature`)。
5.  開啟一個 Pull Request。

---

## 授權

本專案採用 MIT 授權。詳情請參閱 `LICENSE` 文件（如果存在）。