# 介面

## 介面列表

| 介面類型 | 請求方法 | 描述 |
| --- | --- | --- |
| 資產 | [POST /api_market/getBalance](#%E8%8E%B7%E5%8F%96%E4%BD%99%E9%A2%9D) | 獲取餘額 |
| 交易品種資訊 | [GET /api_market/getTokenPrecision](#%E6%89%80%E6%9C%89%E5%B8%81%E7%A7%8D%E7%B2%BE%E5%BA%A6) | 所有幣種精度 |
| 市場行情 | [GET /api_market/apiKline](#K%E7%BA%BF) | K線 |
| 市場行情 | [GET /api_market/getTradeLists](#%E6%89%80%E6%9C%89symbol24%E5%B0%8F%E6%97%B6%E8%A1%8C%E6%83%85) | 所有symbol24小時行情(請求需攜帶api_key) |
| 市場行情 | [GET /api_market/getLatestTradeByPair](#%E5%8D%95%E4%B8%AAsymbol%E6%9C%80%E6%96%B0%E6%88%90%E4%BA%A4%E8%AE%B0%E5%BD%95) | 單個symbol最新成交記錄 |
| 市場行情 | [GET /api_market/getDataOfTradesLatest](#%E6%89%B9%E9%87%8F%E8%8E%B7%E5%8F%96%E5%8D%95%E4%B8%AAsymbol%E6%9C%80%E8%BF%91%E6%88%90%E4%BA%A4%E8%AE%B0%E5%BD%95) | 批量獲取單個symbol最近成交記錄 |
| 市場行情 | [GET /api_market/market/depth](#%E5%8D%95%E4%B8%AAsymbol%E5%B8%82%E5%9C%BA%E6%B7%B1%E5%BA%A6%E8%A1%8C%E6%83%85) | 單個symbol市場深度行情 |
| 市場行情 | [GET /api_market/buyAndSellOnePrice](#%E5%8D%95%E4%B8%AAsymbol%E4%B9%B0%E4%B8%80%E5%8D%96%E4%B8%80) | 單個symbol買一賣一 |
| 市場行情 | [GET /api_market/getLatestPrice](#%E5%8D%95%E4%B8%AAsymbol%E7%89%8C%E4%BB%B7%E4%BF%A1%E6%81%AF) | 單個symbol牌價資訊 |
| 用戶訂單資訊 | [POST /api_market/placeOrder](#%E4%B8%8B%E5%8D%95) | 下單 |
| 用戶訂單資訊 | [POST /api_market/batchPlaceOrder](#%E6%89%B9%E9%87%8F%E4%B8%8B%E5%8D%95) | 批量下單 |
| 用戶訂單資訊 | [POST /api_market/getOrdersByOrderNo](#%E6%A0%B9%E6%8D%AE%E5%8D%95%E5%8F%B7%E6%89%B9%E9%87%8F%E6%9F%A5%E8%AF%A2%E8%AE%A2%E5%8D%95) | 根據單號批量查詢訂單 |
| 用戶訂單資訊 | [POST /api_market/cancelOrder](#%E5%8F%96%E6%B6%88%E8%AE%A2%E5%8D%95) | 取消訂單 |
| 用戶訂單資訊 | [POST /api_market/batchCancelOrder](#%E6%A0%B9%E6%8D%AE%E5%8D%95%E5%8F%B7%E6%89%B9%E9%87%8F%E5%8F%96%E6%B6%88%E8%AE%A2%E5%8D%95) | 根據單號批量取消訂單 |
| 用戶訂單資訊 | [POST /api_market/getOrderByOrderNo](#%E8%8E%B7%E5%8F%96%E6%9F%90%E4%B8%80%E8%AE%A2%E5%8D%95) | 獲取某一訂單 |
| 用戶訂單資訊 | [POST /api_market/getOrders](#%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E8%AE%A2%E5%8D%95%E5%88%97%E8%A1%A8) | 獲取用戶訂單列表 |
| 用戶訂單資訊 | [POST /api_market/getOrders](#%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E6%9C%AA%E6%88%90%E4%BA%A4%E8%AE%A2%E5%8D%95%E5%88%97%E8%A1%A8) | 獲取用戶未成交訂單列表 |
| 用戶訂單資訊 | [POST /api_market/getTrades](#%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E6%88%90%E4%BA%A4%E5%8D%95%E5%88%97%E8%A1%A8) | 獲取用戶成交單列表 |
| 用戶訂單資訊 | [POST /api_market/getTrades](#%E7%94%A8%E6%88%B7%E5%8D%95%E4%B8%AAsymbol%E6%89%B9%E9%87%8F%E6%88%90%E4%BA%A4%E8%AE%B0%E5%BD%95) | 用戶單個symbol批量成交記錄 |
| 充提幣 | [POST /api_market/searchDepositlList](#%E8%8E%B7%E5%8F%96%E5%85%85%E5%B8%81%E8%AE%B0%E5%BD%95) | 獲取充幣記錄 |
| 充提幣 | [POST /api_market/searchWithdrawlList](#%E8%8E%B7%E5%8F%96%E6%8F%90%E5%B8%81%E8%AE%B0%E5%BD%95) | 獲取提幣記錄 |

## 獲取餘額

### POST /api_market/getBalance

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~10000 |
| tokens | 是 | array | 幣種數組 |  | ["BTC","ETH"...] |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "count": 3,
        "data": [
            {
                "user_id": 1,
                "org_id": 12,
                "token": "BTC",
                "token_as": "BTC",
                "usable": "0",
                "locked": "0",
                "total": "0"
            },
            {
                "user_id": 1,
                "org_id": 12,
                "token": "ETH",
                "token_as": "ETH",
                "usable": "0",
                "locked": "0",
                "total": "0"
            }
        ]
    }
}

```

**data說明：**

```
        "data": [
            {
                "user_id": 用戶id,
                "org_id": 機構id,
                "token": 幣名,
                "token_as": 幣種別名（展示名稱）,
                "usable": 可用資產,
                "locked": 鎖定資產,
                "total": 總資產
            }
        ]

```

## 所有幣種精度

### GET /api_market/getTokenPrecision

**請求參數**

**回應參數**

```
{
    "code": 0,
    "msg": "Operational success",
    "data": {
        "BTC": {
            "calc_precision": 4,
            "biz_precision": 8,
            "phy_precision": 8,
            "order_amount_min": "0.01",
            "order_amount_max": "10000",
        },
        "ETH": {
            "calc_precision": 4,
            "biz_precision": 8,
            "phy_precision": 8,
            "order_amount_min": "0.01",
            "order_amount_max": "10000",
        },
        "USDT": {
            "calc_precision": 4,
            "biz_precision": 8,
            "phy_precision": 8,
            "order_amount_min": "0.01",
            "order_amount_max": "10000",
        },
    }
}

```

**data說明：**

```
    {
        "calc_precision": 計算精度,
        "phy_precision":  提幣數量精度,
        "biz_precision":  委託數量精度,
        "order_amount_min":  最小委託數量,
        "order_amount_max":  最大委託數量,
    }

```

## K線

### GET /api_market/apiKline

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| time_type | 是 | string | K線類型 |  | 1、5、10、15、30、60、240、1440、10080、43200 |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |
| limit | 是 | string | 數量 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "success",
    "data": [
        {
            "amount": "1",
            "c_price": "100",
            "o_price": "100",
            "min_price": "100",
            "max_price": "100",
            "volume": "0",
            "timestamp": 1535618520000
        },
        {
            "amount": "1",
            "c_price": "100",
            "o_price": "100",
            "min_price": "100",
            "max_price": "100",
            "volume": "0",
            "timestamp": 1535618580000
        }
    ]
}

```

**data說明**

```
    "data": [
        {
            "amount": 交易量,
            "c_price": 收盤價,
            "o_price": 開盤價,
            "min_price": 最低價,
            "max_price": 最高價,
            "volume": 成交額,
            "timestamp": 時間點
        }
    ]

```

## 所有symbol24小時行情

### GET /api_market/getTradeLists

**請求參數** 此介面需攜帶api_key

**回應參數**

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "main": {
            "USDT": [
                {
                    "id": 10,
                    "vol": "27337458.015767",
                    "market": "USDT",
                    "market_as": "USDT",
                    "token": "BTC",
                    "token_as": "BTC",
                    "amount": "3826.3038",
                    "max_price": "8002.4452",
                    "min_price": "5075.06",
                    "open_price": "6799",
                    "is_up": "-1",
                    "prev_price": "6634.66",
                    "p_precision": "4",
                    "n_precision": "4",
                    "currency": {
                        "CNY": "45768.321",
                        "KRW": "7447036.4739"
                    },
                    "latest_price": "6633.09",
                    "percent_change": "-0.1348463208"
                },
                {
                    "id": 11,
                    "vol": "607.3851",
                    "market": "USDT",
                    "market_as": "USDT",
                    "token": "ETH",
                    "token_as": "ETH",
                    "amount": "2.23",
                    "max_price": "272.37",
                    "min_price": "272.37",
                    "open_price": "272.37",
                    "is_up": "1",
                    "prev_price": "228.84",
                    "p_precision": "4",
                    "n_precision": "4",
                    "currency": {
                        "CNY": "1876.6293",
                        "KRW": "305349.349473"
                    },
                    "latest_price": "272.37",
                    "percent_change": "0.1902202412"
                }
            ],
            "ETH": [
                {
                    "id": 14,
                    "vol": "0",
                    "market": "ETH",
                    "market_as": "ETH",
                    "token": "QTUM",
                    "token_as": "QTUM",
                    "amount": "0",
                    "max_price": "0.0212",
                    "min_price": "0.0212",
                    "open_price": "0.0212",
                    "is_up": "-1",
                    "prev_price": "0.0222",
                    "p_precision": "8",
                    "n_precision": "4",
                    "currency": {
                        "CNY": "16.512424185",
                        "KRW": "2658.6213073839"
                    },
                    "latest_price": "0.0212",
                    "percent_change": "0"
                }
            ]
        },
        "hot": [
            {
                "id": 14,
                "vol": "0",
                "market": "ETH",
                "market_as": "ETH",
                "token": "QTUM",
                "token_as": "QTUM",
                "amount": "0",
                "max_price": "0.0212",
                "min_price": "0.0212",
                "open_price": "0.0212",
                "is_up": "-1",
                "prev_price": "0.0222",
                "p_precision": "8",
                "n_precision": "4",
                "currency": {
                        "CNY": "16.512424185",
                    "KRW": "2658.6213073839"
                },
                "latest_price": "0.0212",
                "percent_change": "0"
            },
            {
                "id": 10,
                "vol": "27337458.015767",
                "market": "USDT",
                "market_as": "USDT",
                "token": "BTC",
                "token_as": "BTC",
                "amount": "3826.3038",
                "max_price": "8002.4452",
                "min_price": "5075.06",
                "open_price": "6799",
                "is_up": "-1",
                "prev_price": "6634.66",
                "p_precision": "4",
                "n_precision": "4",
                "currency": {
                        "CNY": "45768.321",
                    "KRW": "7447036.4739"
                },
                "latest_price": "6633.09",
                "percent_change": "-0.1348463208"
            }
        ],
        "by_percent":[
            {
                "id": 11,
                "vol": "607.3851",
                "market": "USDT",
                "market_as": "USDT",
                "token": "ETH",
                "token_as": "ETH",
                "amount": "2.23",
                "max_price": "272.37",
                "min_price": "272.37",
                "open_price": "272.37",
                "is_up": "1",
                "prev_price": "228.84",
                "p_precision": "4",
                "n_precision": "4",
                "currency": {
                    "CNY": "1876.6293",
                    "KRW": "305349.349473"
                },
                "latest_price": "272.37",
                "percent_change": "0.1902202412"
            },
            {
                "id": 32,
                "vol": "0.5769332",
                "market": "ETH",
                "market_as": "ETH",
                "token": "ONT",
                "token_as": "ONT",
                "amount": "4",
                "max_price": "0.1442333",
                "min_price": "0.1442333",
                "open_price": "0.1442333",
                "is_up": "1",
                "prev_price": "0.1442",
                "p_precision": "8",
                "n_precision": "4",
                "currency": {
                    "CNY": "112.3415769435",
                    "KRW": "18087.8171987879"
                },
                "latest_price": "0.1442333",
                "percent_change": "0.0002309292"
            }
        ],
        "by_time": [
            {
                "id": 14,
                "vol": "0",
                "market": "ETH",
                "market_as": "ETH",
                "token": "QTUM",
                "token_as": "QTUM",
                "amount": "0",
                "max_price": "0.0212",
                "min_price": "0.0212",
                "open_price": "0.0212",
                "is_up": "-1",
                "prev_price": "0.0222",
                "p_precision": "8",
                "n_precision": "4",
                "currency": {
                        "CNY": "16.512424185",
                    "KRW": "2658.6213073839"
                },
                "latest_price": "0.0212",
                "percent_change": "0"
            },
            {
                "id": 10,
                "vol": "27337458.015767",
                "market": "USDT",
                "market_as": "USDT",
                "token": "BTC",
                "token_as": "BTC",
                "amount": "3826.3038",
                "max_price": "8002.4452",
                "min_price": "5075.06",
                "open_price": "6799",
                "is_up": "-1",
                "prev_price": "6634.66",
                "p_precision": "4",
                "n_precision": "4",
                "currency": {
                    "CNY": "45768.321",
                    "KRW": "7447036.4739"
                },
                "latest_price": "6633.09",
                "percent_change": "-0.1348463208"
            }
        ]
    }
}

```

**data說明**

```
{
    "code":0,
    "msg":"success",
    "data"{
        "main":{
            "USDT":[ 交易區
                {
                    "id": id,
                    "vol": 交易額,
                    "market": 市場,
                    "market_as": 市場展示名稱,
                    "token": 幣種,
                    "token_as": 幣種展示名稱,
                    "amount": 交易量,
                    "max_price": 最高價,
                    "min_price": 最低價,
                    "open_price": 開盤價,
                    "is_up": 是否漲跌 1漲 -1跌,
                    "prev_price": 上次價格,
                    "p_precision": 價格精度,
                    "n_precision": 數量精度,
                    "currency": { 發幣參考，
                        "CNY":人民幣，
                        "KRW":韓元
                    },
                    "latest_price": 最新價格,
                    "percent_change": 漲跌幅
                }
            ],
            "ETH":[
            ]
        },
        "hot":[],交易量最大的四個交易對
        "by_percent":[],漲跌幅最大的四個交易對
        "by_time":[],最新上線的交易對
    }
}

```

## 單個symbol最新成交記錄

### GET /api_market/getLatestTradeByPair

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |

**回應參數**

```
[
    {
        "created_at": "2018-08-31 11:26:10",
        "price": "1",
        "amount": "0",
        "volume": "0",
        "dominance": "2"
    },
    {
        "created_at": "2018-08-31 10:26:14",
        "price": "1",
        "amount": "1",
        "volume": "1",
        "dominance": "1"
    }
]

```

**data說明**

```
[
    {
        "created_at": 創建時間,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "dominance":主動成交方 1買方 2賣方
    }
]

```

## 批量獲取單個symbol最近成交記錄

### GET /api_market/getDataOfTradesLatest

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": [
        {
            "id": 1,
            "created_at": "2018-08-31 10:26:14",
            "price": "1",
            "amount": "1",
            "dominance": "1"
        },
        {
            "id": 2,
            "created_at": "2018-08-31 10:26:14",
            "price": "1",
            "amount": "1",
            "dominance": "1"
        }
    ]
}

```

**data說明**

```
    "data": [
      {
        "id": 成交id,
        "price": 成交價,
        "amount": 成交量,
        "dominance": 主動成交方向,
        "created_at": 成交時間
      }
   ]

```

## 單個symbol市場深度行情(停用)

### GET /api_market/market/depth

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "bids": [
            ["6595.25", "20"],
            ["6595.24", "2.73"],
            ["6595.14", "3.25"],
            ["6594.61", "3.34"],
        ],
        "asks": [
            ["7713.62", "0.23"],
            ["7712.74", "10.98"],
            ["7712.52", "1.81"],
            ["7712.45", "0.66"],
        ]
    }
}

```

**data說明**

```
{
        "bids": [
            [
                "2.8",   //價格
                "6.32"   //數量
            ],
            [
                "2.77",  //價格
                "6.72"   //數量
            ]
        ],
        "asks": [
            [
                "5.6",   //價格
                "2.3"    //數量
            ]
        ]
}

```

## 單個symbol買一賣一

### GET /api_market/buyAndSellOnePrice

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |

**回應參數**

```
{
    "buy": "0.02657781",
    "sell": "1.1998887"
}

```

**data說明**

```
{
    "buy": "0.02657781", //買的高價
    "sell": "1.1998887"  //賣的最低價
}

```

## 單個symbol牌價資訊

### GET /api_market/getLatestPrice

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "buy": {
            "orders": [{
                "price": "270.99",
                "exchange": {
                    "CNY": "6.9",
                    "KRW": "1122.71"
                },
                "fiat": "CNY",
                "percent_change": "",
                "amount": "2",
                "matching_amount": "2",
                "matched_amount": "0"
            }, {
                "price": "99",
                "exchange": {
                    "CNY": "6.9",
                    "KRW": "1122.71"
                },
                "fiat": "CNY",
                "percent_change": "",
                "amount": "1",
                "matching_amount": "1",
                "matched_amount": "0"
            }],
            "best_price": "270.99",
            "max_amount": "2"
        },
        "sell": {
            "orders": [],
            "best_price": "0",
            "max_amount": "0"
        }
    }
}

```

**data說明**

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "buy": { //買
            "orders": [{ //訂單列表
                "price": //價格
                "exchange": { // 兌換為法幣
                    "CNY" //人民幣
                    "KRW" //韓元
                },
                "fiat" //法幣幣種
                "percent_change": //漲跌幅
                "amount": //委託量
                "matching_amount": //未成交數量
                "matched_amount":  //已成交數量
            }],
            "best_price": //買入的最高價
            "max_amount": //委託的最大量
        },
        "sell": { //賣
            "orders": [], //訂單列表
            "best_price": //賣出的最低價
            "max_amount": //委託的最大量
        }
    }
}

```

## 下單

### POST /api_market/placeOrder

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| market_type | 是 | string | 市場類型 |  | 1 |
| market | 是 | string | 市場 |  |  |
| token | 是 | string | 幣名 |  |  |
| type | 是 | string | 買/賣 |  | 1買 2賣 |
| price | 是 | string | 價格 |  |  |
| amount | 是 | string | 數量 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "id": 1,
        "status": 1,
        "order_no": "2018090313134038386500017289",
        "type": "1",
        "market_type": "1",
        "account_id": 6,
        "org_id": 12,
        "user_id": 1,
        "market": "BTC",
        "token": "ETH",
        "price": "0.05",
        "amount": "1",
        "volume": "0.05",
        "matched_amount": "0",
        "matched_volume": "0",
        "avg_price":"0",
        "created_at": "2018-09-03 13:13:40",
        "updated_at": "2018-09-03 13:13:40"
    }
}

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "token": 幣名,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 批量下單

### POST /api_market/batchPlaceOrder

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| data | 是 | array | 訂單數組 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": [
        {
            "id": 1,
            "status": 1,
            "type": 1,
            "market_type": 1,
            "order_no": "2018090313134038386500017289",
            "account_id": 6,
            "user_id": 1,
            "org_id": 12,
            "market": "BTC",
            "token": "ETH",
            "price": "0.05",
            "amount": "1",
            "volume": "0.05",
            "matched_amount": "0",
            "matched_volume": "0",
            "avg_price":"0",
            "created_at": "2018-09-03 13:13:40",
            "updated_at": "2018-09-03 13:13:40"
        },
        {
            "id": 2,
            "status": 1,
            "type": 1,
            "market_type": 1,
            "order_no": "2018090313134038386500017299",
            "account_id": 6,
            "user_id": 1,
            "org_id": 12,
            "market": "BTC",
            "token": "ETH",
            "price": "0.05",
            "amount": "1",
            "volume": "0.05",
            "matched_amount": "0",
            "matched_volume": "0",
            "avg_price":"0",
            "created_at": "2018-09-03 13:13:42",
            "updated_at": "2018-09-03 13:13:42"
        }
    ]
}

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "token": 幣名,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 根據單號批量查詢訂單

### POST /api_market/getOrdersByOrderNo

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| arr_order_no | 是 | array | 訂單單號數組 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": [
        {
            "id": 1,
            "status": 1,
            "type": 1,
            "market_type": 1,
            "order_no": "2018090313134038386500017289",
            "account_id": 6,
            "user_id": 1,
            "org_id": 12,
            "market": "BTC",
            "market_as": "BTC",
            "token": "ETH",
            "token_as": "ETH",
            "price": "0.05",
            "amount": "1",
            "volume": "0.05",
            "matched_amount": "0",
            "matched_volume": "0",
            "avg_price":"0",
            "created_at": "2018-09-03 13:13:40",
            "updated_at": "2018-09-03 13:13:40",
            "unmatched_amount": "1"
        },
        {
            "id": 2,
            "status": 1,
            "type": 1,
            "market_type": 1,
            "order_no": "2018090313134038386500017299",
            "account_id": 6,
            "user_id": 1,
            "org_id": 12,
            "market": "BTC",
            "market_as": "BTC",
            "token": "ETH",
            "token_as": "ETH",
            "price": "0.05",
            "amount": "1",
            "volume": "0.05",
            "matched_amount": "0",
            "matched_volume": "0",
            "avg_price":"0",
            "created_at": "2018-09-03 13:13:42",
            "updated_at": "2018-09-03 13:13:42",
            "unmatched_amount": "1"
        }
    ]

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "market_as": 市場別名（展示名稱）,
        "token": 幣名,
        "token_as": 幣種別名（展示名稱）,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "unmatched_amount":未撮合交易幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 取消訂單

### POST /api_market/cancelOrder

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| arr_order_no | 是 | array | 訂單單號數組 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": null
}

```

## 根據單號批量取消訂單

### POST /api_market/batchCancelOrder

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| arr_order_no | 是 | array | 訂單單號數組 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful"
}

```

## 獲取某一訂單

### POST /api_market/getOrderByOrderNo

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| order_no | 是 | string | 訂單單號 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "id": 1,
        "status": 1,
        "order_no": "2018090313134038386500017289",
        "type": "1",
        "market_type": "1",
        "account_id": 6,
        "org_id": 12,
        "user_id": 1,
        "market": "BTC",
        "market_as": "BTC",
        "token": "ETH",
        "token_as": "ETH",
        "price": "0.05",
        "amount": "1",
        "volume": "0.05",
        "matched_amount": "0",
        "matched_volume": "0",
        "avg_price":"0",
        "created_at": "2018-09-03 13:13:40",
        "updated_at": "2018-09-03 13:13:40"
        "unmatched_amount":"0"
    }
}

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "market_as": 市場別名（展示名稱）,
        "token": 幣名,
        "token_as": 幣種別名（展示名稱）,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "unmatched_amount":未撮合交易幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 獲取用戶訂單列表

### POST /api_market/getOrders

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| type | 否 | string | 類型 |  | 1買 2賣 |
| market | 否 | string | 市場 |  |  |
| token | 否 | string | 幣名 |  |  |
| status | 否 | array | 狀態,格式：[0,1,2,3] |  | 0取消 1已創建 2撮合中 3已完成 |
| begin_time | 否 | string | 開始時間， 例2018-08-20 00:00:00； 必須與end_time結合使用 |  |  |
| end_time | 否 | string | 結束時間， 例2018-08-21 23:59:59；必須與start_time結合使用 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "count": 10,
        "data": [
            {
                "id": 1,
                "status": 1,
                "type": 1,
                "market_type": 1,
                "order_no": "2018090313134038386500017289",
                "account_id": 6,
                "user_id": 1,
                "org_id": 12,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "0.05",
                "amount": "1",
                "volume": "0.05",
                "matched_amount": "0",
                "matched_volume": "0",
                "avg_price":"0",
                "created_at": "2018-09-03 13:13:40",
                "updated_at": "2018-09-03 13:13:40",
                "unmatched_amount": "1"
            },
            {
                "id": 2,
                "status": 1,
                "type": 1,
                "market_type": 1,
                "order_no": "2018090313134038386500017299",
                "account_id": 6,
                "user_id": 1,
                "org_id": 12,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "0.05",
                "amount": "1",
                "volume": "0.05",
                "matched_amount": "0",
                "matched_volume": "0",
                "avg_price":"0",
                "created_at": "2018-09-03 13:13:42",
                "updated_at": "2018-09-03 13:13:42",
                "unmatched_amount": "1"
            }
        ]
    }
}

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "market_as": 市場別名（展示名稱）,
        "token": 幣名,
        "token_as": 幣種別名（展示名稱）,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "unmatched_amount":未撮合交易幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 獲取用戶未成交訂單列表

### POST /api_market/getOrders

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| status | 否 | array | 狀態(1未撮合 2撮合中) |  | [1,2] |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "count": 10,
        "data": [
            {
                "id": 1,
                "status": 1,
                "type": 1,
                "market_type": 1,
                "order_no": "2018090313134038386500017289",
                "account_id": 6,
                "user_id": 1,
                "org_id": 12,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "0.05",
                "amount": "1",
                "volume": "0.05",
                "matched_amount": "0",
                "matched_volume": "0",
                "avg_price":"0",
                "created_at": "2018-09-03 13:13:40",
                "updated_at": "2018-09-03 13:13:40",
                "unmatched_amount": "1"
            },
            {
                "id": 2,
                "status": 1,
                "type": 1,
                "market_type": 1,
                "order_no": "2018090313134038386500017299",
                "account_id": 6,
                "user_id": 1,
                "org_id": 12,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "0.05",
                "amount": "1",
                "volume": "0.05",
                "matched_amount": "0",
                "matched_volume": "0",
                "avg_price":"0",
                "created_at": "2018-09-03 13:13:42",
                "updated_at": "2018-09-03 13:13:42",
                "unmatched_amount": "1"
            }
        ]
    }
}

```

**data說明**

```
    "data": {
        "id": 訂單id,
        "status": 狀態 0已取消 1已創建 2撮合中 3已完成,
        "order_no": 訂單單號,
        "type": 類型 1買 2賣,
        "market_type": 市場類型 現階段值為1,
        "account_id_from": 付款帳號id',
        "account_id_to": 收款帳號id',
        "org_id": 機構id,
        "user_id": 用戶id,
        "market": 市場,
        "market_as": 市場別名（展示名稱）,
        "token": 幣名,
        "token_as": 幣種別名（展示名稱）,
        "price": 價格,
        "amount": 交易幣數額,
        "volume": 市場幣數額,
        "matched_amount": 已撮合交易幣數額,
        "matched_volume": 已撮合市場幣數額,
        "unmatched_amount":未撮合交易幣數額,
        "avg_price":已撮合部分平均單價,
        "created_at": 創建時間,
        "updated_at": 更新時間
    }

```

## 獲取用戶成交單列表

### POST /api_market/getTrades

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| type | 否 | string | 類型 |  | 1買 2賣 |
| market | 否 | string | 市場 |  |  |
| token | 否 | string | 幣名 |  |  |
| begin_time | 否 | string | 開始時間， 例2018-08-20 17:59:33； 必須與end_time結合使用 |  |  |
| end_time | 否 | string | 結束時間， 例2018-08-31 17:59:33； 必須與begin_time結合使用 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "count": 10,
        "data": [
            {
                "id": 1,
                "trade_no": "2243534656575453445453343423",
                "buy_order_id": 1,
                "buy_order_no": "2243534656575453445453343465",
                "sell_order_id": 1,
                "sell_order_no": "12135647586799657463241324",
                "dominance": 1,
                "buyer_user_id": 1,
                "seller_user_id": 2,
                "org_id": 12,
                "trade_strategy": 1,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "10.00000000",
                "amount": "1.00000000",
                "volume": "1.00000000",
                "created_at": "1970-01-01 08:00:01",
                "updated_at": "2018-08-29 10:19:12"
            },
            {
                "id": 2,
                "trade_no": "2243534656575453445453345523",
                "buy_order_id": 1,
                "buy_order_no": "2243534656575453445453343472",
                "sell_order_id": 1,
                "sell_order_no": "12135647586799657463241367",
                "dominance": 1,
                "buyer_user_id": 1,
                "seller_user_id": 2,
                "org_id": 12,
                "trade_strategy": 1,
                "market": "BTC",
                "market_as": "BTC",
                "token": "ETH",
                "token_as": "ETH",
                "price": "10.00000000",
                "amount": "1.00000000",
                "volume": "1.00000000",
                "created_at": "1970-01-01 08:00:01",
                "updated_at": "2018-08-29 10:19:12"
            }
        ]
    }
}

```

**data說明**

```
        "data": {
            "id": 1,
            "trade_no": 成交單號,
            "buy_order_id": 買入的訂單id,
            "buy_order_no": 買入的訂單單號,
            "sell_order_id": 賣出的訂單id,
            "sell_order_no": 賣出的訂單單號,
            "dominance": 主動成交方,
            "buyer_user_id": 買入的用戶id,
            "seller_user_id": 賣出的用戶id,
            "org_id": 機構id,
            "trade_strategy": 交易類型 1限價交易,
            "market": 市場,
            "market_as": 市場別名（展示名稱）,
            "token": 幣名,
            "token_as": 幣種別名（展示名稱）,
            "price": 價格,
            "amount": 交易幣數額,
            "volume": 市場幣數額,
            "created_at": 創建時間,
            "updated_at": 更新時間
        }

```

## 用戶單個symbol批量成交記錄

### POST /api_market/getTrades

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| market | 否 | string | 市場 |  |  |
| token | 否 | string | 幣名 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "successful",
    "data": {
        "count": 10,
        "data": [
            {
                "id": 1,
                "trade_no": "2243534656575453445453343423",
                "buy_order_id": 1,
                "buy_order_no": "2243534656575453445453343465",
                "sell_order_id": 1,
                "sell_order_no": "12135647586799657463241324",
                "dominance": 1,
                "buyer_user_id": 1,
                "seller_user_id": 2,
                "org_id": 12,
                "trade_strategy": 1,
                "market": "ETH",
                "market_as": "ETH",
                "token": "BTC",
                "token_as": "BTC",
                "price": "10.00000000",
                "amount": "1.00000000",
                "volume": "1.00000000",
                "created_at": "1970-01-01 08:00:01",
                "updated_at": "2018-08-29 10:19:12"
            },
            {
                "id": 2,
                "trade_no": "2243534656575453445453345523",
                "buy_order_id": 1,
                "buy_order_no": "2243534656575453445453343472",
                "sell_order_id": 1,
                "sell_order_no": "12135647586799657463241367",
                "dominance": 1,
                "buyer_user_id": 1,
                "seller_user_id": 2,
                "org_id": 12,
                "trade_strategy": 1,
                "market": "ETH",
                "market_as": "ETH",
                "token": "BTC",
                "token_as": "BTC",
                "price": "10.00000000",
                "amount": "1.00000000",
                "volume": "1.00000000",
                "created_at": "1970-01-01 08:00:01",
                "updated_at": "2018-08-29 10:19:12"
            }
        ]
    }
}

```

**data說明**

```
        "data": {
            "id": 1,
            "trade_no": 成交單號,
            "buy_order_id": 買入的訂單id,
            "buy_order_no": 買入的訂單單號,
            "sell_order_id": 賣出的訂單id,
            "sell_order_no": 賣出的訂單單號,
            "dominance": 主動成交方,
            "buyer_user_id": 買入的用戶id,
            "seller_user_id": 賣出的用戶id,
            "org_id": 機構id,
            "trade_strategy": 交易類型 1限價交易,
            "market": 市場,
            "market": 市場別名（展示名稱）,
            "token": 幣名,
            "token_as": 幣種名稱（展示名稱）,
            "price": 價格,
            "amount": 交易幣數額,
            "volume": 市場幣數額,
            "created_at": 創建時間,
            "updated_at": 更新時間
        }

```

## 獲取充幣記錄

### POST /api_market/searchDepositList

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| token | 是 | string | 幣名，可為空 |  |  |
| begin_time | 是 | string | 開始時間， 例2018-08-20 17:59:33，可為空；必須與end_time結合使用 |  |  |
| end_time | 是 | string | 結束時間， 例2018-08-31 17:59:33，可為空；必須與start_time結合使用 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "ok",
    "data": {
        "data": [
            {
                "id": 1,
                "user_id": 1,
                "org_id": 12,
                "account_id": 1,
                "token": "BTC",
                "token_as": "BTC",
                "amount": "1",
                "blockchain_tx_id": "ardtyuijuytredsasdfg",
                "deposit_no": "123456789765432133453",
                "address": "aSDFGUIYTREWAaertyrewasSDFGHJK",
                "confirm_count": 0,
                "status": 1,
                "created_at": "2018-09-03 17:23:20",
                "updated_at": "2018-09-03 17:24:24"
            },
            {
                "id": 2,
                "user_id": 1,
                "org_id": 12,
                "account_id": 1,
                "token": "BTC",
                "token_as": "BTC",
                "amount": "2",
                "blockchain_tx_id": "Awedtyuiuyfgdsa",
                "deposit_no": "345678985432132446577",
                "address": "asertyuiouytredasdrtyuiuytfdssasdfgh",
                "confirm_count": 12,
                "status": 5,
                "created_at": "2018-09-03 17:24:18",
                "updated_at": "2018-09-03 17:24:18"
            }
        ],
        "count": 2
    }

```

**data說明：**

```
        "data": {
            "id": 充幣單id,
            "user_id": 用戶,
            "org_id": 機構id,
            "account_id": 帳號id,
            "token": 幣名,
            "token_as": 幣種別名（顯示名稱）,
            "amount": 數量,
            "blockchain_tx_id": txid,
            "deposit_no": 充幣單號,
            "address": 充幣地址,
            "confirm_count": 確認數,
            "status": 狀態 1已創建 5已完成,
            "created_at": 創建時間,
            "updated_at": 更新時間
        }

```

## 獲取提幣記錄

### POST /api_market/searchWithdrawalList

**請求參數**

| 參數名稱 | 是否必須 | 數據類型 | 描述 | 默認值 | 取值範圍 |
| --- | --- | --- | --- | --- | --- |
| page | 是 | string | 頁碼 |  | 1~10000 |
| size | 是 | string | 每頁顯示數量 |  | 1~100 |
| token | 是 | string | 幣名，可為空 |  |  |
| begin_time | 是 | string | 開始時間， 例2018-08-20 17:59:33，可為空；必須與end_time結合使用 |  |  |
| end_time | 是 | string | 結束時間， 例2018-08-31 17:59:33，可為空；必須與start_time結合使用 |  |  |

**回應參數**

```
{
    "code": 0,
    "msg": "ok",
    "data": {
        "data": [
            {
                "id": 1,
                "user_id": 1,
                "org_id": 12,
                "account_id": 6,
                "fee_account_id": 3,
                "token": "BTC",
                "token_as": "BTC",
                "fee_token": "BTC",
                "protocol": 2,
                "amount": "",
                "apply_amount": "1",
                "blockchain_tx_id": null,
                "network_fee": "0.01",
                "withdrawal_no": "2018090317160306293300011976",
                "address_to": "1QT6UzFLZHtQKhWqUEXJgPWY1j5QevxfRk",
                "address_from": "ertyuiytrewrtyui987654ewsdftyu876t5rdsf1s",
                "fee_address": "ertyuiytrewrtyui987654ewsdftyu876t5rdsf1s",
                "reason": null,
                "confirm_count": 0,
                "status": 1,
                "created_at": "2018-09-03 17:16:03",
                "updated_at": "2018-09-03 17:16:03"
            }
        ],
        "count": 1
    }

```

**data說明：**

```
        "data": {
            "id": 提幣單id,
            "user_id": 用戶,
            "org_id": 機構id,
            "account_id": 帳號id,
            "fee_account_id": 手續費帳號id,
            "token": 幣名,
            "token_as": 幣種別名（展示名稱）,
            "fee_token": 網路費幣名,
            "protocol": 協議,
            "amount": 實際到賬數量,
            "apply_amount": 申請數量,
            "blockchain_tx_id": txid,
            "network_fee": 網路費,
            "withdrawal_no": 提幣單號,
            "address_to": 收款地址,
            "address_from": 付款地址,
            "fee_address": 手續費地址,
            "reason": 審核原因,
            "confirm_count": 確認數,
            "status": 狀態 0未審核 1已審核 2錢包已拉取 3已產生礦工費 4已產生第一塊 5已完成 6審核未通過 7取消,
            "created_at": 創建時間,
            "updated_at": 更新時間
        }

```
