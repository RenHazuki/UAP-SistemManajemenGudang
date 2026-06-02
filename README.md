# UAP-SistemManajemenGudang
# Kelompok 4 UAP

# COLECTION FRAMEWORK 1

data_barang = [] #list
riawayat = [] #stack
antrian = [] #Queue
kategori_set = set() #set
barang_dict = {} #dictionary

# OOP 2

class Barang:
     def __init__(self,id_barang,nama,stok):
     self.id_barang = id_barang
     self.nama = nama 
     self.stok = stok

# CREATE 3

def tambah():

    id_barang = entry_id.get()
    nama = entry_nama.get()
    stok = entry_stok.get()

    if id_barang == "" or nama == "" or stok == "":
        messagebox.showerror(
           "error"
           "data tidak boleh kosong"
        )
        return

    barang = Barang(
        id_barang,
        nama,
        stok
    )

    #list
    data_barang.append(barang)

    #stack
    riwayat.append(f"tambah{nama}")

    #queue
    antrian.append(nama)

    #set 
    kategori_set.add(nama)

    #dictionary
    barang_dict[id_barang] = nama 

    tampilkan()

    clear_entry()

# READ 4

def tampilkan():

    listbox.delete(0, END)

    for barang in data_barang:

        listbox.insert(
            END, 
            f"ID: {barang.id_barang} | "
            f"Nama: {barang.nama} | "
            f"Stok : {barang.stok} | "
    )
            

        
    



