# 簽名

## 生成簽名

按照ASCII碼的順序對參數名進行排序，轉化為json字串，使用私鑰簽名，得到簽名計算結果進行 Base64編碼，然後進行url編碼。以查詢資產餘額介面為例進行說明

請求參數：

```
page=1
size=10
api_key=eb4f25dd532c14cee5e9b0301c8d4671

```

按照ASCII碼的順序對參數進行排序：

```
api_key=eb4f25dd532c14cee5e9b0301c8d4671
page=1
size=10

```

轉化為json字串：

```
{"api_key":"eb4f25dd532c14cee5e9b0301c8d4671","page":"1","size":"10"}

```

計算簽名，將參數字串、私鑰傳入加密函數，用sha1演算法生成簽名，計算結果並進行Base64編碼：

```
c6jVyjdQ+KX5oDZGDOr0phH0JZPCZ4lgxva7iwPr2J9cHsCVNhJEmnUzHIYIUlemzSreXzl8Xt39mkQYPaH/Tt8eLqZf8QlUPIigy3MlKzq/BTDzXkJc4vna9ltT42W6ePwNi9q3Otm6FK6gMhiXqWwwUwa7OciHjYYehEomzoo=

```

提示！私鑰是在您申請API時與api_key一起返回的，這裏使用的私鑰為：

```
-----BEGIN PRIVATE KEY-----
MIICdwIBADANBgkqhkiG9w0BAQEFAASCAmEwggJdAgEAAoGBALSQaafkE4wNY21T
+B2sCydP2FwkTQ6xi+bWLMVeF9bhFKyAZndmwxGgEc9bR6/rur5dAblka7OKpw3n
J27p3b5Ig/kd+dOSj4SfMp9pt96nHWud2KNZdAKUH4ybhg51D8TM0AXL474Gh8Cc
PrRvZspMdnlPM17YyUd6VjKQJs55AgMBAAECgYBF7mBdO8IuTckiQJEpvMYdFZlw
JkcJ182dO3nffs+w0z+Uh64ntE78dogvTOT4x01uCMtwJ+pmgN6uTcZB+KV+NEEC
7298kRZyclUZP4IDyc8qW95ljEHIJnDYwOzLop/IAY3PYwYT3ATJe8ceJ7nan32S
howHKNV+8abiD2yt4QJBANh/II1cF8wtSwVgUxaiKchZwz71GPIMxENRwF+Pgzpf
p61FIw8+If8sR1X036HgyY1+fmuakcqqjg68eF19SC0CQQDVgtOtx8BT9YtPEchv
dChqduHZi7f3IkrMuq7dzkZ9XI5QUdnAhnm8WiW8z8ruKUo32yyxJEWIUGOy6NLi
kqL9AkEAwGvVee7Vc/L5z/B6SQ6exmUJxUZBArnYIuFhc03x3Asy1C0z6RNXUh5/
1OVNcuqBGdLI+Eistg37LxvSe32jjQJAEWnPG9A7xl0zVGqN31Eo7q3tc5GqmlRI
p3PeSSbGpvjCfph+Wu5cxVjQ1RpZYZ0qeW29smDT7u8ngnLsqB/vfQJBAJwsJYVC
8V0D8waVTeDS0zgVcmKtjqHOtuJ3VuFivuSX0BZQALQIq5UlwUhIHwUKimEhffHc
84m43hIAVLHj7eM=
-----END PRIVATE KEY-----

```

對Base64編碼後的結果進行URL編碼：

```
c6jVyjdQ%2BKX5oDZGDOr0phH0JZPCZ4lgxva7iwPr2J9cHsCVNhJEmnUzHIYIUlemzSreXzl8Xt39mkQYPaH%2FTt8eLqZf8QlUPIigy3MlKzq%2FBTDzXkJc4vna9ltT42W6ePwNi9q3Otm6FK6gMhiXqWwwUwa7OciHjYYehEomzoo%3D

```

最終，發送到伺服器的 API 請求參數應該為：

