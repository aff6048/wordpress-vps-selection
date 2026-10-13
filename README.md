# WordPress VPS 推薦：從規格、機房到月費怎麼挑，用 DMIT 三地套餐把預算花在對的地方

會開始查「WordPress VPS 推薦」，通常不是因為你還沒聽過共享主機，而是你已經用過了。一開始每月幾十塊很香，等到外掛裝到二十幾個、某篇文被轉發、後台開始轉圈，你才發現自己買的其實是一張共享的入場券。

這篇不打算給你一份「十大主機排行」。更實用的做法是：先搞清楚你這一站真正吃多少資源、訪客在哪裡，再回頭看方案表。以下用 DMIT 這家主打洛杉磯、香港、東京三地機房的主機商當實際案例，把它的全系列方案攤開來對照。

## 先問自己三個問題，答案會直接砍掉一半選項

選 VPS 最常犯的錯，是從規格表開始看。順序應該反過來。

**第一，你的網站是「給人看」還是「給人買」。** 純內容站的外掛數量通常能壓在 15 個以內，快取一開，1 核 1GB 就跑得動。只要有購物車、會員、預約表單，資料庫寫入變頻繁，記憶體不夠就會直接反應在結帳頁轉圈。

**第二，訪客從哪裡來。** 這一題決定了你要不要為「線路」多付錢。台北到香港、台北到東京的網路距離，跟台北到洛杉磯不是同一個量級。如果你的訪客九成在台灣，卻買了一條主打中國大陸回程優化的線路，那筆溢價基本上是白花的。

**第三，你願意扛多少維運。** VPS 給的是 root 權限，不是「拿來就能用」的環境。系統更新、PHP 版本、SSL 續期、備份還原，全部是你的事。不想碰這些，管理型主機貴有它的道理；願意碰，VPS 的每塊錢買到的資源多得多。

## WordPress 真正吃的是記憶體跟磁碟，不是核心數

PHP-FPM 處理請求、MySQL 或 MariaDB 撐資料庫，Nginx 或 LiteSpeed 負責前面擋人。整條鏈裡最容易先爆的是記憶體——尤其是沒裝好快取、每個請求都去戳資料庫的那種站。核心數比較像是「同時能處理幾個請求」，1 核配上好的快取，往往比 4 核配一個爛外掛堆疊還快。

實務上的抓法可以這樣看：

| 網站型態 | 建議規格 | 說明 |
| --- | --- | --- |
| 個人部落格、作品集，日訪客數百 | 1 vCPU / 1GB / 20GB SSD | 一定要開快取；記憶體吃緊時搭配 swap |
| 內容站、企業形象站，外掛 20–40 個 | 2 vCPU / 2GB / 40GB SSD | SEO、表單、分析類外掛同時跑比較穩 |
| WooCommerce、會員系統、同台多站 | 4 vCPU / 4GB 以上 / 80GB SSD | 資料庫與快取都要記憶體，低於 4GB 會很勉強 |

有件事值得先講：**如果預算有限，把錢加在記憶體和月流量上，比加在核心數上更有感。**

## 機房放哪裡，比選哪一家主機商更影響體感

訪客在台灣、香港、東南亞，選香港或東京機房；訪客在美西或全球分散，選洛杉磯再配 CDN；訪客主要在中國大陸，才需要認真考慮 CN2 GIA 這類回程優化線路。

這也解釋了為什麼同一家廠商的方案可以差好幾倍價。以 DMIT 為例，方案按「機房 × 線路 × 硬體平台」排列組合，線路分三檔：

| 線路 | 路由特性 | 適合誰 | 價格帶 |
| --- | --- | --- | --- |
| Premium（Pro） | 三網 CN2 GIA 回程 | 訪客在中國大陸、對晚高峰品質有硬要求 | 最高 |
| Eyeball（EB） | CMIN2／CMI／AS9929 回程，流量給得比 Pro 多 | 預算優先，但希望大陸訪客體驗比一般國際線路好 | 中等 |
| Tier 1（T1） | 純國際 BGP，無中國方向優化 | 訪客在台灣、歐美、日本，或當備份、CI/CD 節點 | 最低 |

