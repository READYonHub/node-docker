# node-docker

## 🚀 Docker Parancsok – Használati útmutató

Ebben a szekcióban megtalálod az összes parancsot, amelyet a projekted Dockerrel való futtatásához használhatsz – magyarázatokkal, fogalmakkal kiegészítve.

---

### 🔧 1. Image építés és újrafelhasználás

| Parancs | Magyarázat |
|--------|-------------|
| `docker build .` | Image építése a jelenlegi mappában található Dockerfile alapján. |
| `docker build -t node-docker .` | Ugyanez, de nevet is adunk az image-nek: `node-docker`. |
| `docker image ls` | Az elérhető lokális image-ek listázása. |
| `docker image rm <id>` | Image törlése azonosító (hash) alapján. |
| `docker image rm <id> --force` | Kényszerített image törlés – még akkor is, ha használatban van. |

> 💡 **Tipp:** Használj verziózott tag-et is az image nevéhez: pl. `node-docker:v1` a könnyebb visszakereshetőség miatt.

---

### 📦 2. Konténer indítása, törlése és ellenőrzése

| Parancs | Magyarázat |
|--------|-------------|
| `docker run -d --name node-docker-app node-docker` | Konténer indítása háttérben (`-d`), megadott névvel. |
| `docker run -p 3000:3000 -d --name node-docker-app node-docker` | Port forwardolással (3000 kívül = 3000 belül). |
| `docker ps` | Jelenleg futó konténerek listája. |
| `docker ps -a` | Minden konténer listázása (futók és leállítottak is). |
| `docker logs node-docker-app` | A konténer naplóinak megtekintése. |
| `docker rm -f node-docker-app` | Konténer törlése erővel (`-f`), ha már nem kell. |

---

### 🧠 Fogalmak röviden

- **Image:** Statikus, futásra kész sablon, amiből konténert csinálsz.
- **Konténer:** Az image futó példánya – él, dolgozik, leállítható, törölhető.
- **Port binding:** A `-p` kapcsolóval összekötöd a géped és a konténer portját.
- **`--name`:** Nevet ad a konténernek – így könnyen 

# 1. Start

## 🐳 Node.js Express App Dockerizálva

Ez a projekt egy egyszerű Node.js + Express alkalmazást tartalmaz, amely Docker segítségével futtatható. A cél az, hogy konténeres környezetben is könnyedén elindítható legyen a szerver.

---

## 🚀 Futtatás Dockerből

1. Image építése

```sh
    docker build -t node-docker .
```

2. Konténer futtatása

```sh
    docker run -p 3000:3000 -d --name node-docker-app node-docker
```

## commands

```sh
    2 npm init
    3 npm init
    4 npm i express
    5 node .\index.js
```

