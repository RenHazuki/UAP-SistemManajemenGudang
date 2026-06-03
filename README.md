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
            
# UPDATE 5
def update():
    try:
        index = listbox.curselection()[0]
        data_barang[index].id_barang = entry_id.get()
        data_barang[index].nama = entry_nama.get()
        data_barang[index].stok = entry_stok.get()

        riwayat.append("Update Data")

        tampilkan()

        clear_entry()
    except:
        messagebox.showerror(
            "Error",
            "Pilih data terlebih dahulu"
        )

# DELETE 6
 def hapus():
     try:
         index = listbox.curselection()[0]
         nama = data_barang[index].nama
         data_barang.pop(index)
         riwayat.append(f"Hapus {nama}")

         tampilkan()

         clear_entry()

     except:
         messagebox.showerror(
             "Error",
             "Pilih data terlebih dahulu"
         )

# SEARCHING 7
  def cari():
      keyword = entry_cari.get().lower()
      listbox.delete(0, END)
      
      for barang in data_barang:
          if (
              keyword in barang.id_barang.lower()
              or
              keyword in barang.nama.lower()
          ):

              listbox.insert(
                  END,
                  f"ID: {barang.id_barang} | "
                  f"Nama: {barang.nama} | "
                  f"Stok: {barang.stok}"
              )
# SORTING 8
def sorting():
    n = len(data_barang)

    for i in range(n):
        for j in range(0, n - i - 1):
            if (
                data_barang[j].id_barang >
                data_barang{j + 1].id_barang
            ):
                data_barang[j], data_barang[j + 1] = (
                    data_barang[j + 1],
                    data_barang[j]
                )
    tampilkan()
      
 
    



