### GET/users/me (Текущий профиль)
Responses  
200
```jsonl
{
  "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "email": "user@example.com",
  "full_name": "string",
  "locale": "string",
  "timezone": "string",
  "status": "active",
  "created_at": "2026-09-21T13:01:11.868Z",
  "updated_at": "2026-09-21T13:01:11.868Z"
}
```
401
```jsonl
{
  "type": "https://example.com/",
  "title": "string",
  "status": 0,
  "detail": "string",
  "instance": "https://example.com/",
  "trace_id": "string",
  "errors": [
    {
      "field": "string",
      "message": "string"
    }
  ]
}
```
### POST/users/me/documents (Добавить документ)
Request body
```jsonl
{
  "doc_type": "passport",
  "doc_number": "string",
  "issued_by": "string",
  "issue_date": "2026-09-21",
  "expiry_date": "2026-09-21",
  "country_code": "string"
}
```
Responses  
201 
```jsonl
{
  "document_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "doc_type": "passport",
  "doc_number_masked": "****1234",
  "issued_by": "string",
  "issue_date": "2026-09-21",
  "expiry_date": "2026-09-21",
  "country_code": "st",
  "created_at": "2026-09-21T13:02:48.626Z"
}
```
### POST/trips (Создать поездку)
Request body

```jsonl
{
  "title": "string",
  "destination": "string",
  "start_date": "2026-09-21",
  "end_date": "2026-09-21",
  "base_timezone": "UTC",
  "budget": 0,
  "currency": "EUR"
}
```
Responses  
201  
```jsonl
{
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "owner_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "title": "string",
  "destination": "string",
  "start_date": "2026-09-21",
  "end_date": "2026-09-21",
  "base_timezone": "Europe/Madrid",
  "budget": 0,
  "currency": "EUR",
  "status": "draft",
  "version": 0,
  "participants": [
    {
      "participant_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "full_name": "string",
      "role": "organizer",
      "status": "invited",
      "joined_at": "2026-09-21T09:24:20.834Z"
    }
  ],
  "created_at": "2026-09-21T09:24:20.834Z",
  "updated_at": "2026-09-21T09:24:20.834Z"
}
```
  
    
### GET/trips/{tripId} (Получить поездку)
Responses  
200
```jsonl
{
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "owner_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "title": "string",
  "destination": "string",
  "start_date": "2026-09-21",
  "end_date": "2026-09-21",
  "base_timezone": "Europe/Madrid",
  "budget": 0,
  "currency": "EUR",
  "status": "draft",
  "version": 0,
  "participants": [
    {
      "participant_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "full_name": "string",
      "role": "organizer",
      "status": "invited",
      "joined_at": "2026-09-21T09:25:51.474Z"
    }
  ],
  "created_at": "2026-09-21T09:25:51.474Z",
  "updated_at": "2026-09-21T09:25:51.474Z"
}
```
404  
```jsonl
{
  "type": "https://example.com/",
  "title": "string",
  "status": 0,
  "detail": "string",
  "instance": "https://example.com/",
  "trace_id": "string",
  "errors": [
    {
      "field": "string",
      "message": "string"
    }
  ]
}
```
### GET/trips/{tripId}/participants (Список участников)
Responses  
200
```jsonl
[
  {
    "participant_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "full_name": "string",
    "role": "organizer",
    "status": "invited",
    "joined_at": "2026-09-21T12:57:00.411Z"
  }
]
```
### POST/trips/{tripId}/participants (Добавить участника)
Request body
```jsonl
{
  "email": "user@example.com",
  "role": "organizer"
}
```
Responses  
200
```jsonl
[
  {
    "item_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "type": "flight",
    "title": "string",
    "start_datetime": "2026-09-21T09:28:29.332Z",
    "end_datetime": "2026-09-21T09:28:29.332Z",
    "timezone": "Europe/Madrid",
    "location": {
      "lat": 0,
      "lon": 0
    },
    "address": "string",
    "position_order": 0,
    "status": "proposed",
    "created_by": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "version": 0,
    "votes": [
      {
        "vote_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "item_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "vote": 1,
        "comment": "string",
        "created_at": "2026-09-21T09:28:29.332Z"
      }
    ],
    "created_at": "2026-09-21T09:28:29.332Z",
    "updated_at": "2026-09-21T09:28:29.332Z"
  }
]

```
### GET/trips/{tripId}/conflicts (Проверить конфликты расписания)
Responses  
200
```jsonl
[
  {
    "conflict_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "type": "transit_too_short",
    "severity": "low",
    "affected_items": [
      "3fa85f64-5717-4562-b3fc-2c963f66afa6"
    ],
    "description": "string",
    "suggestion": "string",
    "detected_at": "2026-09-21T12:54:28.105Z",
    "resolved": true
  }
]
```
### POST/bookings (Создать бронирование)
Request body
```jsonl
{
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "item_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "offer_id": "string",
  "booking_type": "flight",
  "passengers": [
    {
      "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "document_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "passenger_type": "adult"
    }
  ]
}
```
Responses  
201
```jsonl
{
  "booking_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "item_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "supplier_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "supplier": "string",
  "external_booking_ref": "string",
  "booking_type": "flight",
  "status": "pending",
  "total_price": {
    "amount": 0,
    "currency": "string"
  },
  "cancellation_policy": {},
  "booked_by": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "booked_at": "2026-09-21T09:31:53.948Z",
  "idempotency_key": "string",
  "version": 0,
  "updated_at": "2026-09-21T09:31:53.948Z",
  "passengers": [
    {
      "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "booking_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "full_name": "string",
      "document_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "passenger_type": "adult",
      "created_at": "2026-09-21T09:31:53.948Z"
    }
  ]
}
```
409
```jsonl
{
  "type": "https://example.com/",
  "title": "string",
  "status": 0,
  "detail": "string",
  "instance": "https://example.com/",
  "trace_id": "string",
  "errors": [
    {
      "field": "string",
      "message": "string"
    }
  ]
}
```
### POST/bookings/{bookingId}/passengers (Добавить пассажира)
Request body
```jsonl
{
  "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "document_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "passenger_type": "adult"
}
```
201
```jsonl
{
  "id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "booking_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "full_name": "string",
  "document_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "passenger_type": "adult",
  "created_at": "2026-09-21T09:33:31.846Z"
}
```
### GET/recommendations (Персональные рекомендации)
Responses  
200
```jsonl
[
  {
    "recommendation_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "item_type": "hotel",
    "payload": {},
    "score": 1,
    "reason": "string",
    "shown": true,
    "clicked": true,
    "converted": true,
    "created_at": "2026-09-21T09:35:13.241Z"
  }
]

```
### GET/notifications (Список уведомлений)
Responses  
200

```jsonl
{
  "items": [
    {
      "notification_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "type": "booking_confirmed",
      "channel": "push",
      "payload": {},
      "status": "queued",
      "dedup_key": "string",
      "created_at": "2026-09-21T09:35:57.114Z",
      "sent_at": "2026-09-21T09:35:57.114Z",
      "read_at": "2026-09-21T09:35:57.114Z"
    }
  ],
  "next_cursor": "string",
  "unread_count": 0
}
```
### GET/notifications/settings (Настройки уведомлений)
Responses
200

```jsonl
{
  "channels": [
    {
      "channel": "push",
      "enabled": true
    }
  ],
  "quiet_hours_from": "22:00",
  "quiet_hours_to": "08:00"
}

```

### POST/reviews (Оставить отзыв)
Request body
```jsonl
{
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "booking_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "rating": 1,
  "category": "flight",
  "comment": "string"
}
```
Responses
201
```jsonl
{
  "review_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "user_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "trip_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "booking_id": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "rating": 1,
  "category": "flight",
  "comment": "string",
  "moderated": true,
  "moderation_status": "pending",
  "created_at": "2026-09-21T14:12:38.775Z"
}
```

