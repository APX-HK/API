# 注意事項

*   如請求返回403狀態碼，請在header中設置User-Agent為：User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/39.0.2171.71 Safari/537.36。
*   文檔中所有介面參數中出現的'symbol'，需使用交易對替換，symbol 規則： 基礎幣種+計價幣種。如BTC/USD，symbol為BTC_USD。
*   文檔中所提及的market與token，值分別為交易區、交易幣種。如BTC/USD，則market值為USD，token值為BTC。
*   請求需page、size參數的介面，返回值中包含 count 字段，其值為符合條件的所有數據條目數，並不代表本次返回數據條目數。
