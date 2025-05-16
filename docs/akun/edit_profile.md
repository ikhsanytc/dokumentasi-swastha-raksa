---
sidebar_position: 3
---

# Edit Profile

Untuk bisa mengedit profile, ikuti cara ini.

Hal-hal yg perlu disiapkan:

- Token : **Wajib**
- Username : **Opsional**
- Password: **Opsional**
- Email : **Opsional**
- Data toko : **Opsional**, hanya akun dengan tipe penjual yang bisa mengedit ini
- Profile picture : **Opsional**

Cara untuk fetch api nya.

```javascript title="fetch.js"
async function login() {
  const formData = new FormData();
  formData.append("username", "ini opsional");
  formData.append("password", "ini opsional");
  formData.append("email", "ini opsional");
  formData.append(
    "data_toko",
    "ini opsional, hanya akun tipe penjual yang boleh mengedit data ini"
  );
  formData.append("profile_picture", "ini opsional, tipenya harus file");
  const data = await fetch("http://localhost:8080/api/edit_profile", {
    method: "POST",
    headers: {
      Authorization: "Bearer (isi dengan token mu)",
    },
    body: formData,
  });
  const res = await data.json();
}
```

Dan nanti hasil returnnya adalah

```json title="return.json"
{
    "error": false,
    "message": "Berhasil",
    "data": {
        "berisi tentang data apa saja yg barusan kamu ubah"
    }
}
```
