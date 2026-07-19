# 🧠 Ringkasan: LLM Wiki (Andrej Karpathy)

Pola untuk membangun basis pengetahuan personal yang dikelola oleh LLM secara inkremental dan persisten.

## 💡 Konsep Utama
Alih-alih hanya menggunakan RAG (pengambilan data mentah saat bertanya), LLM secara aktif membangun **Wiki** (markdown) dari sumber dokumen. Pengetahuan dikompilasi satu kali dan terus diperbarui, bukan diturunkan ulang setiap kali ada pertanyaan.

## 🏗️ Arsitektur (3 Lapisan)
1.  **Raw Sources**: Koleksi dokumen sumber (artikel, paper, dll) yang tidak dapat diubah (immutable).
2.  **The Wiki**: Direktori file markdown yang dibuat oleh LLM (ringkasan, entitas, konsep).
3.  **The Schema**: Dokumen panduan (`AGENTS.md`) yang memberi tahu LLM cara mengelola wiki.

## ⚙️ Operasi Utama
*   **Ingest**: Menambahkan sumber baru, LLM membaca dan memperbarui 10-15 halaman wiki terkait.
*   **Query**: Bertanya ke wiki, LLM mensintesis jawaban dengan sitasi. Jawaban bagus bisa disimpan kembali ke wiki.
*   **Lint**: Pemeriksaan kesehatan berkala untuk menemukan kontradiksi, klaim basi, atau halaman yatim (tanpa link).

## 🗂️ Navigasi
*   `index.md`: Katalog berorientasi konten (link + ringkasan satu baris).
*   `log.md`: Catatan kronologis semua aktivitas (ingest, query, lint).

## 🚀 Mengapa Ini Berhasil?
LLM menangani beban administratif (bookkeeping) yang biasanya membuat manusia malas memelihara wiki. Manusia tetap fokus pada kurasi sumber dan arah analisis.
