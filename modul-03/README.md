\documentclass[12pt, a4paper]{article}
\usepackage[utf8]{utf8}
\usepackage[margin=1in]{geometry}
\usepackage{amsmath, amssymb}
\usepackage{listings}
\usepackage{xcolor}
\usepackage{hyperref}

% Pengaturan warna dan tampilan blok kode (syntax highlighting)
\definecolor{codegreen}{rgb}{0,0.6,0}
\definecolor{codegray}{rgb}{0.5,0.5,0.5}
\definecolor{codepurple}{rgb}{0.58,0,0.82}
\definecolor{backcolour}{rgb}{0.96,0.96,0.96}

\lstdefinestyle{pythonstyle}{
    backgroundcolor=\color{backcolour},   
    commentstyle=\color{codegreen},
    keywordstyle=\color{magenta},
    numberstyle=\tiny\color{codegray},
    stringstyle=\color{codepurple},
    basicstyle=\ttfamily\small,
    breakatwhitespace=false,         
    breaklines=true,                 
    captionpos=b,                    
    keepspaces=true,                 
    numbers=left,                    
    numbersep=5pt,                  
    showspaces=false,                
    showstringspaces=false,
    showtabs=false,                  
    tabsize=4
}

\lstset{style=pythonstyle}

\title{\textbf{Modul Praktikum 2}\\Mencari Faktor Bilangan}
\author{Petunjuk Pengerjaan \& Hint Pemrograman}
\date{}

\begin{document}

\maketitle

Modul praktikum ini bertujuan untuk membuat program pencari faktor dari suatu bilangan bulat positif kurang dari $100$. Program akan berjalan secara berulang untuk menerima input angka dan menampilkan daftar faktornya hingga pengguna memasukkan angka $0$.

\section{Deskripsi Tugas}
Membuat program interaktif untuk mencari seluruh faktor dari suatu bilangan.
\begin{itemize}
    \item \textbf{Contoh:}
    \begin{itemize}
        \item Bilangan $15 \rightarrow$ faktornya adalah: $1, 3, 5, 15$.
        \item Bilangan $24 \rightarrow$ faktornya adalah: $1, 2, 3, 4, 6, 8, 12, 24$.
    \end{itemize}
    \item \textbf{Ketentuan Khusus:} Wajib menggunakan tipe data \texttt{list} untuk menyimpan daftar faktor bilangan yang ditemukan.
\end{itemize}

\section{Hint Sintaks \& Komponen Coding}
Berikut adalah komponen dan konsep pemrograman Python yang perlu diterapkan dalam kode program:

\begin{enumerate}
    \item \textbf{Format Pencetakan (\texttt{print} format)} \\
    Digunakan untuk menampilkan \emph{header} identitas (Nama dan NRM) serta pesan luaran.
    \begin{itemize}
        \item \emph{Hint:} Gunakan f-string (misalnya \texttt{f"Bilangan \{bil\} Faktornya = \{faktor\}"}) agar penggabungan teks dan variabel lebih rapi.
    \end{itemize}

    \item \textbf{Perulangan Utama (\texttt{while} / \texttt{do-while} loop)} \\
    Digunakan agar program dapat terus meminta input bilangan dari pengguna secara berulang.
    \begin{itemize}
        \item \emph{Hint:} Gunakan perulangan \texttt{while True:} dan tambahkan kondisi penghentian (\texttt{break}) saat pengguna memasukkan angka $0$.
    \end{itemize}

    \item \textbf{Tipe Data \& Manipulasi List (\texttt{list})} \\
    Digunakan untuk menampung seluruh faktor dari bilangan yang diinput.
    \begin{itemize}
        \item \emph{Hint:} Inisialisasi \emph{list} kosong (misal: \texttt{faktor = []}) di dalam \emph{loop} input agar \emph{list} direset setiap kali ada input angka baru. Gunakan metode \texttt{.append()} untuk menambahkan faktor yang ditemukan.
    \end{itemize}

    \item \textbf{Operasi Sisa Bagi / Modulo (\%)} \\
    Digunakan untuk mengecek apakah suatu angka pembagi merupakan faktor dari bilangan yang diuji.
    \begin{itemize}
        \item \emph{Hint:} Suatu angka $i$ adalah faktor dari $\text{bilangan}$ jika:
        $$\text{bilangan} \pmod i == 0$$
    \end{itemize}

    \item \textbf{Perulangan Iterasi Faktor (\texttt{for} loop)} \\
    Digunakan untuk menguji seluruh kandidat pembagi dari $1$ sampai sebesar $\text{bilangan}$.
    \begin{itemize}
        \item \emph{Hint:} Gunakan fungsi \texttt{range(1, bilangan + 1)} untuk menguji setiap angka pembagi.
    \end{itemize}

    \item \textbf{Input Handling (\texttt{input()} \& \texttt{int()})} \\
    Digunakan untuk menerima masukan dari pengguna dan mengonversinya menjadi tipe data bilangan bulat (integer).
\end{enumerate}

\section{Hint Alur Logika Pemrograman (Pseudocode)}
\begin{enumerate}
    \item Tampilkan identitas Nama dan NRM di bagian awal program.
    \item Jalankan perulangan \texttt{while}:
    \begin{enumerate}
        \item Minta masukan angka dari pengguna (\texttt{Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = }).
        \item Periksa apakah angka masukan bernilai $0$:
        \begin{itemize}
            \item Jika bernilai $0$, cetak \texttt{*SELESAI*} dan hentikan perulangan (\texttt{break}).
        \end{itemize}
        \item Buat variabel \emph{list} kosong untuk menampung faktor.
        \item Jalankan perulangan \texttt{for} dari $1$ hingga angka yang dimasukkan pengguna:
        \begin{itemize}
            \item Jika angka masukan habis dibagi angka iterasi ($\text{sisa bagi} == 0$), masukkan angka iterasi tersebut ke dalam \emph{list} faktor menggunakan \texttt{.append()}.
        \end{itemize}
        \item Tampilkan hasil bilangan beserta \emph{list} faktor yang didapatkan.
    \end{enumerate}
\end{enumerate}

\section{Contoh Luaran (Output) Program}

\begin{lstlisting}[language=bash]
Program Faktor Bilangan
Nama : [Nama Praktikan]
NRM  : [NRM Praktikan]

Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 15
Bilangan 15 Faktornya = [1, 3, 5, 15]

Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 24
Bilangan 24 Faktornya = [1, 2, 3, 4, 6, 8, 12, 24]

Masukan sembarang bilangan <100 (masukan 0 untuk selesai) = 0
*SELESAI*
\end{lstlisting}

\end{document}
