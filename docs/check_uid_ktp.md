---
sidebar_position: 3
---

# Check Uid Ktp

Untuk mengecek uid ktp yang di dapatkan dari nfc, ada atau tidak di database gua, caranya ya pake cara ini.

Hal-hal yg perlu disiapkan :

- Uid : **Wajib**

```javascript title="fetch.js"
async function checkUidKtp() {
  const data = await fetch(
    "http://localhost:8080/api/check_uid_ktp/(uid ktp nya)",
    {
      method: "GET",
    }
  );
  const res = await data.json();
}
```

Nanti bakal dapet respon kayak gini.

```json title="return.json"
{
  "error": false,
  "message": "Akun tersebut ada"
}
```

Kalo ga ada akunnya, bakal kaya gini.

```json title="return.json"
{
  "error": true,
  "message": "Tidak ada akun dengan uid ktp tersebut"
}
```
