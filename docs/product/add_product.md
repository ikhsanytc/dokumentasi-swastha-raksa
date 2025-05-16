---
sidebar_position: 1
---

# Add Product

Untuk menambahkan produck anda harus memastikan bahwa akun anda sudah bertipe penjual, cara nya anda bisa menuju [link ini](/docs/akun/change_role.md).

Jika sudah maka hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Nama produk : **Wajib**
- Jenis produk : **Wajib**
- Harga produk : **Wajib**
- Stok produk : **Wajib**

```javascript title="fetch.js"
async function fetchData() {
  const formData = new FormData();
  formData.append("nama_produk", "isi sendiri");
  formData.append("jenis_produk", "isi sendiri");
  formData.append("harga_produk", "isi sendiri");
  formData.append("stok_produk", "isi sendiri");
  const data = await fetch("http://localhost:8080/api/add_product", {
    method: "POST",
    header: {
      Authorization: "Bearer (isi dengan token mu)",
    },
    body: formData,
  });
  const res = await data.json();
}
```

Jika berhasil maka muncul response.

```json title="res.json"
{
  "error": false,
  "message": "OK"
}
```
