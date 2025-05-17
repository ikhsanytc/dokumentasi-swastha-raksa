---
sidebar_position: 4
---

# Get Product

Untuk mendapatkan data produk produk lu, lu bisa melakukan cara ini.

Hal-hal yg perlu disiapkan:

- Token : **Wajib**

```javascript
async function getProduct() {
  const res = await fetch("http://localhost:8080/api/get_product", {
    method: "GET",
    headers: {
      Authorization: "Bearer (isi dengan token mu)",
    },
  });
  const data = await res.json();
}
```

```json
{
    "error": false,
    "message": "OK",
    "data": {
        "*isinya tentang produk produk lu"
    }
}
```
