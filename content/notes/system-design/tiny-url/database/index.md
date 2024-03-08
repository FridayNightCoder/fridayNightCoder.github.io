---
title: Database
weight: 10
menu:
  notes:
    name: Database
    identifier: tiny-database
    parent: tiny-url
    weight: 10
---
{{< note title="Database Tables">}}
- Users table
  - UserId: int
  - Email: string
  - PasswordHash: string
  - CreationTime: date
- Link table
  - ShortUrl: string (Primary or Partition Key)
  - Expiration: date
  - UserId: int
  - OriginalLink: string
- Click table
  - ShortUrl: int
  - TimeClicked: date
  - ClickerInfo: Json
{{< /note >}}