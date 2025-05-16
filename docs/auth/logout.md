---
sidebar_position: 3
---

# Logout

Untuk logout sebenarnya lu tinggal hapus data tentang akun dan token di frontend, cuman kalo gitu keamananya kurang.

Jadi gua bikin mekanisme blacklist token agar token sebelumnya yang udh di logout ga bakal bisa di pake lagi.

Cara fetch api nya agak sedikit sama, disini bedanya lu masukin token yang lu dapet dari hasil login atau register tadi.

Hal-hal yg perlu disiapkan :

- Token auth : **Wajib**

Misal disini gua simpen data tentang akun di localStorage.

```javascript title="fetch.js"
async function logout() {
  const data = await fetch("http://localhost:8080/api/auth/logout", {
    method: "DELETE",
    header: {
      Authorization:
        "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE3NDczMDMxMTYsImV4cCI6MTc1NTA3OTExNiwidWlkIjoiZXlnc2d5YWd3en0.nSeEFSlJqNfoZLrHyi4pBdQ2-y_fkvv6S-Wx8xcqTU5616166",
    },
  });
  const res = await data.json();
  localStorage.removeItem("userInfo");
}
```

Nanti jika lu pake token yang sama, bakal ga bisa akses lagi karena tokennya gua blacklist.
