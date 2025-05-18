---
sidebar_position: 2
---

# Register

Untuk register ke backend ini, gampang cuyy.

Lu harus siapin data data dibawah ini :

- Uid Ktp : **Wajib**
- Username : **Wajib**
- Email : **Opsional**
- Nik : **Opsional**
- Password : **Wajib**
- Tipe akun : Opsional (default Pembeli)
- Profile_picture : Opsional

Untuk fetch ke api nya lu bisa pake form data.

```javascript title="fetch.js"
async function register() {
  const formData = new FormData();
  formData.append("uid_ktp", "isi sendiri");
  formData.append("username", "isi sendiri");
  formData.append("email", "isi sendiri");
  formData.append("nik", "isi sendiri");
  formData.append("password", "isi sendiri");
  formData.append("tipe_akun", "isi sendiri, ini ga wajib");
  formData.append(
    "profile_picture",
    "isi sendiri, ini ga wajib dan harus tipenya file"
  );
  const data = await fetch("http://localhost:8080/api/auth/register", {
    method: "POST",
    body: formData,
  });
  const res = await data.json();
}
```

Kenapa ga pake json? Karena nanti kalo pake json **profile_picture** ga bakal bisa ke upload.

Dan nanti hasil return nya bakal kayak gini.

```json title="return.json"
{
  "error": false,
  "message": "Success",
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

Hampir sama kayak login, data tersebut lu tinggal simpan di frontend.