```
page=1
size=10
api_key=eb4f25dd532c14cee5e9b0301c8d4671
sign=c6jVyjdQ%2BKX5oDZGDOr0phH0JZPCZ4lgxva7iwPr2J9cHsCVNhJEmnUzHIYIUlemzSreXzl8Xt39mkQYPaH%2FTt8eLqZf8QlUPIigy3MlKzq%2FBTDzXkJc4vna9ltT42W6ePwNi9q3Otm6FK6gMhiXqWwwUwa7OciHjYYehEomzoo%3D

```

**sign生成代碼示例：**

```
<!--php代碼-->

    //請求參數數組
    $params = [
        'page' => '1',
        'size' => '10',
        'api_key' => 'eb4f25dd532c14cee5e9b0301c8d4671'
    ];

    //按照鍵名對關聯數組進行昇冪排序，排序規則依據ASCII碼
    ksort($params);

    //參數轉為json格式字串
    $str = json_encode($params);

    //獲取私鑰字串
    $key = file_get_contents('./private_key.pem');

    //解析私鑰供其他函數使用
    $private_key = openssl_pkey_get_private($key);

    //生成簽名
    openssl_sign($str, $sign, $private_key, OPENSSL_ALGO_SHA1);

    //從記憶體中釋放密鑰資源
    openssl_free_key($private_key);

    //簽名進行base64編碼
    $sign = base64_encode($sign);

    //簽名進行urlencode編碼
    $sign = urlencode($sign);

    //將簽名加入參數數組
    $params['sign'] = $sign;

```

