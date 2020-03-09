# Issues

## Get all issues of a magazine

> API returns JSON structured like this:

```json
[
  {
    "id": "5e14a2c0aa68d",
    "bid": "5e14a2c0aa68d",
    "issue_name": "2020/1月號 第280期",
    "published_at": 1578410688,
    "available_from": 0,
    "available_to": 2147483640,
    "description": "曾之喬說自己最大的意義是分享，她喜歡把自己所體會與得到的，不斷的分出去，她說分了不會變少，反而會感覺越來越豐富。",
    "off_shelf_at": 1578410912,
    "has_fit_reading": true,
    "has_audio": false,
    "has_video": false,
    "has_pdf": true,
    "is_adult": false,
    "is_left_flip": true,
    "cover_version": 1578410912,
    "bundle_version": 1578410912,
    "magazine_id": "vogue",
    "magazine_name": "VOGUE",
    "year": 2020
  }
]
```

This endpoint retrieves all issues of a magazine.

### HTTP Request

`GET /magazines/{magazine_id}/issues`

## Get a specific issue

> API returns JSON structured like this:

```json
{
  "id": "5e14a2c0aa68d",
  "bid": "5e14a2c0aa68d",
  "issue_name": "2020/1月號 第280期",
  "published_at": 1578410688,
  "available_from": 0,
  "available_to": 2147483640,
  "description": "曾之喬說自己最大的意義是分享，她喜歡把自己所體會與得到的，不斷的分出去，她說分了不會變少，反而會感覺越來越豐富。",
  "off_shelf_at": 1578410912,
  "has_fit_reading": true,
  "has_audio": false,
  "has_video": false,
  "has_pdf": true,
  "is_adult": false,
  "is_left_flip": true,
  "cover_version": 1578410912,
  "bundle_version": 1578410912,
  "magazine_id": "vogue",
  "magazine_name": "VOGUE",
  "year": 2020
}
```

This endpoint retrieves a specific issue.

### HTTP Request

`GET /issues/{issue_id}`

## Get price of a specific issue

> API returns JSON structured like this:

```json
{
  "price_per_article": "4.5"
}
```

This endpoint retrieves price of a specific issue.

### HTTP Request

`GET /issues/{issue_id}/price`

## Get cover of a specific issue

This endpoint retrieves cover of a specific issue.

### HTTP Request

`GET /issues/{issue_id}/cover(/{size})`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
size | optional | large(default)<br/>medium<br/>small
accept_webp | optional | The image file extension will be `.webp` if the `accept_webp` is given. Example: `accept_webp=1`. Otherwise, The image file extension will be `.jpg`
