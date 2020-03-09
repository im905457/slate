# Videos

## Get video info

> API returns JSON structured like this:

```json
{
  "id": "6047263652665361362",
  "width": 1280,
  "height": 720,
  "length": 60,
  "article_id": "0000615c-a5d8-4bfc-b7ac-48f46a761181"
}
```

This endpoint retrieves information of specific video.

### HTTP Request

`GET /videos/{video_id}`

## Get video thumbnail

This endpoint retrieves thumbnail of specific video.

### HTTP Request

`GET /videos/{video_id}(/{size})`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
size | optional | large(default)<br/>medium<br/>small


## Get video content

This endpoint retrieves video in article json.

### HTTP Request

`GET /videos/{video_id}/playback`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
access_token | required | This token is from the response of `GET /articles/{article_id}/access_key`. It should be valid and not expired.
