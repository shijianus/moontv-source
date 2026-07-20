# MoonTV Source (影視源配置庫)

本倉庫專門為 **MoonTV / LunaTV** 及兼容客戶端提供配置數據源。  
為減少一次載入過多資源造成的檢索負擔，現已改為**分類專用配置檔**，方便用戶按需求選擇。

## 📂 目前文件結構

| 文件名                  | 說明                                   | 建議用途                     |
|-------------------------|----------------------------------------|------------------------------|
| `config.json`           | 綜合通用配置（可選）                   | 一般使用                     |
| `config-films.json`     | 電影 + 劇集 + 直播頻道                 | 影音綜合                     |
| `config-anime.json`     | 動漫專用（日漫 + 國漫為主）            | 動漫用戶                     |
| `config-movie.json`     | 電影專用                               | 只看電影                     |
| `config-tv.json`        | 劇集專用（國產/韓/日/美劇）            | 追劇用戶                     |
| `config-variety.json`   | 綜藝專用                               | 綜藝粉絲                     |
| `config-doc.json`       | 紀錄片專用                             | 紀錄片                       |
| `config-live.json`      | 直播頻道專用（IPTV）                   | 電視直播                     |
| `config-adults.json`    | 成人內容專用（獨立分離）               | 成人模式                     |

> 每個分類檔案約控制在 **30~50 個有效源**，避免過度檢索。

## 🚀 使用方法

### 1. 取得 Raw 連結
GitHub Raw 格式：
```
https://raw.githubusercontent.com/shijianus/moontv-source/main/檔案名
```

**常用範例：**
- 動漫專用：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-anime.json`
- 電影專用：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-movie.json`
- 劇集專用：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-tv.json`
- 直播頻道：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-live.json`
- 成人專用：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-adults.json`
- 綜合影音：`https://raw.githubusercontent.com/shijianus/moontv-source/main/config-films.json`

### 2. 在 MoonTV / LunaTV 中配置
1. 打開客戶端 → **設置 (Settings)** → **配置源 (Source)**
2. 將對應的 Raw 連結貼到「配置地址」
3. 點擊確認 / 更新配置

可同時添加多個分類配置，或依需求切換使用。

### 3. 國內加速（推薦）
如果 GitHub Raw 存取較慢，可使用 jsDelivr：
```
https://cdn.jsdelivr.net/gh/shijianus/moontv-source@main/檔案名
```
例如：
```
https://cdn.jsdelivr.net/gh/shijianus/moontv-source@main/config-anime.json
```

### 4. Docker 掛載範例（可選）
```bash
docker run -d \
  --name moontv \
  -v $(pwd)/moontv-source:/app/config \
  -p 3000:3000 \
  ghcr.io/senshinya/moontv:latest
```

## 🛠️ 維護說明

- 所有配置均為**公開免費源**，定期更新與清理失效接口。
- 成人內容已完全獨立至 `config-adults.json`，與其他檔案分離。
- 更新後請手動在客戶端點擊「更新配置」或重啟應用以刷新緩存。
- 歡迎提交 Issue 回報失效源或建議新增資源。

## ⚠️ 免責聲明

1. 本倉庫僅供學習與技術交流使用，**不存儲任何視頻內容**。
2. 所有接口數據均來自互聯網公開資源，版權歸原權利人所有。
3. 請遵守當地法律法規，勿用於商業用途。
4. 使用本配置產生的任何後果由使用者自行承擔。
5. 如有侵權內容，請提交 Issue，我們會盡快處理。

---

**維護者**：[shijianus](https://github.com/shijianus)  
最後更新：2026-07-20
