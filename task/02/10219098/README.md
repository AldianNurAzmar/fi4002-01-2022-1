# 10219098
Aldian Nur Azmar


## materi sebelumnya
+ Penggunaan dan Visualisasi Metode Runge-Kutta
+ Penggunaan dan Visualisasi Metode Predator Prey
+ Penggunaan dan Visualisasi Metode Euler
+ Penggunaan dan Visualisasi Metode Monte Carlo
+ Penggunaan Random Number Machine
+ Metode Machine Learning


## materi paling menarik
+ Penggunaan dan Visualisasi Metode Runge-Kutta, karena dalam Metode Runge-Kutta dapat menyelesaikan bentuk persamaan diferensial biasa baik dalam bentuk linear atau polynomial, metode tersebut juga dapat dikatakan sebagai metode untuk menyelesaikan persamaan matematika yang kompleks yang telah dimodelkan dalam bentuk persamaan diferensial. Penggunaan Random Number Machine juga sangat menarik karena penggunaan random number di dalam dunia nyata sangat aplikatif dan memiliki banyak manfaat, baik dalam membuat sistem keamanan dan membuat suatu kode tertentu untuk suatu sistem yang kompleks.


## materi paling membosankan
+ Menurut saya, dalam perkuliahan ini tidak ada materi yang membosankan, karena setiap metode yang diajarkan dalam perkuliahan ini merupakan suatu hal yang baru bagi saya, serta metode-metode tersebut sangat aplikatif untuk menyelesaikan suatu persoalan matematika yang sulit dan dapat menyederhanakan suatu persoalan yang kompleks, visualisasi untuk setiap materi yang diberikan sangat bagus dan menarik.


## materi yang sudah dipami
+ Materi yang sudah saya pahami diantaranya adalah materi penggunaan Metode Runge-Kutta dan Metode Predator Prey karena metode tersebut banyak digunakan disetiap tugas yang diberikan, Metode Euler dan Metode Monte Carlo karena metode tersebut pernah dipelajari pada perkuliahan atau mata kuliah yang telah diambil sebelumnya seperti dalam Fisika Matematika.


## materi yang belum dipahami
+ Materi yang belum saya pahami yaitu materi pada beberapa minggu terakhir terkait penggunaan random number machine dan penggunaan metode machine learning. Dalam hal ini, secara teori saya paham mengenai kedua hal tersebut, tetapi secara teknikal saya masih sangat sulit untuk mengimplementasikan kedua hal tersebut. Hal tersebut mungkin dikarenakan saya masih kurang melakukan latihan terkait hal tersebut dan masih kurang dalam melakukan eksplorasi lebih dalam, serta saya masih berada pada titik awal untuk mendalami hal tersebut.


## contoh program
+ Buat suatu contoh program dalam Python dan sertakan di sini dengan hasil keluarnnya.

