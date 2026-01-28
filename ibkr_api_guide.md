# Interactive Brokers (IBKR) API 使用指南

## 概述

Interactive Brokers 是全球知名的在線券商，提供強大的 API 讓開發者進行程序化交易。

## 監管狀態

IBKR 是高度監管的券商，在多個司法管轄區都有許可：
- **美國**：SEC、FINRA、SIPC
- **英國**：FCA（金融行為監管局）
- **歐盟**：各國監管機構
- **澳洲**：ASIC
- **日本**：FSA
- **香港**：SFC
- **加拿大**：IIROC

## API 類型

### 1. IBKR API（原 IB API）
- **類型**：Socket 連接（基於 Java/C++/Python）
- **特點**：
  - 功能完整，支持所有 IBKR 功能
  - 實時市場數據
  - 訂單管理、帳戶信息
  - 低延遲
- **適合**：機構交易者、量化交易
- **官方文檔**：https://www.interactivebrokers.com/en/trading/ib-api.php

### 2. IBKR Pro API
- **類型**：基於雲端的 REST API
- **特點**：
  - 更易於集成
  - 支持多種編程語言
  - 適合現代 web 應用
- **適合**：初學者、個人投資者
- **官方文檔**：https://www.interactivebrokers.com/en/trading/ib-api-for-pro-traders.php

## 支持的市場

### 股票
- 美國：NYSE、NASDAQ
- 歐洲：倫敦、法蘭克福、巴黎等
- 亞洲：東京、香港、上海、深圳等
- 全球：100+ 個市場

### 期權
- 美式、歐式期權
- 支持期權策略

### 期貨
- 商品期貨
- 指數期貨
- 外匯期貨

### 外匯
- 主要貨幣對
- 24 小時交易

### 其他
- 債券
- 共同基金
- ETF
- 結構化產品

## 快速開始

### 1. 開通帳戶
1. 在 IBKR 官網開通帳戶
2. 啟用 API 交易權限
3. 下載 TWS（Trader Workstation）

### 2. 安裝 API
- 下載 IBKR API 軟件
- 配置 TWS 啟用 API 連接

### 3. 連接示例（Python）
```python
from ibapi.client import EClient
from ibapi.wrapper import EWrapper

class TestApp(EWrapper, EClient):
    def __init__(self):
        EClient.__init__(self, self)

app = TestApp()
app.connect("127.0.0.1", 7497, clientId=1)
app.run()
```

## 費用結構

### 佣金
- 股票：每股 $0.005 - $0.01
- 期權：每張 $0.65 - $1.25
- 期貨：每筆 $0.85 - $2.50

### 其他費用
- 市場數據：$1-15/月
- 平台使用費：可選（如使用 TWS 則免費）

## 風險管理

### 保證金要求
- IBKR 使用 TWS 保證金計算
- 實時保證金監控

### 風險控制
- 自動風險管理系統
- 可自定義止損和止盈訂單

## 優點

✅ 高度監管，資金安全
✅ 全球市場接入
✅ 低費率
✅ 強大的 API 功能
✅ 實時市場數據

## 缺點

❌ 存款要求較高（通常 $10,000+）
❌ API 學習曲線較陡
❌ TWS 軟件需要安裝

## 參考資源

- 官方文檔：https://www.interactivebrokers.com/en/trading/api-reference.php
- Python SDK：https://ib-insync.readthedocs.io/
- 社區論壇：https://forums.interactivebrokers.com/
- API 支持郵件：api@interactivebrokers.com

---

*文檔創建日期：2026-01-28*
