# KursPython
Podstawowy kurs dla analityków i ekonomistów z wykorzystaniem Pythona. 

Celem niniejszego kursu jest nauka podstaw programowania w języku Python i obsługa najczęściej wykorzystywanych bibliotek w analizie danych.

Poniżej znajduje się instrukcja instalacji śrtodowiska Python, które będzie wykorzystywane w tym kursie.

## Instalacja środowiska Python w systemie Windows/OS X

Środowisko Python można zainstalować bezpośrednio korzystając z instalatora dostępnego na stronie Python.org: https://www.python.org/downloads/ lub korzystając ze zintegrowanego rozwiązania jakim jest conda (http://conda.pydata.org/docs/intro.html).

Dla początkujących użytkowników wykorzystanie condy jest znacznie łatwiejsze, ponieważ nie wymaga instalowania i konfigurowania kompilatora oraz bibliotek BLAS. Poniższy poradnik opisuje ten sposób instalacji.

### (Ana)conda - instalacja

Conda jest menedżerem pakietów Pythona, który ułatwia nam ich instalację oraz utrzymanie kompatybilnych wersji. Domyślnie wykorzystuje repozytorium pakietów dostarczanych przez Continuum Analytics (https://www.continuum.io/).

Rozpoczniemy od instalacji minimalnego środowiska Conda (http://conda.pydata.org/miniconda.html).

Niniejszy kurs Pythona oparty będzie o wersję 3. Pobieramy stosowną dla naszego systemu operacyjnego wersję (32 lub 64-bitową), np. "64-bit (exe installer)" w kolumnie Windows i wierszu Python 3.5.

Uruchamiamy instalator. W przypadku OS X konieczne jest uruchomienie skryptu w terminalu (np. bash Miniconda3-latest-Linux-x86_64.sh).

W instalatorze wszystkie opcje powinny być domyślnie ustawione poprawnie (warto jednak przeczytać informację na kolejnych ekranach, gdyż wersja instalatora może ulec zmianie od momentu powstania tego poradnika). Wygodniejsza może być instalacja dla wszystkich użytkowników systemu. Zwracamy uwagę na to aby dodane zostały ścieżki PATH w systemie Windows. Dodatkowo ewentualnie odhaczamy „learn more aboud Anaconda Cloud”.
W systemie OS X konieczne może być ponowne uruchomienie terminala po instalacji.

Pełny proces konfiguracji condy i instalacji podstawowych pakietów sprowadza się do czterech poleceń z odpowiednimi uprawnieniami*:

Aktualizacji silnika:
```
conda update conda
```
Stworzenia nowego środowiska:
```
conda create --name myPython python=3.5
```
Aktywacji danego środowiska:
```
activate myPython   (W systemie OS X: source activate myPython )
```
Zainstalowania niezbędnych pakietów:
```
conda install pandas numpy jupyter cython bottleneck numexpr openpyxl lxml xlrd xlwt pytables nose
```


*Uprawnienia administratora
* W przypadku systemu Windows: Uruchamiamy wiersz poleceń z prawami administratora (Start > „cmd” > prawym klawiszem „uruchom jako administrator”).
* Dla OS X może być konieczne wykonywanie poleceń z uprawnieniami root'a (su)

Poniżej ("Przykładowa instalacja") zilustrowane zostało wykonanie powyższych poleceń w systemie Windows. Konfiguracja w systemie OS X przebiega analogicznie. Pomyślne wykonanie powyższych poleceń pozwoli nam uzyskać poprawnie działające środowisko Pythona z obsługą notebooków oraz zainstalowanymi pakietami Numpy i Pandas.


### Pierwsze uruchomienie

Przed pierwszym uruchomieniem warto utworzyć roboczy folder na potrzeby kursu. Przykładowo: "C:\Users\Maciej Wilamowski\pythonKurs". W folderze warto zapisać pliki kursu bezpośrednio z githuba (np. prawy klawisz na pliku "0_Test_instalacji.ipynb" i zapisz jako lub pobranie całego repozytorium).

Za każdym razem pracę z Pythonem będziemy rozpoczynać w ten sam sposób. Ostatnie z poleceń powinno uruchomić naszą domyślną przeglądarkę internetową. Wyświetlona strona powinna zawierać listę plików i podfolderów w wybranym katalogu ("C:\Users\Maciej Wilamowski\pythonKurs" w poniższym przykładzie).

Po uruchomieniu wiersza poleceń/konsoli:
```
activate myPython   (W systemie OS X: source activate myPython )
cd "C:\Users\Maciej Wilamowski\pythonKurs"
jupyter notebook
```
Jeżeli wszystko przebiegło pomyślnie możemy przetestować naszą instalację uruchamiając notatnik "0_Test_instalacji.ipynb".

### Przykładowa instalacja w systemie Windows
#### Konfiguracja środowiska
*UWAGA: przytoczone poniżej wyniki poleceń mogą się nieznacznie różnić. Zostają przytoczone poniżej aby ułatwić sprawdzenie poprawności wykonywania poleceń.*


**W pierwszej kolejności aktualizujemy nasz menedżer pakietów poleceniem:**

```
conda update conda

Microsoft Windows [Version 10.0.14393]
(c) 2016 Microsoft Corporation. All rights reserved.

C:\WINDOWS\system32>conda update conda
Fetching package metadata .........
Solving package specifications: ..........

Package plan for installation in environment C:\Program Files\Miniconda3:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    conda-4.2.13               |           py35_0         449 KB

The following packages will be UPDATED:

    conda: 4.2.12-py35_0 --> 4.2.13-py35_0

Proceed ([y]/n)?

Fetching packages ...
conda-4.2.13-p 100% |###############################| Time: 0:00:00   5.23 MB/s
Extracting packages ...
[      COMPLETE      ]|##################################################| 100%
Unlinking packages ...
[      COMPLETE      ]|##################################################| 100%
Linking packages ...
[      COMPLETE      ]|##################################################| 100%
```

**Następnie warto stworzyć nowe środowisko, aby domyślne pozostawić w stanie niezmienionym (możemy wybrać dowolną nazwę środowiska, np. "myPython":**

```
conda create --name myPython python=3.5

C:\WINDOWS\system32>conda create --name myPython python=3.5
Fetching package metadata .........
Solving package specifications: ..........

Package plan for installation in environment C:\Program Files\Miniconda3\envs\myPython:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    pip-9.0.1                  |           py35_1         1.7 MB

The following NEW packages will be INSTALLED:

    pip:            9.0.1-py35_1
    python:         3.5.2-0
    setuptools:     27.2.0-py35_1
    vs2015_runtime: 14.0.25123-0
    wheel:          0.29.0-py35_0

Proceed ([y]/n)?

Fetching packages ...
pip-9.0.1-py35 100% |###############################| Time: 0:00:00   6.91 MB/s
Extracting packages ...
[      COMPLETE      ]|##################################################| 100%
Linking packages ...
[      COMPLETE      ]|##################################################| 100%
#
# To activate this environment, use:
# > activate myPython
#
# To deactivate this environment, use:
# > deactivate myPython
#
# * for power-users using bash, you must source
#
```

#### Instalacja podstawowych pakietów
**Pakiety chcemy zainstalować we wczesniej utworzonym środowisku. W tym celu musimy je aktywować":**

```
activate myPython   (W systemie OS X: source activate myPython )
```
**Nastepnie przystepujemy do instalacji":**
```
conda install pandas numpy jupyter cython bottleneck numexpr openpyxl lxml xlrd xlwt pytables nose

[Część wierszy została usunięta dla zwiększonej czytelności]

(myPython) C:\WINDOWS\system32>conda install pandas numpy jupyter cython bottleneck numexpr openpyxl lxml xlrd xlwt pytables nose
Fetching package metadata .........
Solving package specifications: ..........

Package plan for installation in environment C:\Program Files\Miniconda3\envs\myPython:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    mkl-11.3.3                 |                1       110.0 MB
    icu-57.1                   |           vc14_0        34.2 MB
...
...
...


The following NEW packages will be INSTALLED:

    _nb_ext_conf:        0.3.0-py35_0
    anaconda-client:     1.6.0-py35_0
    clyent:              1.2.2-py35_0
...
...
...

Proceed ([y]/n)?

Fetching packages ...
mkl-11.3.3-1.t 100% |###############################| Time: 0:00:09  11.72 MB/s
icu-57.1-vc14_ 100% |###############################| Time: 0:00:03  11.43 MB/s
jpeg-8d-vc14_2 100% |###############################| Time: 0:00:00   3.87 MB/s
...
...
...
Extracting packages ...
[      COMPLETE      ]|##################################################| 100%
Linking packages ...
        1 file(s) copied.###########################                     |  58%
[      COMPLETE      ]|##################################################| 100%

```
