# 化學教學互動工具｜Chemistry Teaching Tools

這個 repository 收集高中化學課堂使用的互動式 HTML 教學工具，現階段以 **CH24：原子結構** 為起點。教材以瀏覽器直接開啟，適合在 Windows、macOS、iPad、手機及其他支援現代瀏覽器的裝置上使用。

網站使用 GitHub Pages 發佈，方便教師與學生以網址直接使用教材，而不需要下載或安裝額外軟件。

## 網站入口

啟用 GitHub Pages 後，網站首頁為：

<https://hon20002000.github.io/teaching-tools/>

> GitHub Pages 設定應選擇：`main` branch → `/docs` folder。

## 現有教材

### CH24｜原子結構

| 工具 | 說明 | 網頁連結 |
|---|---|---|
| 氫原子軌域 | 以視覺化方式探索氫原子電子機率分布、量子數、s／p／d 軌域的形狀及節面。 | [開啟教材](https://hon20002000.github.io/teaching-tools/CH24-atom-structure/hydrogen_orbitals.html) |
| 電離能 | 探索原子移走電子所需的能量，並連結有效核電荷、電子層數、遮蔽效應與電子排布。 | [開啟教材](https://hon20002000.github.io/teaching-tools/CH24-atom-structure/Ionization_energy.html) |

## 檔案結構

```text
teaching-tools/
├── README.md
└── docs/
    ├── index.html
    ├── assets/
    │   ├── css/
    │   ├── js/
    │   └── images/
    └── CH24-atom-structure/
        ├── hydrogen_orbitals.html
        └── Ionization_energy.html
```

- `docs/index.html`：網站首頁與教材目錄。
- `docs/CH24-atom-structure/`：第 24 章「原子結構」的互動教材。
- `docs/assets/`：可供不同章節共用的 CSS、JavaScript、圖片、圖示或資料檔案。

## 新增教材方法

建議每個章節使用一個固定格式的資料夾，並以英文小寫和連字號命名，以避免網址中的空格和大小寫問題。

例如新增第 25 章「元素週期律」：

```text
docs/
└── ch25-periodic-trends/
    ├── index.html
    ├── atomic-radius.html
    ├── ionization-energy.html
    ├── css/
    │   └── style.css
    ├── js/
    │   └── app.js
    ├── data/
    │   └── elements.json
    └── images/
        └── periodic-table.png
```

然後在 `docs/index.html` 新增一張連結卡片，例如：

```html
<a class="tool-card" href="./ch25-periodic-trends/">
  <span class="tag">元素週期律</span>
  <h3>第 25 章：元素週期律</h3>
  <p>探索原子半徑、離子半徑、有效核電荷與電離能的週期性變化。</p>
</a>
```

若章節資料夾內有 `index.html`，學生即可用以下形式開啟該章首頁：

```text
https://hon20002000.github.io/teaching-tools/ch25-periodic-trends/
```

## HTML 路徑規則

請使用**相對路徑**，以確保教材可在 GitHub Pages、Windows 和 iPad 正常載入。

正確示例：

```html
<link rel="stylesheet" href="./style.css">
<script src="./script.js"></script>
<img src="./images/orbital.png" alt="原子軌域圖">
<a href="../">返回首頁</a>
```

不要使用 Windows 本機絕對路徑：

```html
<img src="C:\Users\Teacher\Desktop\TeachingTools\images\orbital.png">
```

不要使用反斜線：

```html
<script src="js\app.js"></script>
```

在 GitHub Pages project site 中，也避免將網站內資源寫成以 `/` 開頭：

```html
<!-- 不建議：會指向 hon20002000.github.io 的根目錄 -->
<link rel="stylesheet" href="/style.css">
```

應使用：

```html
<link rel="stylesheet" href="./style.css">
```

或依資料夾層級使用：

```html
<link rel="stylesheet" href="../assets/css/common.css">
```

## 發佈與更新

1. 將新增或修改的 HTML、CSS、JavaScript、圖片及資料檔案放入 `docs/`。
2. Commit 並 push 至 `main` branch。
3. GitHub Pages 會自動重新部署網站。
4. 稍候片刻後，重新整理網站即可看到最新版本。

若網站無法開啟或顯示 404，請檢查：

- GitHub Pages 是否設定為 `Deploy from a branch`。
- Branch 是否選擇 `main`。
- Folder 是否選擇 `/docs`。
- `docs/index.html` 是否存在並已 commit。
- HTML 檔案、資料夾名稱和連結中的大小寫是否完全一致。
- 所有外部 CSS、JavaScript、圖片、JSON 資料是否已一併上傳。

## iPad 使用建議

- 建議直接以 Safari 或 Chrome 開啟 GitHub Pages 網址，而不要下載 HTML 後以本機檔案方式開啟。
- 如需建立常用捷徑，可在 Safari 點選「分享」→「加入主畫面」。
- 涉及圖表、Canvas、三維視覺化或較複雜互動時，建議使用 iPad 橫向模式。
- 如未顯示最新版本，請重新整理頁面；必要時可清除瀏覽器快取後再試。

## 授權與使用

本 repository 內的教材主要用於教學、學習與課堂示範。若要轉載、修改或再發布，請保留原作者資訊並註明來源。

---

Maintained by Leong Honsang · Chemistry Teaching Tools
