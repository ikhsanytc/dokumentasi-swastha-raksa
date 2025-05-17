---
sidebar_position: 1
---

# Get Transaction

Untuk mendapatkan riwayat transaction, lu bisa melakukan cara ini.

Hal-hal yg perlu disiapkan:

- Token : **Wajib**

```javascript
async function getTransaction() {
  const res = await fetch("http://localhost:8080/api/get_transaction", {
    method: "GET",
    headers: {
      Authorization: "Bearer (isi dengan token mu)",
    },
  });
  const data = await res.json();
}
```

Lu akan mendapatkan return seperti ini

```json
{
    "error": false,
    "message": "OK",
    "data": {
        "*isinya riwayat transaction lu"
    }
}
```
