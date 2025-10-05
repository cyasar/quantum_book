# 🧠 KUANTUM HESAPLAMA VE PROGRAMLAMA
### _Matematiksel Temeller ve Uygulamalı Araçlar ile Qiskit 2.0, Cirq ve QuTiP_  

**Editörler:**  
Prof. Dr. İhsan Yılmaz • Prof. Dr. Can Aktaş • Öğr. Gör. Dr. Cumali Yaşar  

---

## 🎯 Proje Amacı  
Bu GitHub deposu, *“Kuantum Hesaplama ve Programlama: Matematiksel Temeller ve Uygulamalı Araçlar ile Qiskit 2.0, Cirq ve QuTiP”* adlı kitabın **uygulamalı kodlarını**, **örnek defterlerini** ve **ek materyallerini** içerir.  
Amaç, kitapta sunulan kuramsal kavramların Python tabanlı kuantum programlama kütüphaneleri aracılığıyla **doğrudan deneyimlenmesini** sağlamaktır.

---

## 📚 İçerik ve Yapı  

| Bölüm | Konu Başlığı | Kod Örnekleri |
|-------|---------------|---------------|
| **I–IV** | Kuantum bilgisayarların temelleri, kompleks sayılar, operatörler ve matris cebiri | `Bolum01_01.ipynb` – `Bolum04_04.ipynb` |
| **V–VII** | Bra-Ket gösterimi, ölçüm ve No-Cloning Teoremi | `Bolum05_00.ipynb` – `Bolum07_02.ipynb` |
| **VIII–X** | Dolanıklık, Bell durumları ve yoğunluk matrisi | `Bolum08_01.ipynb` – `Bolum10_04.ipynb` |
| **XI–XIII** | Teleportasyon, ölçme operatörleri ve bağlılık analizleri | `Bolum11_00.ipynb` – `Bolum13_02.ipynb` |
| **XIV–XV** | Fourier dönüşümü ve kuantum algoritmalar | `Bolum14_01.ipynb` – `Bolum15_09.ipynb` |
| **XVI** | Kuantum Kriptografi (BB84, B92, E91, Grover saldırıları) | `Bolum16_00.ipynb` |
| **XVII** | Kuantum Yürüyüşler ve Simülasyonlar | `Bolum17_00.ipynb` |
| **XVIII** | Qiskit, Cirq ve QuTiP ile Programlama | `Bolum18_*.ipynb` (Qiskit, Cirq, D-Wave örnekleri) |

---

## ⚙️ Kullanılan Teknolojiler  
- **Python 3.10+**  
- **Jupyter Notebook / Jupyter Lab**  
- **Qiskit 2.0**, **Cirq**, **QuTiP**, **D-Wave Ocean SDK**  
- **NumPy**, **Matplotlib**, **SymPy**, **SciPy**

---

## 🧩 Uygulama Örnekleri  

### 🪐 Qiskit – Bell Durumu Oluşturma
```python
from qiskit import QuantumCircuit, transpile, Aer, execute

qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
qc.measure_all()

sim = Aer.get_backend('aer_simulator')
result = execute(qc, sim).result()
print(result.get_counts())
qc.draw('mpl')
```

### 🧬 QuTiP – Hadamard Sonrası Qubit Evrimi
```python
from qutip import *
import numpy as np

H = hadamard_transform(1)
psi0 = basis(2, 0)
psi = H * psi0
print(psi)
plot_bloch_vector(np.real(psi.full()).flatten())
```

### ⚛️ Cirq – Grover Algoritması (Basit Örnek)
```python
import cirq

q0, q1 = cirq.LineQubit.range(2)
circuit = cirq.Circuit(
    cirq.H(q0), cirq.H(q1),
    cirq.CNOT(q0, q1),
    cirq.measure(q0, q1)
)
sim = cirq.Simulator()
print(sim.run(circuit, repetitions=10))
```

---

## 📖 PDF Kaynak  
Kitabın tam metni:  
**KUANTUM BİLGİSAYARLARA GİRİŞ (Holistence Publications, 2025)**  
Bu PDF, her bölümün teorik içeriğini ve matematiksel temellerini kapsamaktadır.  
📄 Dosya: `KUANTUM_BİLGİSAYARLARA_GİRİŞ.pdf`  

Kod defterleri bu içeriğin uygulamalı tamamlayıcısı olarak düzenlenmiştir.

---

## 💡 Kullanım  
1. Depoyu klonla:  
   ```bash
   git clone https://github.com/<kullanıcı_adı>/KuantumBilgisayarlar.git
   cd KuantumBilgisayarlar
   ```
2. Ortamı etkinleştir:  
   ```bash
   pip install -r requirements.txt
   jupyter lab
   ```
3. İlgili bölümün `.ipynb` dosyasını aç ve çalıştır.

---

## 🧾 Lisans  
Bu proje **akademik ve öğretim amaçlı** olarak paylaşılmıştır.  
Kaynak gösterilmek kaydıyla açık erişimdir.  
> © 2025 Holistence Publications • Cumali Yaşar, Arzu Aktaş, Sevdanur Genç, Burak Arslan  

---

## 🌐 İletişim  
📧 cyasar@comu.edu.tr  
🏛️ Çanakkale Onsekiz Mart Üniversitesi  
🔗 [Holistence Publications](http://publications.holistence.com)  