```
#python代碼

# -*- coding: utf-8 -*-

    import base64
    import collections
    import json
    import requests
    from requests import Session

    #需要先安裝：pip install pyOpenSSL
    from OpenSSL import crypto

    try:
        import urllib.parse as _urlencode    # Python 3
    except ImportError:
        import urllib as _urlencode          # Python 2

    params = {
        'page' : '1',
        'size' : '10',
        'api_key' : 'eb4f25dd532c14cee5e9b0301c8d4671',
        }

    secret = '''-----BEGIN PRIVATE KEY-----
    MIICdwIBADANBgkqhkiG9w0BAQEFAASCAmEwggJdAgEAAoGBALSQaafkE4wNY21T
    +B2sCydP2FwkTQ6xi+bWLMVeF9bhFKyAZndmwxGgEc9bR6/rur5dAblka7OKpw3n
    J27p3b5Ig/kd+dOSj4SfMp9pt96nHWud2KNZdAKUH4ybhg51D8TM0AXL474Gh8Cc
    PrRvZspMdnlPM17YyUd6VjKQJs55AgMBAAECgYBF7mBdO8IuTckiQJEpvMYdFZlw
    JkcJ182dO3nffs+w0z+Uh64ntE78dogvTOT4x01uCMtwJ+pmgN6uTcZB+KV+NEEC
    7298kRZyclUZP4IDyc8qW95ljEHIJnDYwOzLop/IAY3PYwYT3ATJe8ceJ7nan32S
    howHKNV+8abiD2yt4QJBANh/II1cF8wtSwVgUxaiKchZwz71GPIMxENRwF+Pgzpf
    p61FIw8+If8sR1X036HgyY1+fmuakcqqjg68eF19SC0CQQDVgtOtx8BT9YtPEchv
    dChqduHZi7f3IkrMuq7dzkZ9XI5QUdnAhnm8WiW8z8ruKUo32yyxJEWIUGOy6NLi
    kqL9AkEAwGvVee7Vc/L5z/B6SQ6exmUJxUZBArnYIuFhc03x3Asy1C0z6RNXUh5/
    1OVNcuqBGdLI+Eistg37LxvSe32jjQJAEWnPG9A7xl0zVGqN31Eo7q3tc5GqmlRI
    p3PeSSbGpvjCfph+Wu5cxVjQ1RpZYZ0qeW29smDT7u8ngnLsqB/vfQJBAJwsJYVC
    8V0D8waVTeDS0zgVcmKtjqHOtuJ3VuFivuSX0BZQALQIq5UlwUhIHwUKimEhffHc
    84m43hIAVLHj7eM=
    -----END PRIVATE KEY-----'''

    query = collections.OrderedDict(sorted(params.items(), key=lambda t: t[0]))
    json_str = json.dumps(query, separators=(',', ':'))
    key = crypto.load_privatekey(crypto.FILETYPE_PEM, secret)
    signature_base64 = base64.b64encode(crypto.sign(key, bytes(json_str, encoding = "utf8"), 'RSA-SHA1'))
    signature_str_tmp = str(signature_base64, encoding='utf-8')
    query['sign'] = _urlencode.quote(signature_str_tmp, safe="~()*!.'")
    body = json.dumps(query, separators=(',', ':'))
    print (body)
    print ()
    #{"api_key":"eb4f25dd532c14cee5e9b0301c8d4671","page":"1","size":"10","sign":"c6jVyjdQ%2BKX5oDZGDOr0phH0JZPCZ4lgxva7iwPr2J9cHsCVNhJEmnUzHIYIUlemzSreXzl8Xt39mkQYPaH%2FTt8eLqZf8QlUPIigy3MlKzq%2FBTDzXkJc4vna9ltT42W6ePwNi9q3Otm6FK6gMhiXqWwwUwa7OciHjYYehEomzoo%3D"}

    url = 'https://api.ebx.kz/api_market/getBalance'
    headers = {
        'Content-Type': 'application/json',
    }

    r = requests.post(url, headers=headers, data=body)

    print (r)
    #<Response [200]>

    print (r.text)
    #{"code":0,"msg":"\u64cd\u4f5c\u6210\u529f","data":{"count":5,"data":[{"user_id":352,"org_id":9,"token":"EOS","usable":"0","locked":"0","total":"0","token_as":"EOS"},{"user_id":352,"org_id":9,"token":"ETH","usable":"0","locked":"0","total":"0","token_as":"ETH"},{"user_id":352,"org_id":9,"token":"ONT","usable":"0","locked":"0","total":"0","token_as":"ONT"},{"user_id":352,"org_id":9,"token":"QTUM","usable":"0","locked":"0","total":"0","token_as":"QTUM"},{"user_id":352,"org_id":9,"token":"USDT","usable":"162449.02927762","locked":"2615.345","total":"165064.37427762","token_as":"USDT"}]}}

```

```
//NodeJs代碼
var http = require('http');
var fs = require('fs');
var crypto = require('crypto');
var urlencode = require('urlencode');
var qs = require('querystring');

const privateKey = fs.readFileSync('./private_key.pem').toString();

var params = {
    api_key:'eb4f25dd532c14cee5e9b0301c8d4671',
    page:'1',
    size:'10'
}

var options = {
    hostname: 'api.ebx.kz',
    path: '/api_market/getBalance',
    method: 'POST',
    headers: {
        'Content-Type':'application/json',
    }
};

var req = http.request(options, function (res) {
    console.log('STATUS: ' + res.statusCode);
    //console.log('HEADERS: ' + JSON.stringify(res.headers));
    res.setEncoding('utf8');
    res.on('data', function (chunk) {
        console.log('BODY: ' + chunk);
    });
});

req.on('error', function (e) {
    console.log('problem with request: ' + e.message);
});

req.write(qs.stringify(sign(params)));

req.end();

function sign(data) {
    data = objKeySort(data);
    var sign = crypto.createSign('sha1');
    sign.update(JSON.stringify(data));
    var sig = sign.sign(privateKey, 'base64');
    sigData =  urlencode(sig);
    data.sign = sigData;
    return data;
}

function objKeySort(arys) {
    var newkey = Object.keys(arys).sort();
    var newObj = {};
    for(var i = 0; i < newkey.length; i++) {
        newObj[newkey[i]] = arys[newkey[i]];
    }
    return newObj;
}

```
