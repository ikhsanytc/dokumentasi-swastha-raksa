---
sidebar_position: 2
---

# Edit Product

Untuk mengedit produck anda harus memastikan bahwa akun anda sudah bertipe penjual, cara nya anda bisa menuju [link ini](/docs/akun/change_role.md).

Jika sudah maka hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Id produk : **Wajib**
- Harga produk : **Opsional**
- Stok produk : **Opsional**

```javascript title="fetch.js"
async function fetchData() {
  const formData = new FormData();
  formData.append("id_produk", "Isi sendiri");
  formData.append("harga_produk", "Isi sendiri");
  formData.append("stok_produk", "Isi sendiri");
  const res = await fetch("http://localhost:8080/api/edit_product", {
    method: "POST",
    headers: {
      Authorization: "Bearer (isi dengan token mu)",
    },
    body: formData,
  });
  const data = await res.json();
}
```

dengan hasil return sebagai berikut

```json
{
    "error": false,
    "message": "Berhasil edit produk",
    "data": {
        "*isinya tentang data apa saja yg berhasil di rubah"
    }
}
```
