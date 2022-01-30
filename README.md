# Docker

## link
- ```https://hub.docker.com/``` oficialní image

## ```docker``` základní příkazy

- ```docker ps``` výpis běžících kontejnerů
- ```docker ps --all``` výpis všech kontejnerů
- ```docker run hello-world``` stažení a spuštění kontejneru
- ```docker run --name=moje-prvni-aplikace hello-world``` stažení a spuštění kontejneru + pojemnování kontejneru
- ```docker build -t {NAME} .``` vytvoření image
- ```docker images``` Zoznam kontajnerov (bez ďalších parametrov zobrazí len tie, ktoré sú spustené)

```https://www.learn2code.sk/aplikacia/skupiny#/docker-pre-zaciatocnikov/chapters/07-cli-zakladne-prikazy-video```

## ```docker``` vytvoření image

### Základné Dockerfile inštrukcie:

- FROM
  - inicializuje image, ktorý potrebuje vychádzať z nejakého základneho image-u
  - obvykle to býva z oficiálneho Docker Hubu
- LABEL
  - definovanie metadát pre image
  - služí pre lepšiu informovanosť a možnosti pokročilejšej filtrácie v zozname image-ov
- RUN
  - najčastejšie využívané pre inštaláciu knižníc a závislosti pre daný OS
- CMD
  - spúšťa nejaký program v podobe napríklad shell príkazu spolu s argumentami
- ENTRYPOINT
  - spúšťa nejaké príkazy po naštartovaní kontajnera (podobne ako CMD)
  - podporuje navyše dynamicky zadané argumenty pri štartovaní kontajnera
  cez CMD sa môžu definovať default argumenty - pokiaľ ich nezadal používateľ
- EXPOSE
  - definovanie portov, na ktorých môže počúvať bežiaci kontajner
  - samotné publikovanie portu sa robí až pri spúšťaní kontajnera
- ENV
  - premenné prostredia
  - môžu sa v nich uchovávať nejaké nemenné hodnoty, napr. verzie balíčkov
- ADD a COPY
  - oba fungujú podobne, kopírujú súbory z nejakého zdroja do image-u
  ADD môže kopírovať súbory aj zo vzdialenej URL adresy
- VOLUME
  - inštrukcia pre vytvorenie zväzku - virtuálne úložisko pre dáta
  - obvykle sa sem ukladajú dáta, ktoré chcete aby ostali perzistentné ja po tom, ako kontajner prestane bežať
- USER
  - definovanie používateľa, pod ktorým bude bežať kontajner po jeho naštartovaní
- WORKDIR
  - nastavenie sa do priečinka, v ktorom budú iné inštrukcie pracovať
  - ekvivalent príkazu "cd /path" - tento tvar sa ale v Dockerfile neod
