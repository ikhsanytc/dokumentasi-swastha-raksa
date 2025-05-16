---
sidebar_position: 1
---

# Change Role

Untuk mengubah tipe akun dari pembeli ke penjual atau pun sebaliknya, cara ini bisa diikuti.

Hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Role : **Wajib**

Cara menggunakan api ini.

```javascript title="fetch.js"
// untuk mengubah ke pembeli.
async function changeRole() {
  const data = await fetch("http://localhost:8080/api/auth/change_role", {
    method: "POST",
    header: {
      "Content-Type": "application/json",
      Authorization: "Bearer (isi dengan token mu)",
    },
    body: JSON.stringify({
      role: "Pembeli",
    }),
  });
  const res = await data.json();
}
```

**Perhatian** jika anda mengubah tipe akun dari penjual ke pembeli produk anda bisa hilang, dan data_toko akan kosong.
