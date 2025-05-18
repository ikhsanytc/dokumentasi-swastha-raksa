---
sidebar_position: 2
---

# Add Transaction

Untuk menambahkan riwayat transaction pastikan tipe akun mu adalah penjual, [klik link ini](/docs/akun/change_role.md) untuk melihat cara ganti tipe akun.

Hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Uid buyer : **Wajib**
- Products : **Wajib**

Parameter products harus berupa json string, contoh:

```json
[
  { "id_produk": 1, "jumlah_produk": 2 },
  { "id_produk": 2, "jumlah_produk": 1 }
]
```

```javascript
async function addTransactio() {
  const products = [
    {
      id_produk: 1,
      jumlah_produk: 2,
    },
  ];
  const formData = new FormData();
  formData.append("uid_buyer", "isi sendiri");
  formData.append("products", JSON.stringify(products));
  const res = await fetch("http://localhost:8080/api/add_transaction", {
    method: "POST",
    headers: {
      Authorization: "Bearer (isi dengan token mu)",
    },
    body: formData,
  });
  const res = await res.json();
}
```

dengan hasil return

```json
{
  "error": false,
  "message": "Berhasil"
}
```
