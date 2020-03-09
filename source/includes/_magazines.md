# Magazines

## Get all magazines

> API returns JSON structured like this:

```json
[
  {
    "id": "vogue",
    "title": "vogue",
    "name": "VOGUE",
    "description": "記錄逾百年頂尖流行，被喻為「時尚聖經」的VOGUE雜誌是時尚類國際中文版女性雜誌的領導者。\r\nVOGUE時尚雜誌每月均為您報導來自巴黎、米蘭、紐約頂尖時裝設計大師的流行預言及獨家專訪，帶您永遠走在時尚與品味的頂端！",
    "is_left_flip": true
  }
]
```

This endpoint retrieves all magazines.

### HTTP Request

`GET /magazines`

## Get a specific magazine

> API returns JSON structured like this:

```json
{
  "id": "vogue",
  "title": "vogue",
  "name": "VOGUE",
  "description": "記錄逾百年頂尖流行，被喻為「時尚聖經」的VOGUE雜誌是時尚類國際中文版女性雜誌的領導者。\r\nVOGUE時尚雜誌每月均為您報導來自巴黎、米蘭、紐約頂尖時裝設計大師的流行預言及獨家專訪，帶您永遠走在時尚與品味的頂端！",
  "is_left_flip": true
}
```

This endpoint retrieves a specific magazine.

### HTTP Request

`GET /magazines/{magazine_id}`
