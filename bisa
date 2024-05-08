import streamlit as st

def konfigurasi_elektron(nomor_atom):
    konfigurasi = ""
    elektron = nomor_atom
    shell = 1
    while elektron > 0:
        max_elektron_shell = 2 * shell ** 2
        if elektron >= max_elektron_shell:
            konfigurasi += "{}{} ".format(shell, "s" if shell == 1 else "p")
            elektron -= max_elektron_shell
        else:
            subshell = elektron // (shell ** 2)
            remainder = elektron % (shell ** 2)
            if subshell > 0:
                konfigurasi += "{}{}{} ".format(shell, "s" if shell == 1 else "p", subshell)
            if remainder > 0:
                konfigurasi += "{}{}{} ".format(shell, "s" if shell == 1 else "p", subshell + 1)
            elektron = 0
        shell += 1
    return konfigurasi.strip()

def generate_konfigurasi(nomor_mulai, nomor_akhir):
    hasil = {}
    for nomor_atom in range(nomor_mulai, nomor_akhir + 1):
        hasil[nomor_atom] = konfigurasi_elektron(nomor_atom)
    return hasil

konfigurasi_semua_atom = generate_konfigurasi(1, 118)
for nomor_atom, konfigurasi in konfigurasi_semua_atom.items():
    print("Nomor atom:", nomor_atom, "-> Konfigurasi elektron:", konfigurasi)