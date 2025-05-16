---
sidebar_position: 3
---

# Delete Product

Untuk mengdelete produck anda harus memastikan bahwa akun anda sudah bertipe penjual, cara nya anda bisa menuju [link ini](/docs/akun/change_role.md).

Hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Id produk : **Wajib**

```javascript
async function fetchData() {
  const res = await fetch(
    "http://localhost:8080/api/delete_product/(id produknya)",
    {
      method: "DELETE",
      headers: {
        Authorization: "Bearer (isi dengan token mu)",
      },
    }
  );
  const data = await res.json();
}
```

dengan hasil return sebagai berikut

```json
{
  "error": false,
  "message": "Berhasil delete"
}
```