一句話判斷：**訪客不在中國大陸，就別為 Pro 付錢。** 這是 WordPress 站長最容易多花的一筆。

## DMIT 全方案標價對照

> 下表整理的是各機房、各線路的公開標價。同一個線路名稱會對應不同硬體平台（AS3 為 AMD EPYC 7003、AN4 為 EPYC 9004、AN5 為 EPYC 9005），補貨批次不同、標價可能不同，庫存變動也頻繁。實際價格與供貨狀況一律以結帳頁面顯示為準。

### Tier 1 國際線路（洛杉磯／香港／東京同價）

| 方案 | CPU | 記憶體 | SSD | 月流量／頻寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1.WEE | 1 核 | 1GB | 20GB | 1TB @4Gbps | 限速 50–100Mbps 不限流量 | $36.90／年 | [ 看年付入門方案](https://www.dmit.io/aff.php?aff=12046) |
| T1.TINY | 1 核 | 1–2GB | 20–40GB | 2TB @4Gbps | 限速 100–200Mbps 不限流量 | $6.90／月 | [ 查看 T1.TINY](https://www.dmit.io/aff.php?aff=12046) |
| T1.STARTER | 2 核 | 2GB | 40GB | 4TB @10Gbps | 限速 100–200Mbps 不限流量 | $12.90／月 | [ 查看 T1.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| T1.MINI | 2 核 | 2–4GB | 60–80GB | 8TB @10Gbps | 限速 100–200Mbps 不限流量 | $21.90／月 | [ 查看 T1.MINI](https://www.dmit.io/aff.php?aff=12046) |
| T1.MICRO | 4 核 | 4GB | 80–120GB | 16TB @10Gbps | 限速 200–500Mbps 不限流量 | $32.90／月 | [ 查看 T1.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| T1.MEDIUM | 4 核 | 8GB | 160GB | 32TB @10Gbps | 限速 200–500Mbps 不限流量 | $49.90／月 | [ 查看 T1.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| T1.LARGE | 8 核 | 16GB | 320GB | 64TB @10Gbps | 限速 500Mbps–1Gbps 不限流量 | $99.90／月 | [ 查看 T1.LARGE](https://www.dmit.io/aff.php?aff=12046) |
| T1.GIANT | 8 核 | 24GB | 640GB | 128TB @10Gbps | 限速 500Mbps–1Gbps 不限流量 | $199.90／月 | [ 查看 T1.GIANT](https://www.dmit.io/aff.php?aff=12046) |

洛杉磯還多一條以流量為主的 AN5 平台 Tier 1 VOLUME 系列，同價位給的流量明顯更多：

| 方案 | CPU | 記憶體 | SSD | 月流量 @頻寬 | 超量後 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1 VOLUME 入門 | 2 核 | 2GB | 40GB | 5TB @10Gbps | 限速 100Mbps 不限流量 | $14.90／月 | [ 看洛杉磯大流量方案](https://www.dmit.io/aff.php?aff=12046) |
| T1 VOLUME | 2 核 | 4GB | 80GB | 10TB @10Gbps | 限速 200Mbps 不限流量 | $23.90／月 | [ 查看 2核4G 規格](https://www.dmit.io/aff.php?aff=12046) |
| T1 VOLUME | 4 核 | 4GB | 120GB | 20TB @10Gbps | 限速 200Mbps 不限流量 | $36.90／月 | [ 查看 4核4G 規格](https://www.dmit.io/aff.php?aff=12046) |
| T1 VOLUME | 4 核 | 8GB | 160GB | 40TB @10Gbps | 限速 500Mbps 不限流量 | $52.90／月 | [ 查看 4核8G 規格](https://www.dmit.io/aff.php?aff=12046) |
| T1 VOLUME | 8 核 | 16GB | 240GB | 80TB @10Gbps | 限速 500Mbps 不限流量 | $119.90／月 | [ 查看 8核16G 規格](https://www.dmit.io/aff.php?aff=12046) |
| T1 VOLUME | 12 核 | 24GB | 320GB | 160TB @10Gbps | 限速 500Mbps 不限流量 | $199.90／月 | [ 查看 12核24G 規格](https://www.dmit.io/aff.php?aff=12046) |

### 洛杉磯 Premium（CN2 GIA 回程）

| 方案 | CPU | 記憶體 | SSD | 月流量 @頻寬 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- |
| Pro.TINY | 1 核 | 2GB | 20GB | 1TB @1Gbps | $9.99／月 | [ 看洛杉磯 Pro 入門](https://www.dmit.io/aff.php?aff=12046) |
| Pro.Pocket | 1–2 核 | 2GB | 40GB | 1.5TB @4Gbps | $14.90／月 | [ 查看 Pro.Pocket](https://www.dmit.io/aff.php?aff=12046) |
| Pro.STARTER | 2 核 | 2GB | 80GB | 3TB @10Gbps | $29.90／月 | [ 查看 Pro.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MINI | 2 核 | 4GB | 80GB | 5TB @10Gbps | $58.88／月 | [ 查看 Pro.MINI](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MICRO | 4 核 | 4GB | 160GB | 7TB @10Gbps | $74.99／月 | [ 查看 Pro.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| Pro.MEDIUM | 4–6 核 | 8GB | 160GB | 14TB @10Gbps | $168.88／月 | [ 查看 Pro.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| Pro.LARGE | 8 核 | 16GB | 320GB | 25TB @10Gbps | $338.88／月 | [ 查看 Pro.LARGE](https://www.dmit.io/aff.php?aff=12046) |
| Pro.GIANT | 8 核 | 24GB | 640GB | 50TB @10Gbps | $619.99／月 | [ 查看 Pro.GIANT](https://www.dmit.io/aff.php?aff=12046) |

### 洛杉磯 Eyeball（CMIN2 回程）

| 方案 | CPU | 記憶體 | SSD | 月流量 @頻寬 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- |
| EB.TINY | 1 核 | 2GB | 20GB | 1.5TB @2Gbps | $9.99／月 | [ 看洛杉磯 EB 入門](https://www.dmit.io/aff.php?aff=12046) |
| EB.Pocket | 2 核 | 2GB | 40GB | 3TB @4Gbps | $14.90／月 | [ 查看 EB.Pocket](https://www.dmit.io/aff.php?aff=12046) |
| EB.STARTER | 2 核 | 2GB | 80GB | 5TB @10Gbps | $29.90／月 | [ 查看 EB.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| EB.MINI | 4 核 | 4GB | 80GB | 10TB @10Gbps | $58.88／月 | [ 查看 EB.MINI](https://www.dmit.io/aff.php?aff=12046) |
| EB.MICRO | 4 核 | 4GB | 160GB | 14TB @10Gbps | $74.99／月 | [ 查看 EB.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| EB.MEDIUM | 6 核 | 8GB | 160GB | 30TB @10Gbps | $168.88／月 | [ 查看 EB.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| EB.LARGE | 8 核 | 16GB | 320GB | 50TB @10Gbps | $338.88／月 | [ 查看 EB.LARGE](https://www.dmit.io/aff.php?aff=12046) |
| EB.GIANT | 12 核 | 24GB | 640GB | 100TB @10Gbps | $619.99／月 | [ 查看 EB.GIANT](https://www.dmit.io/aff.php?aff=12046) |

同一個 TINY 方案，AS3 平台（EPYC 7003）的標價會落在 $10.90／月左右，比 AN4／AN5 平台稍高。下單頁顯示哪個平台、哪個價格，就照那個走。

### 香港與東京方案

| 機房／線路 | 方案 | CPU | 記憶體 | SSD | 月流量 | 價格 | 購買 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 香港 Pro | TINY | 1 核 | 1GB | 20GB | 500GB @1Gbps | $39.90／月 | [ 看香港 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | STARTER | 1 核 | 2GB | 40GB | 1TB @1Gbps | $79.90／月 | [ 查看香港 Pro.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | MINI | 2 核 | 2GB | 60GB | 1.5TB @1Gbps | $119.90／月 | [ 查看香港 Pro.MINI](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | MICRO | 4 核 | 4GB | 80GB | 2TB @1Gbps | $159.90／月 | [ 查看香港 Pro.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | MEDIUM | 4 核 | 8GB | 160GB | 2.5TB @1Gbps | $179.90／月 | [ 查看香港 Pro.MEDIUM](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | LARGE | 8 核 | 16GB | 320GB | 3TB @1Gbps | $239.90／月 | [ 查看香港 Pro.LARGE](https://www.dmit.io/aff.php?aff=12046) |
| 香港 Pro | GIANT | 8 核 | 24GB | 640GB | 6TB @1Gbps | $499.90／月 | [ 查看香港 Pro.GIANT](https://www.dmit.io/aff.php?aff=12046) |
| 香港 EB | TINY | 1 核 | 1GB | 20GB | 1TB @1Gbps | $29.90／月 | [ 看香港 Eyeball 方案](https://www.dmit.io/aff.php?aff=12046) |
| 香港 EB | STARTER | 1 核 | 2GB | 40GB | 2TB @2Gbps | $59.90／月 | [ 查看香港 EB.STARTER](https://www.dmit.io/aff.php?aff=12046) |
| 香港 EB | MINI | 2 核 | 2GB | 60GB | 3TB @2Gbps | $89.90／月 | [ 查看香港 EB.MINI](https://www.dmit.io/aff.php?aff=12046) |
| 香港 EB | MICRO | 4 核 | 4GB | 80GB | 4TB @4Gbps | $129.90／月 | [ 查看香港 EB.MICRO](https://www.dmit.io/aff.php?aff=12046) |
| 東京 Pro | TINY | 1 核 | 1GB | 20GB | 500GB @1Gbps | $21.90／月 | [ 看東京 Pro 方案](https://www.dmit.io/aff.php?aff=12046) |

東京的 Tier 1 與洛杉磯、香港同價，T1.TINY 為 $6.90／月、T1.STARTER 為 $12.90／月。東京 Eyeball 系列曾被下架，要買之前先確認列表上還在不在。

## 三種常見情境，具體該點哪一台

**訪客九成在台灣的技術部落格。** 你的訪客不會經過中國大陸的網路，Pro 的價值幾乎為零。香港 T1.TINY（$6.90／月）或 T1.STARTER（$12.90／月）就夠，2GB 記憶體配上 LiteSpeed Cache 之類的快取外掛，撐幾千日訪客不成問題。要更好一點的線路品質，東京或香港的 Eyeball 是中間選項。

**有在經營 SEO、需要穩定 TTFB 的企業形象站。** 這一類通常外掛不少、還有表單與追蹤碼。香港 Pro.TINY 落在 $39.90／月，記憶體只有 1GB，老實說對外掛多的站偏緊；同價位帶更務實的做法是洛杉磯 Pro.STARTER（2 核 2GB、80GB SSD、$29.90／月），或是香港 EB.STARTER（2GB、$59.90／月）。差別在於你更在意「台灣訪客延遲」還是「中國大陸訪客延遲」。

**要跑 WooCommerce 或多站台。** 低於 4GB 記憶體會很痛苦，資料庫、Redis、PHP-FPM 三個一起搶記憶體。洛杉磯 EB.MINI（4 核 4GB、10TB 流量、$58.88／月）在這條預算線上配置合理；如果訪客主要在大陸，就換成洛杉磯 Pro.MINI 付線路錢。香港同級要 $129.90／月起，價差是買延遲。

## 買了 VPS 之後，WordPress 還需要做的六件事

1. **系統選 Ubuntu LTS 或 Debian，用 SSH Key 登入並關閉密碼登入。** WordPress 站被暴力破解，多半從 22 埠開始。
2. **裝 Nginx 或 OpenLiteSpeed + PHP 8.x + MariaDB。** 不想手動編譯就用現成的 LNMP 一鍵腳本，但版本要自己確認還在維護週期內。
3. **Let's Encrypt 的 SSL 要設自動續期。** 憑證過期是自架站最常見的「莫名全站紅字」來源。
4. **快取至少裝一層。** 記憶體只有 1GB 的機器，Redis 要克制，不然快取反而把資源吃光。
5. **備份要真的還原過一次。** 備份檔存在不等於救得回來，這是最容易被跳過、也最貴的一步。
6. **洛杉磯機房強烈建議接 CDN。** 靜態資源交給 CDN，延遲感受會拉近跟亞洲機房的差距。

## DMIT 的幾個實務細節

付款支援支付寶、PayPal、信用卡，並提供中文客服，主要走工單系統。對台灣與香港使用者來說，支付方式的門檻比很多只收信用卡的美系主機低。

退款政策寫得算清楚：**購買 3 天內且傳輸量不超過 30GB，可全額退款；30 天內可申請部分退款**，金額按「已用流量比例」與「剩餘時間比例」中較高者扣除。退到 DMIT 帳戶餘額不收手續費，退到原支付方式會被支付商收一筆手續費，其中支付寶因為退款時返還手續費，實務上不扣。3 天這個窗口，實質上就等於一段短暫試用期，可以拿去實測你所在 ISP 的實際路由。

要注意的是，被 (D)DoS 攻擊、以「網路不夠好」為由、IP 地區可用性問題這幾類情況不在退款範圍內；同一系列產品退過 3 次也不能再退。IP 部分，官方提供自助更換 IP 的功能，免費額度與條件依方案條款而定，遇到問題建議購買當天就反映。

流量用完不會直接停機，而是降速繼續跑，T1 系列尤其明顯（50Mbps 到 1Gbps 不等）。對 WordPress 來說這是個實用的安全網：假設某篇文章突然爆流量，網站會變慢，但不會變成 403。

比較現實的一點是庫存。洛杉磯 Pro 的熱門規格（MINI、MICRO）與部分香港、東京方案常缺貨，看到有貨就先確認好規格，別等到要下單才發現只剩最高階那檔。

## 常見問題

**1GB 記憶體跑得動 WordPress 嗎？** 跑得動，但條件是外掛精簡、快取有效、沒有 WooCommerce。外掛裝到二十個以上、又開了 Redis 與多層快取，1GB 會開始頻繁觸發 OOM。

**需要 cPanel 嗎？** 不需要。純跑 WordPress 用不到 cPanel，那筆授權費拿去升級記憶體更實際。

**該買月付還是年付？** 先用月付跑一到兩週，確認你的 ISP 到該機房的路由表現穩定，再轉年付。年付的單價確實低一截（例如 T1.WEE 年付 $36.90，換算下來比月付 TINY 便宜），但那是建立在「這台你確定要長期用」的前提上。

**為什麼香港比洛杉磯貴這麼多？** 香港機房與頻寬成本本來就高，加上 Pro 系列走的是中國電信 CN2 GIA，這種線路的頻寬單價不是一般國際 BGP 能比的。這也是為什麼如果你的訪客不在大陸，選香港 Pro 通常是最不划算的組合。

**可以中途升級方案嗎？** 官方支援工單申請升級，實際作法與價差計算依當期政策，建議直接問客服，別自己臆測。

**現在有優惠碼嗎？** 官方會不定期對特定產品線推年付折扣，結帳頁有優惠碼欄位可以驗證。與其盯著來路不明的折扣碼，更穩定的省錢方式是挑年付週期、並選你真正需要的線路——在 DMIT 這裡，選錯線路造成的價差通常比折扣碼大得多。

## 最後的選購原則

先量自己的需求，再對方案表。訪客在台灣就用 T1 或直接用 CDN 蓋掉地理距離；訪客在大陸才付 Pro 的錢；要跑商店就別在記憶體上省。

DMIT 的定位偏向「願意為線路品質付費」的那一群，入門價從 $6.90／月、$36.90／年起，硬體標示為 AMD EPYC 與企業級 SSD，實際值不值得，3 天退款窗口是你自己的驗證機會。先用測試 IP 與月付確認路由，再決定要不要長期綁定，這個順序不會出錯。
