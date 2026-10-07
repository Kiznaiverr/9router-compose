# 9Router with Cloudflare Zero Trust

Setup 9Router tanpa Headroom (hemat resource) dan tanpa expose port host. Akses hanya via Cloudflare Tunnel.

## Setup

1. Buat Tunnel di Cloudflare Zero Trust:
   - Masuk ke Zero Trust Dashboard -> **Networks** -> **Tunnels** -> **Create a tunnel**.
   - Pilih **Cloudflared**.
   - Simpan nama tunnel, salin `TUNNEL_TOKEN`.
   - Di tab **Public Hostname**:
     - Service Type: `HTTP`
     - URL: `9router:20128`

2. Siapkan file `.env`:
   ```bash
   cp .env.example .env
   ```
   Isi `TUNNEL_TOKEN`, `JWT_SECRET`, dan `INITIAL_PASSWORD`.

3. Jalankan container:
   ```bash
   docker compose up -d
   ```
