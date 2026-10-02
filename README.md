# 👻 Modul Kaamanan Ghost
**Alat Penguatan Kaamanan Windows sareng Azure Dumasar PowerShell**

> **Penguatan kaamanan proaktif pikeun endpoints Windows sareng lingkungan Azure.** Ghost nyayogikeun fungsi penguatan dumasar PowerShell anu tiasa ngabantosan ngirangan vektor serangan umum ku cara nganonaktipkeun jasa sareng protokol anu henteu diperyogikeun.

## ⚠️ Peringatan Penting

**UJI COBA DIPERYOGIKEUN**: Salawasna uji coba Ghost di lingkungan non-produksi heula. Nganonaktipkeun jasa tiasa mangaruhan fungsi bisnis anu sah.

**TAYA JAMINAN**: Sanaos Ghost nargétkeun vektor serangan umum, teu aya alat kaamanan anu tiasa nyegah sadaya serangan. Ieu mangrupikeun hiji komponén dina strategi kaamanan anu komprehensif.

**DAMPAK OPERASIONAL**: Sababaraha fungsi tiasa mangaruhan fungsionalitas sistem. Tingali deui unggal setélan kalayan ati-ati sateuacan panyebaran.

**EVALUASI PROFÉSIONAL**: Pikeun lingkungan produksi, konsultasi sareng ahli kaamanan pikeun mastikeun yén setélan saluyu sareng kabutuhan organisasi anjeun.

## 📊 Bentang Kaamanan

Karugian ransomware ngahontal **$57 milyar taun 2025**, panilitian nunjukkeun yén seueur serangan anu suksés ngamanfaatkeun jasa dasar Windows sareng konfigurasi anu salah. Vektor serangan umum kalebet:

- **90% kajadian ransomware** ngalibatkeun eksploitasi RDP
- **Kerentanan SMBv1** ngamungkinkeun serangan sapertos WannaCry sareng NotPetya
- **Makro dokumén** tetep janten metode utama pangiriman malware
- **Serangan dumasar USB** terus nargétkeun jaringan air-gap
- **Penyalahgunaan PowerShell** parantos ningkat sacara signifikan dina taun-taun ayeuna

## 🛡️ Fungsi Kaamanan Ghost

Ghost nyayogikeun **16 fungsi penguatan Windows** ditambah **integrasi kaamanan Azure**:

### Penguatan Windows Endpoint

| Fungsi | Tujuan | Pertimbangan |
|----------|---------|----------------|
| `Set-RDP` | Ngokolakeun aksés Remote Desktop | Tiasa mangaruhan administrasi jarak jauh |
| `Set-SMBv1` | Ngontrol protokol SMB warisan | Diperyogikeun pikeun sistem anu lami pisan |
| `Set-AutoRun` | Ngontrol AutoPlay/AutoRun | Tiasa mangaruhan kanyamanan pangguna |
| `Set-USBStorage` | Ngawates alat neundeun USB | Tiasa mangaruhan pamakean USB anu sah |
| `Set-Macros` | Ngontrol palaksanaan makro Office | Tiasa mangaruhan dokumén anu diaktipkeun makro |
| `Set-PSRemoting` | Ngokolakeun PowerShell remoting | Tiasa mangaruhan manajemén jarak jauh |
| `Set-WinRM` | Ngontrol Windows Remote Management | Tiasa mangaruhan administrasi jarak jauh |
| `Set-LLMNR` | Ngokolakeun protokol résolusi nami | Biasana aman pikeun dianonaktipkeun |
| `Set-NetBIOS` | Ngontrol NetBIOS dina TCP/IP | Tiasa mangaruhan aplikasi warisan |
| `Set-AdminShares` | Ngokolakeun babagi administratif | Tiasa mangaruhan aksés file jarak jauh |
| `Set-Telemetry` | Ngontrol pangumpulan data | Tiasa mangaruhan kamampuan diagnostik |
| `Set-GuestAccount` | Ngokolakeun akun tamu | Biasana aman pikeun dianonaktipkeun |
| `Set-ICMP` | Ngontrol réspon ping | Tiasa mangaruhan diagnostik jaringan |
| `Set-RemoteAssistance` | Ngokolakeun Remote Assistance | Tiasa mangaruhan operasi help desk |
| `Set-NetworkDiscovery` | Ngontrol pamanggihan jaringan | Tiasa mangaruhan browsing jaringan |
| `Set-Firewall` | Ngokolakeun Windows Firewall | Kritis pikeun kaamanan jaringan |

