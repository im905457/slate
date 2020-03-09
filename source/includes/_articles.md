# Articles

## Get all articles of a issue

> API returns JSON structured like this:

```json
[
  {
    "id": "fc10d875-7339-4e3b-a690-e95870d27607",
    "article_id": "fc10d875-7339-4e3b-a690-e95870d27607",
    "title": "vogue diary",
    "intro": "金豬年已經到了尾聲，錢鼠已經迫不及待出來宣告新氣象，Tory Burch為即將來到的農曆鼠年推出討喜又帶有貴氣的錢鼠-Rita(麗塔)與你一同慶新年，各式精緻商品都能發現她的迷人身。Rita穿著優雅的軟呢外套，領口搭配祖母綠的皮革緄邊，胸口縫製金色雙T Logo 珍珠母貝鈕釦，左手提著迷你小包，右邊口袋還放著她最愛的起士，擬人化的造型讓人莞爾一笑。",
    "sequence": 54,
    "author": "",
    "plan_type": 1,
    "is_highlight": false,
    "page_number": 206,
    "end_page": 207,
    "has_fit_reading": false,
    "has_audio": false,
    "has_video": false,
    "has_pdf": true,
    "main_image_version": 1578410912,
    "text_version": 1578410912,
    "issue_id": "5e14a2c0aa68d"
  }
]
```

This endpoint retrieves all articles of a issue.

### HTTP Request

`GET /issues/{issue_id}/articles`

## Get a specific article

> API returns JSON structured like this:

```json
{
  "id": "fc10d875-7339-4e3b-a690-e95870d27607",
  "article_id": "fc10d875-7339-4e3b-a690-e95870d27607",
  "title": "vogue diary",
  "intro": "金豬年已經到了尾聲，錢鼠已經迫不及待出來宣告新氣象，Tory Burch為即將來到的農曆鼠年推出討喜又帶有貴氣的錢鼠-Rita(麗塔)與你一同慶新年，各式精緻商品都能發現她的迷人身。Rita穿著優雅的軟呢外套，領口搭配祖母綠的皮革緄邊，胸口縫製金色雙T Logo 珍珠母貝鈕釦，左手提著迷你小包，右邊口袋還放著她最愛的起士，擬人化的造型讓人莞爾一笑。",
  "sequence": 54,
  "author": "",
  "plan_type": 1,
  "is_highlight": false,
  "page_number": 206,
  "end_page": 207,
  "has_fit_reading": false,
  "has_audio": false,
  "has_video": false,
  "has_pdf": true,
  "main_image_version": 1578410912,
  "text_version": 1578410912,
  "issue_id": "5e14a2c0aa68d"
}
```

This endpoint retrieves a specific article.

### HTTP Request

`GET /articles/{article_id}`

## Get main image of a specific article

This endpoint retrieves main image of a specific article.

### HTTP Request

`GET /articles/{article_id}/main_image`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
size | optional | large(default)<br/>medium<br/>small
crop | optional | original(default)<br/>1:1<br/>4:3<br/>9:5
accept_webp | optional | The image file extension will be `.webp` if the `accept_webp` is given. Example: `accept_webp=1`. Otherwise, The image file extension will be `.jpg`

## Get keyword of a specific article

> API returns JSON structured like this:

```json
[
  "食物", "台北", "教學", "光碟"
]
```

This endpoint retrieves keywords of a specific article.

### HTTP Request

`GET /articles/{article_id}/keywords`

## Get access token

