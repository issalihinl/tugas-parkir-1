from collections import deque

class Parkir:
    def __init__(self):
        self.parkir = deque()

    def park(self, kendaraan):
        if len(self.parkir) < 10:
            self.parkir.append(kendaraan)
            print(f"Kendaraan {kendaraan} telah diterima untuk parkir.")
        else:
            print("Parkiran penuh. Silakan mencari parkiran lain.")

    def unpark(self):
        if len(self.parkir) > 0:
            kendaraan = self.parkir.popleft()
            print(f"Kendaraan {kendaraan} telah dikeluarkan dari parkir.")
        else:
            print("Tidak ada kendaraan yang dapat dikeluarkan.")

    def status(self):
        if len(self.parkir) > 0:
            print("Kendaraan yang sedang parkir:")
            for i, kendaraan in enumerate(self.parkir, 1):
                print(f"{i}. {kendaraan}")
        else:
            print("Tidak ada kendaraan yang sedang parkir.")

# Contoh penggunaan
park = Parkir()
park.park("Vario")
park.park("H2r")
park.park("Mio")
park.park("Mazda rx7")
park.park("Gtr r34")
park.park("Supra mk4")
park.park("Bmw 30i")
park.status()
park.unpark()
park.status()
