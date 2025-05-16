---
sidebar_position: 2
---

# Get User Info

Cara ini adalah cara untuk mendapatkan informasi tentang user jikalau lu sudah login atau register.

Karena hal-hal yg perlu disiapkan :

- Token : **Wajib**

Cara untuk fetchnya seperti ini.

```javascript title="fetch.js"
async function getUserInfo() {
  const data = await fetch("http://localhost:8080/api/get_user_info", {
    method: "GET",
    header: {
      Authorization: "Bearer (isi dengan token lu)",
    },
  });
  const res = await data.json();
}
```

Nanti hasil returnnya akan seperti ini.

```json title="return.json"
{
    "error": false,
    "message": "OK",
    "data": {
        "*isinya tentang informasi akun lu"
    }
}
```
