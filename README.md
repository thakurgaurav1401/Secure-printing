🔐 Secure Cybercafe Upload Client

A lightweight, single-file HTML5 web application that enables customers to securely upload documents to cybercafes using end-to-end encryption. Built with modern Web Crypto API standards and designed to work seamlessly with Flutter Desktop receivers.

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?logo=tailwind-css&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?logo=supabase&logoColor=white)

✨ Features

🔒 End-to-End Encryption**: AES-256-CBC file encryption with RSA-OAEP-256 key wrapping
📱 Mobile-First Design**: Responsive Tailwind CSS interface optimized for all devices
🎯 Drag & Drop**: Intuitive file upload with visual feedback
📊 Real-Time Progress**: Live upload progress with status messages
🚨 Confidential Mode**: Mark sensitive documents with special handling flag
⚡ Zero Dependencies**: Single HTML file with CDN-based libraries
🔐 RLS Compliant**: Supabase Row Level Security compatible storage paths

🛠️ Tech Stack

Frontend: HTML5, Tailwind CSS (CDN)
Encryption: Web Crypto API (native `window.crypto.subtle`) [web:1]
Backend: Supabase (Storage + PostgreSQL)
Crypto Standards:
  - AES-256-CBC with PKCS7 padding
  - RSA-OAEP with SHA-256 hash [web:5]

🏗️ Architecture

 Encryption Flow

1.Key Generation: Generate random 32-byte AES key + 16-byte IV
2.File Encryption: Encrypt document using AES-256-CBC
3.Key Wrapping: Encrypt AES key with cafe's RSA public key (OAEP padding)
4.Upload: Store encrypted file in Supabase Storage
5.Metadata: Insert job details with Base64-encoded encrypted key and IV

Database Schema

