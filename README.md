ZeroCloud

"The self-hosted, end-to-end encrypted, privacy-first cloud storage system."

ZeroCloud is a production-grade, open-source alternative to Google Drive and Dropbox. It's designed for privacy enthusiasts and professionals who want full control over their data. ZeroCloud focuses on security, modularity, scalability, and privacy while being as easy to deploy as possible.

🧠 Project Purpose

Self-hosted file storage: You control where your data is hosted.

End-to-end encryption: Files are encrypted client-side and decrypted only with your keys.

Scalable and fast: Built using modern async FastAPI, Redis, PostgreSQL, and Docker.

Open-source, modular, and extensible: Fully customizable for any organization or individual use.

Minimal user cost: Architecture and compression focused on minimizing storage overhead.

📐 Technical Stack

Backend: FastAPI, PostgreSQL, Redis, Celery, Tortoise ORM

Frontend: React + Tailwind (Responsive, Mobile First)

Encryption: AES-256 client-side + optional RSA

Deployment: Docker, Docker Compose, Nginx, Gunicorn, Uvicorn

Realtime: WebSockets (for sync notifications), Background Workers (Celery)

Authentication: JWT with refresh tokens (stored in HttpOnly cookies)

Monitoring: Sentry, Prometheus + Grafana (future phases)

🔁 Phase Breakdown

✅ Phase 1: Basic File Storage System (Centralized MVP)

Goal: Build a secure, simple web app to upload, view, download, and delete files.

JWT-based authentication (login, signup).

Frontend + backend for file upload/download.

Store and retrieve file metadata (name, size, type, timestamps).

Responsive UI that works across mobile and desktop.

PostgreSQL database setup for file and user management.

Admin dashboard (basic) for viewing uploaded data.

🔐 Phase 2: End-to-End Encryption

Goal: Add client-side encryption so files are never seen unencrypted by the server.

Encrypt files using AES-256 before sending them.

User keys stored securely on the client side.

Only encrypted blobs stored in the backend.

Decryption happens in-browser only when requested.

Protect metadata and indexes via hashing or encryption.

🔁 Phase 3: Sync Engine & Background Workers

Goal: Enable real-time updates and scalable task processing.

WebSocket-based update channel for live sync.

Device-based sync listeners for changes.

Use Celery + Redis for background processing:

Virus scanning

Compression tasks

Logging and metrics

Sync queue and retry mechanisms.

🔄 Phase 4: Sharing & Permission Management

Goal: Implement user collaboration and secure sharing.

Share files with role-based access (view, edit, etc).

Create secure time-limited links.

Users can revoke access anytime.

Secure encrypted key sharing for shared files.

UI for managing access and permissions.

📦 Phase 5: Performance & Scale

Goal: Optimize backend for large user load.

Implement Redis-based metadata + chunk caching.

Scale horizontally with Nginx load balancer + multiple Gunicorn workers.

Use Docker Compose for full-stack deployment.

Add log aggregation tools + monitoring (e.g., Prometheus).

Add rate limiting, brute force protection, and safe defaults.

Optional: Add server-side configurable compression (e.g., zstd).

🧱 Phase 6: Decentralization & Redundancy (Optional)

Goal: Begin transitioning from centralized to federated or P2P architecture.

Peer-to-peer file sync options (like Syncthing).

Devices become mini-nodes, syncing only among trusted ones.

Server coordination layer optional.

Data redundancy and zero-trust storage model.

Local-first experience with offline cache + background resync.

