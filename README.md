# Deploy DB dengan Docker Compose

## Overview

Pada repo ini terdapat 3 services:

- Redis
- Seeder: Untuk menginisiasi data pada redis
- MongoDB

## Requirements

- VM dengan Docker dan Docker Compose terinstal.
- Firewall pada VM harus mengizinkan traffic ingress pada port `6379` dan `27017`.

## Deployment Steps

1. **Konfigurasi Producer**

   - Pastikan environment variables pada `docker-compose.yaml` sudah benar.

2. **Menjalankan Producer**

   - Navigasikan ke direktori tempat file `docker-compose.yaml` berada.
   - Jalankan perintah berikut untuk mendeploy 3 layanan sekaligus:

     ```sh
     docker-compose up -d
     ```

   - Jalankan perintah berikut untuk mendeploy layanan redis saja:

   ```sh
   docker-compose -f docker-compose.redis.yaml up -d
   ```

   - Jalankan perintah berikut untuk mendeploy layanan mongodb saja:

   ```sh
   docker-compose -f docker-compose.mongodb.yaml up -d
   ```

   - Jalankan perintah berikut untuk mendeploy layanan seeder saja:

   ```sh
   docker-compose -f docker-compose.seeder.yaml up -d
   ```

   - Periksa status container untuk memastikan layanan berjalan dengan baik:

     ```sh
     docker-compose ps
     ```
