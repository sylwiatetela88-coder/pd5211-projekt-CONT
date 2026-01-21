# Projekt koncowy -Konteneryzacja (CONT)
**Autor:** Sylwia Tetela
**Numer sluchacza:** pd5211

##Opis Projektu
Projekt jest realizacja mikroserwisu bioinformatycznego, ktory ma mozliwosc analizy automatycznej jakosci sekwencji DNA (zawartego w plikach FASTQ) przy uzyciu narzdzia FastQC i umozliwia wyswietlanie wynikow przez serwe NGINX.

##Struktura plikow
- 'Dockerfile' buduje obraz przy pomocy narzedzia FastQC,
- 'docker-compose.yml' definiuje serwis FastQC i NGINX, wolumeny oraz siec,
- 'nginx.conf' umozliwia konfiguracje serwera WWW,
- 'input/' to katalog zawierajacy dane wyjsciowe,
- 'README.md' To wyjsciowa dokumentacja projektu.

##Technologie z ktorych korzysta projekt
* **FastQC**- narzedzie do kontroli jakosci sekwencji DNA
* **NGINX**- serwer WWW do prezentacji raportow HTML
* **Docker & Docker Compose** do orkiestracji kontenerow
#Etapy realizacji projektu
1. **Przygotowanie struktury**
Utworzenie katalogu projektu 'pd5211-projekt-CONT' oraz podkatalogu 'input'
2. **Dane wyjsciowe** 
Umieszczenie pliku  genomowego 'SRR8786200_1.fastq.gz' w folderze 'input'
3. **Dockerfile**
 Przygotowanie obrazu opartego na Ubuntu 22.04 z zainstalowanym srodowiskiem Java i narzedziem FastQC
4. **Konfiguracja NGINX** 
Stworzenie pliku 'nginx.conf' wskazujacego na wygenerowany raport FastQC
5. **Docker Compose**
Definicja dwoch uslug:
	*'nginx' odbiera wyniki i serwuje je na porcie 8080
	*'fastqc' przetwarza dane z wolumenu 'input' i zapisuje wyniki do wspoldzielonego wolumenu 'fastqc_results"
6. **Uruchomienie**
 Budowa i start serwisu komenda 'docker compose up --build'
7. **Weryfikacja dzialania**
 Sprawdzenie poprawnosci raportu pod adresem 'http://localhost:8080'
8. **Publikacja**
 Przeslanie kodu do repozytorium na koncie GitHub 

##Jak uruchomic?
1. Sklonowanie repozytorium lub przejscie do folderu projektu.
2. Nalezy umiescic plik genomowy w folderze 'input/' pod nazwa 'SRR8786200_1.fastq.gz'
3. Uruchomienie kontenerow: 
'''bash 
docker compose up --build 

##Dziekuje i pozdrawiam :)