### Kaamanan Azure Cloud

| Fungsi | Tujuan | Syarat |
|----------|---------|--------------|
| `Set-AzureSecurityDefaults` | Ngaktipkeun kaamanan dasar Azure AD | Idin Microsoft Graph |
| `Set-AzureConditionalAccess` | Ngonpigurasi kawijakan aksés | Lisénsi Azure AD P1/P2 |
| `Set-AzurePrivilegedUsers` | Audit akun hak husus | Idin Global Admin |

### Pilihan Panyebaran Perusahaan

| Métode | Kasus Pamakéan | Syarat |
|--------|----------|--------------|
| **Palaksanaan Langsung** | Uji coba, lingkungan alit | Hak admin lokal |
| **Group Policy** | Lingkungan domain | Admin domain, manajemén GP |
| **Microsoft Intune** | Alat anu dikokolakeun ku cloud | Lisénsi Intune, Graph API |

## 🚀 Mimiti Gancang

### Evaluasi Kaamanan
```powershell
# Muatkeun modul Ghost
Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1' -OutFile .\Ghost.ps1
Get-Content .\Ghost.ps1
. .\Ghost.ps1

# Pariksa postur kaamanan ayeuna
Get-Ghost
```

### Penguatan Dasar (Uji Coba Heula)
```powershell
# Penguatan ésénsial - uji coba heula di lingkungan laboratorium
Set-Ghost -SMBv1 -AutoRun -Macros

# Tinjau parobihan
Get-Ghost
```

### Panyebaran Perusahaan
```powershell
# Panyebaran Group Policy (lingkungan domain)
Set-Ghost -SMBv1 -AutoRun -GroupPolicy

# Panyebaran Intune (alat anu dikokolakeun ku cloud)
Set-Ghost -SMBv1 -RDP -USBStorage -Intune
```

## 📋 Métode Instalasi

### Pilihan 1: Unduhan Langsung (Uji Coba)
```powershell
Invoke-WebRequest 'https://raw.githubusercontent.com/jimrtyler/Ghost/main/Ghost.ps1' -OutFile .\Ghost.ps1
Get-Content .\Ghost.ps1
. .\Ghost.ps1
```

### Pilihan 2: Instalasi Modul
```powershell
# Pasang tina PowerShell Gallery (nalika sayogi)
Install-Module Ghost -Scope CurrentUser
Import-Module Ghost
```

### Pilihan 3: Panyebaran Perusahaan
```powershell
# Salin ka lokasi jaringan pikeun panyebaran Group Policy
# Konpigurasi skrip PowerShell Intune pikeun panyebaran cloud
```

## 💼 Conto Kasus Pamakéan

### Usaha Leutik
```powershell
# Panyalindungan dasar kalayan dampak minimal
Set-Ghost -SMBv1 -AutoRun -Macros -ICMP
```

### Lingkungan Kasehatan
```powershell
# Penguatan anu fokus kana HIPAA
Set-Ghost -SMBv1 -RDP -USBStorage -AdminShares -Telemetry
```

### Jasa Keuangan
```powershell
# Konfigurasi kaamanan tinggi
Set-Ghost -RDP -SMBv1 -AutoRun -USBStorage -Macros -PSRemoting -AdminShares
```

### Organisasi Cloud-First
```powershell
# Panyebaran anu dikokolakeun ku Intune
Connect-IntuneGhost -Interactive
Set-Ghost -SMBv1 -RDP -AutoRun -Macros -Intune
```

## 🔍 Detil Fungsi

### Fungsi Penguatan Utama

#### Jasa Jaringan
- **RDP**: Ngahalangan aksés desktop jarak jauh atanapi acak port
- **SMBv1**: Nganonaktipkeun protokol babagi file warisan
- **ICMP**: Nyegah réspon ping pikeun reconnaissance
- **LLMNR/NetBIOS**: Ngahalangan protokol résolusi nami warisan

#### Kaamanan Aplikasi
- **Makro**: Nganonaktipkeun palaksanaan makro dina aplikasi Office
- **AutoRun**: Nyegah palaksanaan otomatis tina média anu tiasa dicabut