```python
# contoh program python
import matplotlib.pyplot as plt
import pandas as pd
import warnings
warnings.filterwarnings("ignore")

def f1(t,x,y):
    return y

def k1(i):
    x=x0
    y1=y[0]
    y2=y[1]
    if i==0:
        return h*f1(x,y1,y2)
    else:
        return h*f2(x,y1,y2)
        
def k2(i):
    x=x0
    y1=y[0]+k1(0)/2
    y2=y[1]+k1(1)/2
    if i==0:
        return h*f1(x,y1,y2)
    else:
        return h*f2(x,y1,y2)

def k3(i):
    x=x0
    y1=y[0]+k2(0)/2
    y2=y[1]+k2(1)/2
    if i==0:
        return h*f1(x,y1,y2)
    else:
        return h*f2(x,y1,y2)
        
def k4(i):
    x=x0
    y1=y[0]+k3(0)
    y2=y[1]+k3(1)
    if i==0:
        return h*f1(x,y1,y2)
    else:
        return h*f2(x,y1,y2)


df0 = pd.DataFrame (columns=["t","x","v"])

def f2(t,x,y):
    return (-20*x)/20

x0 = 0
y = [1,0]
xf = 15
h = 0.1

new_row={"t":x0,"x":y[0], "v":y[1]}
df0= df0.append(new_row, ignore_index= True)

iter = int(xf/h)
for a in range(0,iter):
    hasil1 = y[0]+(k1(0)+2*(k2(0)+k3(0))+k4(0))/6
    hasil2 = y[1]+(k1(1)+2*(k2(1)+k3(1))+k4(1))/6
    y[0] = hasil1
    y[1] = hasil2
    x0 = x0+h
    new_row={"t":x0,"x":y[0], "v":y[1]}
    df0= df0.append(new_row, ignore_index= True)


df1 = pd.DataFrame (columns=["t","x","v"])

def f2(t,x,y):
    return (-5*y - 20*x)/20

x0 = 0
y = [1,0]
xf = 15
h = 0.1

new_row={"t":x0,"x":y[0], "v":y[1]}
df1= df1.append(new_row, ignore_index= True)

iter = int(xf/h)
for a in range(0,iter):
    hasil1 = y[0]+(k1(0)+2*(k2(0)+k3(0))+k4(0))/6
    hasil2 = y[1]+(k1(1)+2*(k2(1)+k3(1))+k4(1))/6
    y[0] = hasil1
    y[1] = hasil2
    x0 = x0+h
    new_row={"t":x0,"x":y[0], "v":y[1]}
    df1= df1.append(new_row, ignore_index= True)
    
    
df2 = pd.DataFrame (columns=["t","x","v"])

def f2(t,x,y):
    return -2*y-x

x0 = 0
y = [1,0]
xf = 15
h = 0.1

new_row={"t":x0,"x":y[0], "v":y[1]}
df2= df2.append(new_row, ignore_index= True)

iter = int(xf/h)
for a in range(0,iter):
    hasil1 = y[0]+(k1(0)+2*(k2(0)+k3(0))+k4(0))/6
    hasil2 = y[1]+(k1(1)+2*(k2(1)+k3(1))+k4(1))/6
    y[0] = hasil1
    y[1] = hasil2
    x0 = x0+h
    new_row={"t":x0,"x":y[0], "v":y[1]}
    df2= df2.append(new_row, ignore_index= True)
    
    
df3 = pd.DataFrame (columns=["t","x","v"])

def f2(t,x,y):
    return -10*y-x

x0 = 0
y = [1,0]
xf = 15
h = 0.1

new_row={"t":x0,"x":y[0], "v":y[1]}
df3= df3.append(new_row, ignore_index= True)

iter = int(xf/h)
for a in range(0,iter):
    hasil1 = y[0]+(k1(0)+2*(k2(0)+k3(0))+k4(0))/6
    hasil2 = y[1]+(k1(1)+2*(k2(1)+k3(1))+k4(1))/6
    y[0] = hasil1
    y[1] = hasil2
    x0 = x0+h
    new_row={"t":x0,"x":y[0], "v":y[1]}
    df3= df3.append(new_row, ignore_index= True)
    
df0123 = pd.DataFrame (columns=["t","x_periodik","x_under","x_critical","x_over"])
df0123.t = df1.t
df0123.x_periodik = df0.x
df0123.x_under = df1.x
df0123.x_critical = df2.x
df0123.x_over = df3.x
print(df0123)

fig, ax = plt.subplots(figsize=(12,8))
data_x = df0123.t
data_y0 = df0123.x_periodik
data_y1 = df0123.x_under
data_y2 = df0123.x_critical
data_y3 = df0123.x_over

ax.plot(data_x,data_y0, label='Periodik')
ax.plot(data_x,data_y1, label='Underdamped')
ax.plot(data_x,data_y2, label='Critical damped')
ax.plot(data_x,data_y3, label='Overdamped')

plt.rc('axes', labelsize =15)
plt.rc('xtick', labelsize =12)
plt.rc('ytick', labelsize =12)
plt.rc('legend', fontsize =15)

ax.set_xlabel('Waktu, t(s)')
ax.set_ylabel('Perpindahan, x(t)')

plt.legend()
plt.grid()
plt.show()
plt.savefig('Figure (1) Grafik Osilasi Teredam.png')
```

Hasilnya adalah

```
![alt text](https://github.com/AldianNurAzmar/fi4002-01-2022-1/blob/main/task/02/10219098/Figure%20(1)%20Grafik%20Osilasi%20Teredam.jpg?raw=true)
```


## cara perkuliahan
+ Tuliskan pendapat Anda mengenai cara perkuliahan selama ini dan cantumkan usulan untuk perkuliahan setelah UTS.


## topik sistem fisis
+ Tuliskan sistem fisis yang menarik bagi Anda untuk dikaji lebih dalam dan jelaskan alasannya mengapa.


## simulasi dan visualisasi
+ Apakah Anda tertarik dengan simulasi dan visualisasi? Jelaskan topik yang ingin Anda simulasikan / visualisasikan serta cantumkan alasannya dan perkiraan pusataka Python yang perlu digunakan.
