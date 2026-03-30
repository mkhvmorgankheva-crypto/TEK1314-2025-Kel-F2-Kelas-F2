# 📄 Baseline Report - Phase 1: Hardening Review  
**Kelompok 7 - Kelas F2**  
**Mata Kuliah**: TEK1314 Keamanan Siber  
**Tanggal**: 31/03/2026

---

## 1. Pendahuluan

### 1.1 Tujuan Hardening  
Tujuan dari implementasi hardening pada infrastruktur lab ini adalah untuk meningkatkan keamanan layanan DNS dari berbagai ancaman seperti DNS Spoofing dan DNS Tunneling. Hardening dilakukan untuk memastikan sistem mampu mendeteksi, mencegah, dan memonitor aktivitas mencurigakan yang terjadi pada jaringan.

---

### 1.2 Ringkasan Infrastruktur  
- **Network Subnet**: `192.168.70.0/24`  
- **Jumlah VM**: 3 sistem  
- **Skenario**: DNS Defense System  
- **Attack Type**: DNS Spoofing & DNS Tunneling  
- **Service**: DNS Server (Port 53 TCP/UDP)  

---

### 1.3 Standar Keamanan  
Standar keamanan yang digunakan mengacu pada:
- Principle of Least Privilege  
- Network Segmentation  
- Secure DNS Configuration Best Practice  
- Monitoring & Logging menggunakan SIEM (Security Onion)  

---

## 2. Network Hardening

### 2.1 Topologi Jaringan  
![Topologi Jaringan](assets/01-topology.png)

**Deskripsi Topologi**:  
Topologi jaringan terdiri dari satu router sebagai gateway utama yang menghubungkan tiga sistem dalam satu subnet melalui switch (LAN), yaitu:
- Attacker Machine (Client)  
- DNS Server  
- Security Onion (Monitoring)  

Semua komunikasi DNS berjalan melalui port `53` dan dimonitor oleh Security Onion.

---

### 2.2 Konfigurasi Firewall  

#### 2.2.1 DNS Server (Target - 192.168.70.10)  
**Firewall**: UFW  
**Status**: Aktif  

**Aturan yang Diterapkan**:
```bash
sudo ufw status verbose