#### Manajemén Jarak Jauh
- **PSRemoting**: Nganonaktipkeun sesi jarak jauh PowerShell
- **WinRM**: Ngeureunkeun Windows Remote Management
- **Remote Assistance**: Ngahalangan sambungan bantuan jarak jauh

#### Kontrol Aksés
- **Admin Shares**: Nganonaktipkeun babagi C$, ADMIN$
- **Guest Account**: Nganonaktipkeun aksés akun tamu
- **USB Storage**: Ngawates pamakean alat USB

### Integrasi Azure
```powershell
# Sambungkeun ka tenant Azure
Connect-AzureGhost -Interactive

# Aktipkeun default kaamanan
Set-AzureSecurityDefaults -Enable

# Konpigurasi aksés kondisional
Set-AzureConditionalAccess -BlockLegacyAuth -RequireMFA

# Audit pangguna hak husus
Set-AzurePrivilegedUsers -AuditOnly
```

### Integrasi Intune (Anyar dina v2)
```powershell
# Sambungkeun ka Intune
Connect-IntuneGhost -Interactive

# Sebarkeun ngaliwatan kawijakan Intune
Set-IntuneGhost -Settings @{
    RDP = $true
    SMBv1 = $true
    USBStorage = $true
    Macros = $true
}
```

## ⚠️ Pertimbangan Penting

### Syarat Uji Coba
- **Lingkungan Laboratorium**: Uji coba heula sadaya setélan di lingkungan anu terpisah
- **Panyebaran Bertahap**: Sebarkeun sacara bertahap pikeun ngaidentipikasi masalah
- **Rencana Rollback**: Pastoskeun anjeun tiasa ngabalikeun parobihan upami diperyogikeun
- **Dokumentasi**: Catat setélan anu mana anu jalan pikeun lingkungan anjeun

### Dampak Poténsial
- **Produktivitas Pangguna**: Sababaraha setélan tiasa mangaruhan alur kerja harian
- **Aplikasi Warisan**: Sistem lami tiasa ngabutuhkeun protokol khusus
- **Aksés Jarak Jauh**: Pertimbangkeun dampak kana administrasi jarak jauh anu sah
- **Prosés Bisnis**: Pariksa yén setélan henteu ngarusak fungsi kritis

### Watesan Kaamanan
- **Pertahanan Jero**: Ghost mangrupikeun hiji lapisan kaamanan, sanés solusi lengkep
- **Manajemén Kontinyu**: Kaamanan ngabutuhkeun pangawasan sareng pamutahiran kontinyu
- **Latihan Pangguna**: Kontrol téknis kedah dipasangkeun sareng kasadaran kaamanan
- **Évolusi Ancaman**: Métode serangan anyar tiasa ngalangkungan panyalindungan ayeuna

## 🎯 Conto Skenario Serangan

Sanaos Ghost nargétkeun vektor serangan umum, pencegahan spésifik gumantung kana palaksanaan sareng uji coba anu leres:

### Serangan Gaya WannaCry
- **Mitigasi**: `Set-Ghost -SMBv1` nganonaktipkeun protokol anu rentan
- **Pertimbangan**: Pastikan teu aya sistem warisan anu ngabutuhkeun SMBv1

### Ransomware Dumasar RDP
- **Mitigasi**: `Set-Ghost -RDP` ngahalangan aksés desktop jarak jauh
- **Pertimbangan**: Tiasa ngabutuhkeun métode aksés jarak jauh alternatif

### Malware Dumasar Dokumén
- **Mitigasi**: `Set-Ghost -Macros` nganonaktipkeun palaksanaan makro
- **Pertimbangan**: Tiasa mangaruhan dokumén sah anu makro diaktipkeun

### Ancaman anu Dikirimkeun USB
- **Mitigasi**: `Set-Ghost -USBStorage -AutoRun` ngawates fungsionalitas USB
- **Pertimbangan**: Tiasa mangaruhan pamakean alat USB anu sah

## 🏢 Fitur Perusahaan

### Dukungan Group Policy
```powershell
# Terapkeun setélan ngaliwatan registry Group Policy
Set-Ghost -SMBv1 -RDP -AutoRun -GroupPolicy

# Setélan diterapkeun di sakumna domain saatos refresh GP
gpupdate /force
```

### Integrasi Microsoft Intune
```powershell
# Cipta kawijakan Intune pikeun setélan Ghost
Set-IntuneGhost -Settings $GhostSettings -Interactive

# Kawijakan disebarkeun sacara otomatis ka alat anu dikokolakeun
```

