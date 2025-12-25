# MoonTV Source (影視源配置庫)

本倉庫用於託管 MoonTV (LunaTV) 及兼容客戶端的配置數據源。包含影視接口配置、直播源列表及站點自定義設置。

通過引用本倉庫的 Raw 文件鏈接，可以實現 MoonTV 的快速配置與雲端更新。

## 📂 文件結構說明

| 文件名 | 說明 | 格式 |
| :--- | :--- | :--- |
| `config.json` | **核心配置文件** (站點設置、接口列表、解析源等) | JSON |
| `live.m3u` / `live.txt` | 直播源列表 (IPTV) | M3U / TXT |
| `custom_spider.jar` | 自定義爬蟲源 (如需要) | JAR |
| `wallpaper.json` | 壁紙/背景圖配置 | JSON |

> **注意**：以上文件名僅為示例，請根據您實際上傳的文件名進行對應。

## 🚀 使用方法

### 1. 獲取引用鏈接
為了讓 MoonTV 客戶端讀取配置，您需要使用文件的 **Raw (原始數據)** 鏈接。
GitHub 的原始鏈接格式通常為：
`https://raw.githubusercontent.com/shijianus/moontv-source/main/文件名`

例如：
- 配置地址: `https://raw.githubusercontent.com/shijianus/moontv-source/main/config.json`

### 2. 在 MoonTV 中配置
1. 打開 MoonTV (或 LunaTV) 客戶端/網頁端。
2. 進入 **設置 (Settings)** > **配置源 (Source)**。
3. 在「配置地址」欄位中填入上述獲取的 `config.json` 鏈接。
4. 點擊「確認」或「更新」，等待數據加載完成。

### 3. Docker 部署掛載 (可選)
如果您是自建服務端，也可以直接將此倉庫的文件掛載到容器中：

```bash
docker run -d \
  --name moontv \
  -v $(pwd)/moontv-source/config.json:/app/config.json \
  -p 3000:3000 \
  ghcr.io/senshinya/moontv:latest

```

## 🛠️ 維護與更新

* **更新源**：直接修改本倉庫中的 `.json` 或 `.m3u` 文件並提交 (Push)。
* **緩存刷新**：客戶端通常有緩存，更新文件後，用戶可能需要重啟應用或手動點擊「更新配置」才能看到最新內容。
* **國內加速**：如果 GitHub Raw 鏈接在部分地區訪問困難，可以使用 CDN 加速服務（如 `jsDelivr`）：
* 原鏈接：`https://raw.githubusercontent.com/...`
* 加速鏈接：`https://cdn.jsdelivr.net/gh/shijianus/moontv-source@main/config.json`



## ⚠️ 免責聲明 (Disclaimer)

1. 本倉庫僅用於學習和技術交流，**不存儲任何視頻文件**。
2. 所有配置數據均收集自互聯網，其內容版權歸原作者或原平台所有。
3. 請勿將本項目用於任何商業用途，使用本項目產生的任何後果由使用者自行承擔。
4. 如果任何內容侵犯了您的權益，請提交 Issue 聯繫刪除。

---

*Created by [shijianus*](https://github.com/shijianus)
