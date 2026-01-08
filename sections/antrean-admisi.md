\section{Antrean}

\par \textbf{Antrean} adalah modul yang digunakan untuk mendaftarkan pasien yang telah memiliki nomor tunggu ke dalam sistem antrian berdasarkan lantai, titik pelayanan, dan counter yang tersedia.

\subsection{Mendaftarkan Pasien ke Pemeriksaan TTV}

Langkah-langkah mendaftarkan pasien ke pemeriksaan TTV:

\begin{itemize}
    \item Buka menu \textbf{Antrean} dari menu utama. Halaman \textbf{DAFTAR ANTREAN} akan ditampilkan dengan tab \textbf{Antrean Pelayanan} yang aktif.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=1]{images/pdf/antrean-admisi.pdf}
        \caption{Halaman Daftar Antrean dengan tab Antrean Pelayanan}
        \label{fig:antrean-admisi-1}
        \end{figure}
    \item Pilih lantai pada dropdown \textbf{Lantai}. Dalam contoh ini, \textbf{Lantai 1} dipilih.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=2]{images/pdf/antrean-admisi.pdf}
        \caption{Dropdown Lantai menampilkan pilihan lantai yang tersedia}
        \label{fig:antrean-admisi-2}
        \end{figure}
    \item Pilih titik pelayanan pada dropdown \textbf{Titik Pelayanan}. Opsi yang tersedia adalah \textbf{Admisi}, \textbf{Farmasi}, \textbf{Poli Umum}, dan \textbf{Radiologi}.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=3]{images/pdf/antrean-admisi.pdf}
        \caption{Dropdown Titik Pelayanan menampilkan layanan yang tersedia}
        \label{fig:antrean-admisi-3}
        \end{figure}
    \item Pilih counter pada dropdown \textbf{Counter}. Counter yang tersedia bergantung pada titik pelayanan yang dipilih, misalnya \textbf{Pendaftaran HD}, \textbf{Pendaftaran IGD}, \textbf{Pendaftaran Poli Umum}, dan \textbf{Pendaftaran Rujukan}.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=4]{images/pdf/antrean-admisi.pdf}
        \caption{Dropdown Counter menampilkan counter sesuai titik pelayanan}
        \label{fig:antrean-admisi-4}
        \end{figure}
    \item Masukkan nomor tunggu pasien pada field \textbf{Masukan Nomor Tunggu}. Nomor tunggu adalah nomor yang telah diterima pasien saat pendaftaran awal.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=6]{images/pdf/antrean-admisi.pdf}
        \caption{Field untuk memasukkan nomor tunggu pasien}
        \label{fig:antrean-admisi-6}
        \end{figure}
    \item Klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=5]{images/pdf/antrean-admisi.pdf}}}$ untuk menyimpan pendaftaran antrian. Sistem akan memproses dan menampilkan notifikasi sukses beserta data pasien yang telah didaftarkan.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=7]{images/pdf/antrean-admisi.pdf}
        \caption{Notifikasi berhasil dan data pasien dalam antrian yang sudah terdaftar}
        \label{fig:antrean-admisi-7}
        \end{figure}
\end{itemize}

\subsection{Pemanggil Antrean TTV}

Langkah-langkah perawat untuk memanggil dan melayani pasien yang telah terdaftar dalam antrian:

\begin{itemize}
    \item Buka modul \textbf{Antrean} dari menu utama. Halaman akan menampilkan daftar antrian dengan pasien-pasien yang telah didaftarkan oleh admisi. Setiap pasien dalam antrian memiliki tombol \textbf{Panggil} yang siap untuk dipilih.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=8]{images/pdf/pemanggil-antrean-ttv.pdf}
        \caption{Halaman Antrian dengan daftar pasien terdaftar dan tombol Panggil}
        \label{fig:pemanggil-antrean-ttv-8}
        \end{figure}
    \item Klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=9]{images/pdf/pemanggil-antrean-ttv.pdf}}}$ pada pasien yang akan dilayani untuk memanggil pasien tersebut.

    \item Setelah pasien dipanggil, sistem akan menampilkan detail informasi pasien beserta tiga opsi aksi: \textbf{Panggil}, \textbf{Selanjutnya}, dan \textbf{Mulai Pelayanan}.
        \begin{figure}[H]
        \centering
            \includegraphics[width=\textwidth,page=10]{images/pdf/pemanggil-antrean-ttv.pdf}
        \caption{Detil pasien terpanggil dengan opsi aksi yang tersedia}
        \label{fig:pemanggil-antrean-ttv-10}
        \end{figure}

    \item Untuk melewati pasien ke antrian berikutnya, klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=11]{images/pdf/pemanggil-antrean-ttv.pdf}}}$. Pasien yang dilewati akan ditempatkan di akhir antrian dan dapat dipanggil kembali hingga 3 kali sebelum dipindahkan secara otomatis.

    \item Untuk memulai pemeriksaan TTV, klik tombol $\vcenter{\hbox{\includegraphics[height=.6cm, page=12]{images/pdf/pemanggil-antrean-ttv.pdf}}}$. Sistem akan membawa ke halaman pemeriksaan TTV untuk pasien yang terpilih.
\end{itemize}

\begin{mdframed}[backgroundcolor=yellow!20]
\textbf{Catatan:} Jika pasien dilewati (dengan tombol \textbf{Selanjutnya}), pasien akan ditempatkan di bawah antrian. Jika pasien dilewati sebanyak 3 kali oleh pasien lain dalam antrian, pasien akan secara otomatis dipindahkan ke status tertentu.
\end{mdframed}