> API returns JSON structured like this:

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiJ9.eyJzIjoicyJ9.yqcB795dFYX1zeE2HntaZiJhjozlewwJeZr4G-Uq-wQ",
  "expired_at": 1580935149
}
```

This endpoint retrieves an access token for fetching article content.

### HTTP Request

`GET /articles/{article_id}/access_key`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
t | required | current UNIX timestamp in seconds.
uid | required | unique user id.
secret | required | SHA256 of parameters string.

* Concat all parameters and smarticle api secret with pipe as following format:<br/>
  <code>{article_id}|{t}|{uid}|{smarticle_api_secret}</code>
* Digest the string below SHA256 to get <code>secret</code>
* Example:
  * article_id: <code>c97e959b-cf6a-43a1-9795-493ece71499c</code>
  * t: <code>1580925055</code>
  * uid: <code>12345</code>
  * smarticle_api_secret: <code>69cbc3ae8b97</code>
  * Then, the parameters string will be:<br/>
    <code>c97e959b-cf6a-43a1-9795-493ece71499c|1580925055|12345|69cbc3ae8b97</code><br/>
  * And use SHA256 to digest the string to get `secret`:<br/>
    <code>c17719b21b26f2710679ab28f9e84c0e4338b58e013e81ba35355ecdc3c287e8</code><br/><br/>

You must replace <code>69cbc3ae8b97</code> with your API secret.

## Get article content

> API returns JSON structured like this:

```json
{
  "styles": {},
  "elements": [
    {
      "style": null,
      "element": {
        "content": "Angus Chiang 身上始終散發著空靈的夏日氣息，讓人聯想到電影《藍色大門》片尾，騎著自行車穿行在臺北街頭的少年。他的身後，是一群在台灣流行文化的滋潤下幸福快樂成長的一代人。",
        "dtype": "TEXT",
        "id": "client-4yojlqmfi4epouxz6o8jdb",
        "stype": "PREFACE"
      }
    },
    {
      "style": null,
      "element": {
        "content": "跟 Angus Chiang 的見面地點就在他工作室樓下的咖啡店，他帶著團隊把工作室從臺北搬到上海不到兩年時間。與他聊天，就像是走入了一幕又一幕的台灣青春電影。<br><br>從動畫創作專業改行時裝設計的 Angus Chiang 是土生土長的臺北男孩，他的設計根植於從1990年代至今的台灣本土民俗文化與流行文化，並賦予它們幽默和視覺化的解讀。因為太能引發台灣本土年輕人的共鳴，他最早期的設計在台灣年輕人眼中娛樂性比穿著性更大。「台灣有個論壇叫 PTT，我經常看到上面有人質疑我，不過也有很多支持我的人。」因為他所使用的設計元素與靈感來源，通常是台灣年輕人目之所見的、觸手可及的東西，對他們來說沒有什麼衝擊性，反而有偷懶的嫌疑。「PTT 上有很多聲音，比如『他哪是在做衣服，他根本就是在玩！』」 但在溫哥華時裝周、倫敦時裝周、巴黎時裝周組委會和 LVHM 大獎的評委會眼中，這些台灣獨有的元素反而帶來了巨大的文化衝擊，當然 Angus 也用他天馬行空的想象、恰到好處的克制，以及極強的視覺化表現力，生動地講述了他所處的社會時代和他所處的獨特地域文化的故事。<br><br>早前在巴黎男裝周發表的2020春夏系列，主題叫作「愛的主打歌」。這一次，他與台灣知名的音樂公司「滾石唱片」和「玫瑰唱片」合作，打造出一個「安可唱片（Angus Records&amp;Tapes）」，這是設計師對台灣流行音樂黃金時代的紀念，劉若英、孔令奇和徐懷鈺的〈大家來戀愛〉、伍佰的〈挪威的森林〉、張震嶽的〈愛我別走〉都成為秀場的背景音樂。還特別邀請台灣著名的音樂製作人黃韻玲錄製了電台主持的聲音，音樂、廣告、主持人旁邊穿插營造出一種台灣廣播電台興盛時代的熟悉感。整個系列的設計仍然回歸到 Angus Chiang 擅長的對台灣流行文化的解構與細節把玩之中，肩部廓形帶來一種流行巨星登場的氣勢，外套與T恤外的牛角扣綑紮，設計師用軟耳塞製成了牛角扣的樣子；口袋設計模擬了 CD 收納袋的樣子，唱片上黃色的促銷貼紙和反光銀色防偽標識圖案，成為系列中時髦的點綴。<br><br>本就是在台灣流行音樂與娛樂中浸泡長大的孩子，Angus 在大學時期的作業設計就模仿過台灣嘻哈歌手羅百吉。對於他來說，音樂用於時裝設計是很好玩的，比如把以前歌手的封面造型轉化成 Angus 自己的圖。臉、嘴都是自己拼上去的，但遠看很像那個歌手，有一種萬聖節變裝派對或是 Cosplay 節日的惡趣味，甚至能與當代藝術家 Cindy Sherman 的那一套自導自演的扮演攝影藝術達成一種理念的貫通。<br><br>作為一個在《偶像百分百》、《超級星光大道》、《康熙來了》等綜藝節目影響中長大的小孩，Angus Chiang 就是一本行走的亞洲流行文化活字典，他甚至有想過將秀場的一組模特打造成時髦的F4等形式。但經歷了1990年代至2000年代台灣流行文化最蓬勃的時期後，他注意到流行文化產業的變化。「還在念國中的時候，每個周六都有演唱會，還有什麼免費的專輯慶功會啊、唱片簽售會啊，觀眾拿著 CD 就可以進場；或者買杯飲料，憑那個瓶蓋就可以進場聽演唱會。明星們都在，周杰倫、張韶涵、潘瑋柏、蔡依林都在。大概從高中的時候開始，這種活動就愈來愈少了。以前專輯破百萬、80萬，明星們還會手持一個小錘出來錘冰。後來銷量10萬的唱片都能破冰慶祝了，最後也沒人再做這種事了。我覺得特別可惜，所以這個新系列是從1978年講起，把黑膠、卡帶、CD、MP3，到現在的線上音樂的演變，夠過一場秀體現到一個側面。」聊到這裡，他的聲音帶著點遺憾，彷彿一個年輕人手握一把鑰匙，卻再也打不開故居的門。而現在的他只要一回家，就會打開電視，追看由台灣明星大小S、阿雅和范曉萱一起錄製的綜藝真人秀《我們是真正的朋友》。雖然這群陪伴著他長大的台灣流行文化符號依然活躍在屏幕上，但有些東西已經微妙地悄然改變了。",
        "dtype": "TEXT",
        "id": "client-nte6q35i8nhja6fw8wizo",
        "stype": "PARAGRAPH"
      }
    },
    {
      "style": null,
      "element": {
        "content": "",
        "dtype": "IMAGE",
        "id": "08313ee8-3227-11ea-900c-06737616480d",
        "stype": "IMAGE"
      }
    },
    {
      "style": null,
      "element": {
        "content": "『「工頭在搭建舞臺的時候很緊張、壓力很大，他們嚼檳榔，工地上都是一堆一堆的檳榔渣。」每每這樣想著，Angus 能在異鄉的夜晚笑出聲來。』",
        "dtype": "TEXT",
        "id": "client-sjazuuqnl0jda796it4g5e",
        "stype": "QUOTE"
      }
    }
  ],
  "subtitle": "uno FASHION｜何處是故鄉 HOME TOWN",
  "version": "1.0.0",
  "language": "zh_TW",
  "author": "採訪、文字╲海淼",
  "has_audio": false,
  "sequence": 26,
  "has_fit_reading": true,
  "has_video": false,
  "images": [
    {
      "content": "",
      "dtype": "IMAGE",
      "id": "08313ee8-3227-11ea-900c-06737616480d",
      "stype": "IMAGE"
    }
  ],
  "magazine": {
    "bid": "5e15ec79c7d90",
    "issue": "2020/1月號 第245期",
    "name": "men's uno男人誌",
    "title": "mens_uno"
  },
  "intro": "Angus Chiang 身上始終散發著空靈的夏日氣息，讓人聯想到電影《藍色大門》片尾，騎著自行車穿行在臺北街頭的少年。他的身後，是一群在台灣流行文化的滋潤下幸福快樂成長的一代人。",
  "page_number": 95,
  "keywords": ["台灣", "文化", "唱片"],
  "title": "ANGUS CHIANG　他的背後是台灣流行文化孕育的一代",
  "has_translation": false,
  "article_id": "b16d037a-9ff5-420d-a890-025a4452f44c",
  "end_page": 96
}
```

This endpoint retrieves article content.

### HTTP Request

`GET /articles/{article_id}/text.json`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
access_token | required | This token is from the response of `GET /articles/{article_id}/access_key`. It should be valid and not expired.
