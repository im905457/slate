# Audios

## Get audio info

> API returns JSON structured like this:

```json
{
  "id": "6047263652665361362",
  "length": 60,
  "article_id": "0000615c-a5d8-4bfc-b7ac-48f46a761181"
}
```

This endpoint retrieves information of specific audio.

### HTTP Request

`GET /audios/{audio_id}`

## Get audio content

This endpoint retrieves audio in article json.

### HTTP Request

`GET /audios/{audio_id}/playback`

### Query Parameters

Parameter | Required | Description
--------- | -------- | -----------
access_token | required | This token is from the response of `GET /articles/{article_id}/access_key`. It should be valid and not expired.
