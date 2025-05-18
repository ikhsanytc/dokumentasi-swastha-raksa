---
sidebar_position: 1
---

# Login

Untuk login atau masuk ke akun di backend gua, pastikan anda mempunyai akun (yaiyalah anjir).

Lalu langkah selanjutnya adalah fetch ke api gua.

Data data yang perlu dikirim adalah :

- Username : **wajib**
- Email : **Opsional**
- Nik : **Opsional**
- Password : **wajib**
- Uid ktp : **Wajib**

Lu bisa ngirim lewat json atau form data.

```javascript title="login-dengan-json.js"
async function login() {
  const data = await fetch("http://localhost:8080/api/auth/login", {
    method: "POST",
    header: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      username: "isi sendiri",
      email: "isi sendiri",
      nik: "isi sendiri",
      password: "isi sendiri",
      uid_ktp: "isi sendiri",
    }),
  });
  const res = await data.json();
}
```

Atau dengan form data.

```javascript title="login-dengan-form-data.js"
async function login() {
  const formData = new FormData();
  formData.append("username", "isi sendiri");
  formData.append("email", "isi sendiri");
  formData.append("nik", "isi sendiri");
  formData.append("password", "isi sendiri");
  formData.append("uid_ktp", "isi sendiri");
  const data = await fetch("http://localhost:8080/api/auth/login", {
    method: "POST",
    body: formData,
  });
  const res = await data.json();
}
```

Nanti bakal dapet data kek gini dalam bentuk json.

```json title="return.json"
{
  "error": false,
  "message": "OK",
  "data": {
    "auth_key": "token yg lu dapet nanti",
    "username": "username akun lu",
    "email": "email lu",
    "nik": "nik lu",
    "profile_picture": "gambar profile akun lu",
    "tipe_akun": "Tipe akun lu apa",
    "data_toko": "informasi mengenai data toko jika lu penjual"
  }
}
```

Contoh misal

```json title="return-contoh.json"
{
  "error": false,
  "message": "OK",
  "data": {
    "auth_key": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE3NDczMDMxMTYsImV4cCI6MTc1NTA3OTExNiwidWlkIjoiZXlnc2d5YWd3en0.nSeEFSlJqNfoZLrHyi4pBdQ2-y_fkvv6S-Wx8xcqTU5616166",
    "username": "ikhsan",
    "email": "ikhsanm181209@gmail.com",
    "nik": "ini_nik_ygy",
    "profile_picture": "http://localhost:8080/uploads/1747305267_2fa48fd2700486ab9a43.jpg",
    "tipe_akun": "Penjual",
    "data_toko": "Informasi toko dalam bentuk json"
  }
}
```

Dan di frontend lu tinggal simpen data yang di return dari api gua, termasuk token tersebut.