### Laporan Kepatuhan
```powershell
# Ngahasilkeun laporan evaluasi kaamanan
Get-Ghost | Export-Csv -Path "SecurityAudit-$(Get-Date -Format 'yyyy-MM-dd').csv"

# Laporan postur kaamanan Azure
Get-AzureGhost | Out-File "AzureSecurityReport.txt"
```

## 📚 Prakték Pangalusna

### Sateuacan Panyebaran
1. **Dokumentasikeun Kaayaan Ayeuna**: Jalankeun `Get-Ghost` sateuacan parobihan
2. **Uji Coba Kalayan Ati-ati**: Validasi di lingkungan non-produksi
3. **Rencanakeun Rollback**: Terang kumaha ngabalikeun unggal setélan
4. **Tinjauan Stakeholder**: Pastoskeun unit bisnis nyatujuan parobihan

### Salami Panyebaran
1. **Pendekatan Bertahap**: Sebarkeun heula ka grup pilot
2. **Pantau Dampak**: Awas keluhan pangguna atanapi masalah sistem
3. **Dokumentasikeun Masalah**: Catat masalah naon waé pikeun rujukan hareup
4. **Komunikasikeun Parobihan**: Béjakeun pangguna ngeunaan perbaikan kaamanan

### Saatos Panyebaran
1. **Evaluasi Rutin**: Périodik jalankeun `Get-Ghost` pikeun mariksa setélan
2. **Perbarui Dokumentasi**: Jaga konfigurasi kaamanan ayeuna
3. **Tinjau Éféktivitas**: Pantau kajadian kaamanan
4. **Perbaikan Kontinyu**: Sesuaikeun setélan dumasar kana bentang ancaman

## 🔧 Pemecahan Masalah

### Masalah Umum
- **Kasalahan Idin**: Pastoskeun sesi PowerShell anu ditinggalkeun
- **Dependensi Jasa**: Sababaraha jasa tiasa gaduh dependensi
- **Kompatibilitas Aplikasi**: Uji coba sareng aplikasi bisnis
- **Konektivitas Jaringan**: Pariksa yén aksés jarak jauh masih jalan

### Pilihan Pamulihan
```powershell
# Aktipkeun deui jasa khusus upami diperyogikeun
Set-RDP -Enable
Set-SMBv1 -Enable
Set-AutoRun -Enable
Set-Macros -Enable
```

## 👨‍💻 Ngeunaan Panulis

**Jim Tyler** - Microsoft MVP pikeun PowerShell
- **YouTube**: [@PowerShellEngineer](https://youtube.com/@PowerShellEngineer) (10,000+ palanggan)
- **Newsletter**: [PowerShell.News](https://powershell.news) - Intelijén kaamanan mingguan
- **Panulis**: "PowerShell for Systems Engineers"
- **Pangalaman**: Dasawarsa otomatisasi PowerShell sareng kaamanan Windows

## 📄 Lisensi sareng Penolakan

### Lisensi MIT
Ghost disayogikeun dina Lisensi MIT pikeun pamakean, modifikasi, sareng distribusi gratis.

### Penolakan Kaamanan
- **Taya Jaminan**: Ghost disayogikeun "sapertos kitu" tanpa jaminan naon waé
- **Uji Coba Diperyogikeun**: Salawasna uji coba di lingkungan non-produksi heula
- **Panduan Profésional**: Konsultasi sareng profésional kaamanan pikeun panyebaran produksi
- **Dampak Operasional**: Panulis henteu tanggung jawab kana gangguan operasional naon waé
- **Kaamanan Komprehensif**: Ghost mangrupikeun hiji komponén dina strategi kaamanan lengkep

### Dukungan
- **GitHub Issues**: [Laporkeun bug atanapi menta fitur](https://github.com/jimrtyler/Ghost/issues)
- **Dokumentasi**: Paké `Get-Help <function> -Full` pikeun bantuan detil
- **Komunitas**: Forum komunitas PowerShell sareng kaamanan

---

**🔒 Nguatkeun postur kaamanan anjeun ku Ghost - tapi salawasna uji coba heula.**

```powershell
# Mimiti ku evaluasi, sanés asumsi
Get-Ghost
```

**⭐ Béré béntang ka repository ieu upami Ghost ngabantosan ningkatkeun postur kaamanan anjeun!**