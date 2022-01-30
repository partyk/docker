# Docker

```https://www.learn2code.sk/aplikacia/skupiny#/docker-pre-zaciatocnikov/chapters/08-hello-world-appka```

- ```docker build -t hello-world-app .``` build image
- ```docker run -d -p 8080:80 --name hello-world-app-c hello-world-app``` spustebi kontejneru *hello-world-app-c* z iamge *hello-world-app*
- ```docker stop hello-world-app-c``` zastaveni kontejneru
