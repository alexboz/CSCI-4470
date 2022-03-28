# Lab 08 Report - Virtualization and Docker

## Example 00
```
> docker run docker/whalesay cowsay boo
Unable to find image 'docker/whalesay:latest' locally
latest: Pulling from docker/whalesay
Image docker.io/docker/whalesay:latest uses outdated schema1 manifest format. Please upgrade to a schema2 image for better future compatibility. More information at https://docs.docker.com/registry/spec/deprecated-schema-v1/
e190868d63f8: Pull complete
909cd34c6fd7: Pull complete
0b9bfabab7c1: Pull complete
a3ed95caeb02: Pull complete
00bf65475aba: Pull complete
c57b6bcc83e3: Pull complete
8978f6879e2f: Pull complete
8eed3712d2cf: Pull complete
Digest: sha256:178598e51a26abbc958b8a2e48825c90bc22e641de3d31e18aaf55f3258ba93b
Status: Downloaded newer image for docker/whalesay:latest
 _____
< boo >
 -----
    \
     \
      \
                    ##        .
              ## ## ##       ==
           ## ## ## ##      ===
       /""""""""""""""""___/ ===
  ~~~ {~~ ~~~~ ~~~ ~~~~ ~~ ~ /  ===- ~~~
       \______ o          __/
        \    \        __/
          \____\______/
```

## Example 01
```
> docker run -it ubuntu bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
4d32b49e2995: Pull complete
Digest: sha256:bea6d19168bbfd6af8d77c2cc3c572114eb5d113e6f422573c93cb605a0e2ffb
Status: Downloaded newer image for ubuntu:latest
root@77ec261811b7:/# apt update
Get:1 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal InRelease [265 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Get:5 http://security.ubuntu.com/ubuntu focal-security/universe amd64 Packages [863 kB]
Get:6 http://archive.ubuntu.com/ubuntu focal/restricted amd64 Packages [33.4 kB]
Get:7 http://archive.ubuntu.com/ubuntu focal/multiverse amd64 Packages [177 kB]
Get:8 http://archive.ubuntu.com/ubuntu focal/main amd64 Packages [1275 kB]
Get:9 http://security.ubuntu.com/ubuntu focal-security/restricted amd64 Packages [1069 kB]
Get:10 http://archive.ubuntu.com/ubuntu focal/universe amd64 Packages [11.3 MB]
Get:11 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 Packages [25.8 kB]
Get:12 http://security.ubuntu.com/ubuntu focal-security/main amd64 Packages [1686 kB]
Get:13 http://archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 Packages [30.3 kB]
Get:14 http://archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [1146 kB]
Get:15 http://archive.ubuntu.com/ubuntu focal-updates/restricted amd64 Packages [1140 kB]
Get:16 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [2101 kB]
Get:17 http://archive.ubuntu.com/ubuntu focal-backports/universe amd64 Packages [26.0 kB]
Get:18 http://archive.ubuntu.com/ubuntu focal-backports/main amd64 Packages [51.2 kB]
Fetched 21.6 MB in 26s (838 kB/s)
Reading package lists... Done
Building dependency tree
Reading state information... Done
All packages are up to date.
root@77ec261811b7:/# apt install vim
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following additional packages will be installed:
  alsa-topology-conf alsa-ucm-conf file libasound2 libasound2-data libcanberra0 libexpat1 libgpm2 libltdl7
  libmagic-mgc libmagic1 libmpdec2 libogg0 libpython3.8 libpython3.8-minimal libpython3.8-stdlib libreadline8
  libsqlite3-0 libssl1.1 libtdb1 libvorbis0a libvorbisfile3 mime-support readline-common sound-theme-freedesktop
  vim-common vim-runtime xxd xz-utils
Suggested packages:
  libasound2-plugins alsa-utils libcanberra-gtk0 libcanberra-pulse gpm readline-doc ctags vim-doc vim-scripts
The following NEW packages will be installed:
  alsa-topology-conf alsa-ucm-conf file libasound2 libasound2-data libcanberra0 libexpat1 libgpm2 libltdl7
  libmagic-mgc libmagic1 libmpdec2 libogg0 libpython3.8 libpython3.8-minimal libpython3.8-stdlib libreadline8
  libsqlite3-0 libssl1.1 libtdb1 libvorbis0a libvorbisfile3 mime-support readline-common sound-theme-freedesktop vim
  vim-common vim-runtime xxd xz-utils
0 upgraded, 30 newly installed, 0 to remove and 0 not upgraded.
Need to get 14.9 MB of archives.
After this operation, 70.6 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu focal/main amd64 libmagic-mgc amd64 1:5.38-4 [218 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal/main amd64 libmagic1 amd64 1:5.38-4 [75.9 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal/main amd64 file amd64 1:5.38-4 [23.3 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 libexpat1 amd64 2.2.9-1ubuntu0.4 [74.4 kB]
Get:5 http://archive.ubuntu.com/ubuntu focal/main amd64 libmpdec2 amd64 2.4.2-3 [81.1 kB]
Get:6 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 libssl1.1 amd64 1.1.1f-1ubuntu2.12 [1322 kB]

Hello
man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/ex.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/ex.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/ex.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/ex.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/editor (editor) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/editor.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/editor.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/editor.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/editor.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/editor.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/editor.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/editor.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/editor.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group editor) doesn't exist
Processing triggers for libc-bin (2.31-0ubuntu9.7) ...
Selecting previously unselected package libgdbm-compat4:amd64.
Preparing to unpack .../2-libgdbm-compat4_1.18.1-5_amd64.deb ...
Unpacking libgdbm-compat4:amd64 (1.18.1-5) ...
Selecting previously unselected package libperl5.30:amd64.
Preparing to unpack .../3-libperl5.30_5.30.0-9ubuntu0.2_amd64.deb ...
Unpacking libperl5.30:amd64 (5.30.0-9ubuntu0.2) ...
Selecting previously unselected package perl.
Preparing to unpack .../4-perl_5.30.0-9ubuntu0.2_amd64.deb ...
Unpacking perl (5.30.0-9ubuntu0.2) ...
Selecting previously unselected package libtext-charwidth-perl.
Preparing to unpack .../5-libtext-charwidth-perl_0.04-10_amd64.deb ...
Unpacking libtext-charwidth-perl (0.04-10) ...
Selecting previously unselected package netbase.
Preparing to unpack .../6-netbase_6.1_all.deb ...
Unpacking netbase (6.1) ...
Selecting previously unselected package cowsay.
Preparing to unpack .../7-cowsay_3.03+dfsg2-7_all.deb ...
Unpacking cowsay (3.03+dfsg2-7) ...
Setting up libtext-charwidth-perl (0.04-10) ...
Setting up perl-modules-5.30 (5.30.0-9ubuntu0.2) ...
Setting up netbase (6.1) ...
Setting up libgdbm6:amd64 (1.18.1-5) ...
Setting up libgdbm-compat4:amd64 (1.18.1-5) ...
Setting up libperl5.30:amd64 (5.30.0-9ubuntu0.2) ...
Setting up perl (5.30.0-9ubuntu0.2) ...
Setting up cowsay (3.03+dfsg2-7) ...
Processing triggers for libc-bin (2.31-0ubuntu9.7) ...
root@77ec261811b7:/# cowsay
bash: cowsay: command not found
root@77ec261811b7:/# su
root@77ec261811b7:/# cowsay "moo!"
 ______
< moo! >
 ------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

## Example 02
```
> docker run --name db -d mongo:3.2 mongod --smallfiles
Unable to find image 'mongo:3.2' locally
3.2: Pulling from library/mongo
a92a4af0fb9c: Pull complete
74a2c7f3849e: Pull complete
927b52ab29bb: Pull complete
e941def14025: Pull complete
be6fce289e32: Pull complete
f6d82baac946: Pull complete
7c1a640b9ded: Pull complete
e8b2fc34c941: Pull complete
1fd822faa46a: Pull complete
61ba5f01559c: Pull complete
db344da27f9a: Pull complete
Digest: sha256:0463a91d8eff189747348c154507afc7aba045baa40e8d58d8a4c798e71001f3
Status: Downloaded newer image for mongo:3.2
1c37c69af29d3f1ab389701c8a40ff2ea7f91ef902c9e9235c10e4b47a0f674c
> docker run --name rocketchat -p 3000:3000 --env ROOT_URL=http://localhost --link db:db -d rocket.chat:0.62
Unable to find image 'rocket.chat:0.62' locally
0.62: Pulling from library/rocket.chat
4176fe04cefe: Pull complete
851356ecf618: Pull complete
fb492416b9f4: Pull complete
93078d113a16: Pull complete
1e735139451d: Pull complete
4b55f7e35a3a: Pull complete
4cc60d118ddf: Pull complete
5b791ce1d721: Pull complete
a44f3e97b664: Pull complete
Digest: sha256:c818411984172f5e313684c60fe30f959e26eedf494bf5aa4344ebae7e453d0f
Status: Downloaded newer image for rocket.chat:0.62
baa76952456d3c17f96731c954ffe192903226d30a8e1ce9498bd1ae5a1bbde4
> docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED              STATUS              PORTS                    NAMES
baa76952456d   rocket.chat:0.62   "node main.js"           12 seconds ago       Up 7 seconds        0.0.0.0:3000->3000/tcp   rocketchat
1c37c69af29d   mongo:3.2          "docker-entrypoint.s…"   About a minute ago   Up About a minute   27017/tcp                db         "docker-entrypoint.s…"   2 minutes ago    Up About a minute   27017/tcp                db
> docker stop rocketchat
rocketchat
> docker stop db
db
```

![](../../images/lab8-example2.png)

## Example 03
- Dockerfile
    ```
    # Comments in Dockerfiles
    FROM python:3.5
    
    # Update and install dependencies
    RUN apt-get update
    RUN pip install Flask
    
    # Add code
    ADD . /opt/webapp/
    
    # Set the working directory
    WORKDIR /opt/webapp
    
    # Set environment variables
    ENV FLASK_APP=hello.py
    
    # Expose the application's port
    EXPOSE 5000
    
    # Run the application
    CMD ["flask", "run", "--host=0.0.0.0"]
    ```
- Build and Run
    ```
    > docker build -t python-hello .
    [+] Building 80.0s (10/10) FINISHED
     => [internal] load build definition from Dockerfile                                              0.1s
     => => transferring dockerfile: 417B                                                              0.0s
     => [internal] load .dockerignore                                                                 0.1s
     => => transferring context: 2B                                                                   0.0s
     => [internal] load metadata for docker.io/library/python:3.5                                     5.9s
     => [1/5] FROM docker.io/library/python:3.5@sha256:42a37d6b8c00b186bdfb2b620fa8023eb775b3eb3a76  58.5s
     => => resolve docker.io/library/python:3.5@sha256:42a37d6b8c00b186bdfb2b620fa8023eb775b3eb3a768  0.0s
     => => sha256:42a37d6b8c00b186bdfb2b620fa8023eb775b3eb3a768fd3c2e421964eee9665 1.86kB / 1.86kB    0.0s
     => => sha256:24d62b9e24e5b601b524f33a1d477a66fce675efe11c96dd163c0f0ce5cc9810 2.22kB / 2.22kB    0.0s
     => => sha256:3687eb5ea744671d2ed755e4768e000289d1c9afd3da06a9b6c35fc51bc04a09 9.05kB / 9.05kB    0.0s
     => => sha256:57df1a1f1ad841deaf50c8f662d77e93b4b17af776ed66148116607f9aceffa 50.40MB / 50.40MB  14.4s
     => => sha256:71e126169501d71bbbd0d3c8d9f35836c41660869fe8432ac606341ed21f7adb 7.81MB / 7.81MB    2.6s
     => => sha256:1af28a55c3f320826db8df3146a2c198f9042877ef679f9e32210aa9a7fac9ef 10.00MB / 10.00MB  3.2s
     => => sha256:03f1c9932170e54fface2382b2550b8052ae3d41f27e66ea1294e2055dd2b2e 51.83MB / 51.83MB  17.0s
     => => sha256:65b3db15f518f11e53c95664d0675a5d78a5329d18d5316a406c2a45907a0 192.25MB / 192.25MB  30.2s
     => => sha256:850581be87f324c7b6f7d1c27b379793434517f3d4a5df97a9b859accbbaa7d0 6.15MB / 6.15MB   16.3s
     => => extracting sha256:57df1a1f1ad841deaf50c8f662d77e93b4b17af776ed66148116607f9aceffa8         6.0s
     => => sha256:1e37775630ae1e9c27b0bed43eba813e8d5fd21ec35cb3053f7fa264b548f3b 14.53MB / 14.53MB  19.2s
     => => sha256:7e054ca5fcba1e88f73ee14aa3e058ffe33decfa2b1be6698407265ed1930dd1 233B / 233B       17.1s
     => => sha256:92a0fe22689619ea67f6cf45df3fbd338ba24a76dddbb0fb6410be6a7270941c 2.12MB / 2.12MB   17.7s
     => => extracting sha256:71e126169501d71bbbd0d3c8d9f35836c41660869fe8432ac606341ed21f7adb         0.8s
     => => extracting sha256:1af28a55c3f320826db8df3146a2c198f9042877ef679f9e32210aa9a7fac9ef         0.7s
     => => extracting sha256:03f1c9932170e54fface2382b2550b8052ae3d41f27e66ea1294e2055dd2b2e7         7.3s
     => => extracting sha256:65b3db15f518f11e53c95664d0675a5d78a5329d18d5316a406c2a45907a0723        21.2s
     => => extracting sha256:850581be87f324c7b6f7d1c27b379793434517f3d4a5df97a9b859accbbaa7d0         1.1s
     => => extracting sha256:1e37775630ae1e9c27b0bed43eba813e8d5fd21ec35cb3053f7fa264b548f3be         3.3s
     => => extracting sha256:7e054ca5fcba1e88f73ee14aa3e058ffe33decfa2b1be6698407265ed1930dd1         0.0s
     => => extracting sha256:92a0fe22689619ea67f6cf45df3fbd338ba24a76dddbb0fb6410be6a7270941c         0.4s
     => [internal] load build context                                                                 0.1s
     => => transferring context: 4.84kB                                                               0.0s
     => [2/5] RUN apt-get update                                                                      6.4s
     => [3/5] RUN pip install Flask                                                                   8.1s
     => [4/5] ADD . /opt/webapp/                                                                      0.1s
     => [5/5] WORKDIR /opt/webapp                                                                     0.1s
     => exporting to image                                                                            0.4s
     => => exporting layers                                                                           0.4s
     => => writing image sha256:2042d561543d6bca6997535daf59fbafd50dc76a409d7699be6fce8197c4a38d      0.0s
     => => naming to docker.io/library/python-hello                                                   0.0s
    
    Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
    > docker run -p 5000:5000 python-hello
     * Serving Flask app "hello.py"
     * Environment: production
       WARNING: This is a development server. Do not use it in a production deployment.
       Use a production WSGI server instead.
     * Debug mode: off
     * Running on http://0.0.0.0:5000/ (Press CTRL+C to quit)
    172.17.0.1 - - [28/Mar/2022 21:48:14] "GET / HTTP/1.1" 200 -
    172.17.0.1 - - [28/Mar/2022 21:48:14] "GET /favicon.ico HTTP/1.1" 404 -
    ```

![](../../images/lab8-example3.png)

## Example 04
- Dockerfile
    ```
    # Use node 10.15.3 LTS
    FROM node:10.15.3
    ENV LAST_UPDATED 20190325T175400
    
    # Copy source code
    COPY . /app
    
    # Change working directory
    WORKDIR /app
    
    # Install dependencies
    RUN npm install
    
    # Fix up some of the issues
    #RUN npm audit fix
    
    # Expose API port to the outside
    EXPOSE 1337
    
    # Launch application
    CMD ["node","app.js"]
    ```
- Build Container
    ```
    > docker build -t message-app .
    [+] Building 66.0s (9/9) FINISHED
     => [internal] load build definition from Dockerfile                                                                                                                                                        0.1s
     => => transferring dockerfile: 364B                                                                                                                                                                        0.0s
     => [internal] load .dockerignore                                                                                                                                                                           0.1s
     => => transferring context: 2B                                                                                                                                                                             0.0s
     => [internal] load metadata for docker.io/library/node:10.15.3                                                                                                                                             5.2s
     => [internal] load build context                                                                                                                                                                          10.7s
     => => transferring context: 2.99MB                                                                                                                                                                        10.6s
     => CACHED [1/4] FROM docker.io/library/node:10.15.3@sha256:c5e919a89352d3ce6a883dde54a5d51dde12229c2d11088593cd1f3efefcc16e                                                                                0.0s
     => [2/4] COPY . /app                                                                                                                                                                                      19.5s
     => [3/4] WORKDIR /app                                                                                                                                                                                      0.1s
     => [4/4] RUN npm install                                                                                                                                                                                  18.7s
     => exporting to image                                                                                                                                                                                     11.3s
     => => exporting layers                                                                                                                                                                                    11.2s
     => => writing image sha256:a44b3bff0f32f161e3074127a1d73e701260a0afea213318b133405570bdfd73                                                                                                                0.0s
     => => naming to docker.io/library/message-app                                                                                                                                                              0.0s
    
    Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
    ```
- Docker Images
    ```
    > docker images
    REPOSITORY         TAG       IMAGE ID       CREATED          SIZE
    message-app        latest    a44b3bff0f32   23 minutes ago   1.03GB
    ```
- docker-compose.yml
    ```
    version: '3'
    services:
      mongo:
        image: mongo:4.0.7
        volumes:
          - mongo-data:/data/db
        expose:
          - "27017"
      app:
        build: .
        ports:
                - "1337:1337"
        links:
          - mongo
        depends_on:
          - mongo
        environment:
          - MONGO_URL=mongodb://mongo/messageApp
    volumes:
      mongo-data:
    ```
- Docker Compose Build
    ```
    > docker-compose build
    mongo uses an image, skipping
    Building app
    [+] Building 126.4s (9/9) FINISHED
     => [internal] load build definition from Dockerfile                                                                                                                                                        0.1s
     => => transferring dockerfile: 364B                                                                                                                                                                        0.0s
     => [internal] load .dockerignore                                                                                                                                                                           0.1s
     => => transferring context: 2B                                                                                                                                                                             0.0s
     => [internal] load metadata for docker.io/library/node:10.15.3                                                                                                                                             2.0s
     => CACHED [1/4] FROM docker.io/library/node:10.15.3@sha256:c5e919a89352d3ce6a883dde54a5d51dde12229c2d11088593cd1f3efefcc16e                                                                                0.0s
     => [internal] load build context                                                                                                                                                                          79.5s
     => => transferring context: 133.01MB                                                                                                                                                                      79.4s
     => [2/4] COPY . /app                                                                                                                                                                                      15.4s
     => [3/4] WORKDIR /app                                                                                                                                                                                      0.1s
     => [4/4] RUN npm install                                                                                                                                                                                  22.4s
     => exporting to image                                                                                                                                                                                      6.3s
     => => exporting layers                                                                                                                                                                                     6.3s
     => => writing image sha256:5454339f3e7759879b2cfddac432376e043bacca447ec50f50debf5aaa192483                                                                                                                0.0s
     => => naming to docker.io/library/messageapp_app                                                                                                                                                           0.0s
    
    Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
    ```
- Docker Compose Up
    ```
    > docker-compose up
    Creating network "messageapp_default" with the default driver
    Creating volume "messageapp_mongo-data" with default driver
    Pulling mongo (mongo:4.0.7)...
    4.0.7: Pulling from library/mongo
    34667c7e4631: Pull complete
    d18d76a881a4: Pull complete
    119c7358fbfc: Pull complete
    2aaf13f3eff0: Pull complete
    f7833eaffdda: Pull complete
    8287cb5b9daf: Pull complete
    ea00040a145a: Pull complete
    eeb70119a2ba: Pull complete
    066b6bd644f8: Pull complete
    17862d4a3122: Pull complete
    1cdcc815e975: Pull complete
    73e0e2953af7: Pull complete
    f719605a4369: Pull complete
    Digest: sha256:07b8ccd32d40f47892ff5d074626cb9a866f49742658ce872dd1095cb51d9264
    Status: Downloaded newer image for mongo:4.0.7
    Creating messageapp_mongo_1 ... done
    Creating messageapp_app_1   ... done
    Attaching to messageapp_mongo_1, messageapp_app_1
    mongo_1  | 2022-03-28T22:16:06.260+0000 I CONTROL  [main] Automatically disabling TLS 1.0, to force-enable TLS 1.0 specify --sslDisabledProtocols 'none'
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] MongoDB starting : pid=1 port=27017 dbpath=/data/db 64-bit host=74fc264a8b0b
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] db version v4.0.7
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] git version: 1b82c812a9c0bbf6dc79d5400de9ea99e6ffa025
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] OpenSSL version: OpenSSL 1.0.2g  1 Mar 2016
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] allocator: tcmalloc
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] modules: none
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] build environment:
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten]     distmod: ubuntu1604
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten]     distarch: x86_64
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten]     target_arch: x86_64
    mongo_1  | 2022-03-28T22:16:06.265+0000 I CONTROL  [initandlisten] options: { net: { bindIpAll: true } }
    mongo_1  | 2022-03-28T22:16:06.266+0000 I STORAGE  [initandlisten]
    mongo_1  | 2022-03-28T22:16:06.266+0000 I STORAGE  [initandlisten] ** WARNING: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine
    mongo_1  | 2022-03-28T22:16:06.266+0000 I STORAGE  [initandlisten] **          See http://dochub.mongodb.org/core/prodnotes-filesystem
    mongo_1  | 2022-03-28T22:16:06.266+0000 I STORAGE  [initandlisten] wiredtiger_open config: create,cache_size=5822M,session_max=20000,eviction=(threads_min=4,threads_max=4),config_base=false,statistics=(fast),log=(enabled=true,archive=true,path=journal,compressor=snappy),file_manager=(close_idle_time=100000),statistics_log=(wait=0),verbose=(recovery_progress),
    mongo_1  | 2022-03-28T22:16:07.335+0000 I STORAGE  [initandlisten] WiredTiger message [1648505767:335182][1:0x7fac035b3a40], txn-recover: Set global recovery timestamp: 0
    mongo_1  | 2022-03-28T22:16:07.360+0000 I RECOVERY [initandlisten] WiredTiger recoveryTimestamp. Ts: Timestamp(0, 0)
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten]
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten] ** WARNING: Access control is not enabled for the database.
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten] **          Read and write access to data and configuration is unrestricted.
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten]
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten]
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten] ** WARNING: /sys/kernel/mm/transparent_hugepage/enabled is 'always'.
    mongo_1  | 2022-03-28T22:16:07.399+0000 I CONTROL  [initandlisten] **        We suggest setting it to 'never'
    mongo_1  | 2022-03-28T22:16:07.400+0000 I CONTROL  [initandlisten]
    mongo_1  | 2022-03-28T22:16:07.401+0000 I STORAGE  [initandlisten] createCollection: admin.system.version with provided UUID: aeb85402-31d7-47cf-996c-39b6a4f43bae
    mongo_1  | 2022-03-28T22:16:07.453+0000 I COMMAND  [initandlisten] setting featureCompatibilityVersion to 4.0
    mongo_1  | 2022-03-28T22:16:07.489+0000 I STORAGE  [initandlisten] createCollection: local.startup_log with generated UUID: 55dc4c5d-3d27-4d54-ad2c-34e1d6bad07f
    mongo_1  | 2022-03-28T22:16:07.550+0000 I FTDC     [initandlisten] Initializing full-time diagnostic data capture with directory '/data/db/diagnostic.data'
    mongo_1  | 2022-03-28T22:16:07.563+0000 I STORAGE  [LogicalSessionCacheRefresh] createCollection: config.system.sessions with generated UUID: 824d3dfe-572a-4e0a-9171-0b7ccb70ef5c
    mongo_1  | 2022-03-28T22:16:07.565+0000 I NETWORK  [initandlisten] waiting for connections on port 27017
    mongo_1  | 2022-03-28T22:16:07.656+0000 I INDEX    [LogicalSessionCacheRefresh] build index on: config.system.sessions properties: { v: 2, key: { lastUse: 1 }, name: "lsidTTLIndex", ns: "config.system.sessions", expireAfterSeconds: 1800 }
    mongo_1  | 2022-03-28T22:16:07.656+0000 I INDEX    [LogicalSessionCacheRefresh]          building index using bulk method; build may temporarily use up to 500 megabytes of RAM
    mongo_1  | 2022-03-28T22:16:07.664+0000 I INDEX    [LogicalSessionCacheRefresh] build index done.  scanned 0 total records. 0 secs
    mongo_1  | 2022-03-28T22:16:07.665+0000 I COMMAND  [LogicalSessionCacheRefresh] command config.$cmd command: createIndexes { createIndexes: "system.sessions", indexes: [ { key: { lastUse: 1 }, name: "lsidTTLIndex", expireAfterSeconds: 1800 } ], $db: "config" } numYields:0 reslen:114 locks:{ Global: { acquireCount: { r: 2, w: 2 } }, Database: { acquireCount: { w: 2, W: 1 } }, Collection: { acquireCount: { w: 2 } } } protocol:op_msg 102ms
    app_1    | debug: The `sails.config.models.connection` setting is deprecated.  Please use `sails.config.models.datastore` instead.
    app_1    | debug: For more info, see http://sailsjs.com/documentation/upgrading/to-v-1-0/#?changes-to-database-configuration
    app_1    |
    mongo_1  | 2022-03-28T22:16:12.613+0000 I NETWORK  [listener] connection accepted from 172.18.0.3:48522 #1 (1 connection now open)
    mongo_1  | 2022-03-28T22:16:12.638+0000 I NETWORK  [conn1] received client metadata from 172.18.0.3:48522 conn1: { driver: { name: "nodejs", version: "2.2.25" }, os: { type: "Linux", name: "linux", architecture: "x64", version: "4.19.128-microsoft-standard" }, platform: "Node.js v10.15.3, LE, mongodb-core: 2.1.9" }
    app_1    |  info:
    app_1    |  info:                .-..-.
    app_1    |  info:
    app_1    |  info:    Sails              <|    .-..-.
    app_1    |  info:    v1.1.0              |\
    app_1    |  info:                       /|.\
    app_1    |  info:                      / || \
    app_1    |  info:                    ,'  |'  \
    app_1    |  info:                 .-'.-==|/_--'
    app_1    |  info:                 `--'-------'
    app_1    |  info:    __---___--___---___--___---___--___
    app_1    |  info:  ____---___--___---___--___---___--___-__
    app_1    |  info:
    app_1    |  info: Server lifted in `/app`
    app_1    |  info: To shut down Sails, press <CTRL> + C at any time.
    app_1    |  info: Read more at https://sailsjs.com/support.
    app_1    |
    app_1    | debug: -------------------------------------------------------
    app_1    | debug: :: Mon Mar 28 2022 22:16:12 GMT+0000 (Coordinated Universal Time)
    app_1    | debug: Environment : development
    app_1    |
    app_1    | debug: Port        : 1337
    app_1    | debug: -------------------------------------------------------
    mongo_1  | 2022-03-28T22:16:44.706+0000 I STORAGE  [conn1] createCollection: messageApp.message with generated UUID: 308a1c07-e011-49cd-90bf-58c77ec4dd91
    app_1    | debug: Using `PUT` to update a record is deprecated in Sails 1.0.  Use `PATCH` instead!
    app_1    | debug: Using `PUT` to update a record is deprecated in Sails 1.0.  Use `PATCH` instead!
    Gracefully stopping... (press Ctrl+C again to force)
    Stopping messageapp_app_1   ... done
    Stopping messageapp_mongo_1 ... done
    ```
- Usage
    ```
    $ curl http://localhost:1337/message
    []
    $ curl -XPOST http://localhost:1337/message?text=hello
    {
      "text": "hello",
      "createdAt": 1648505804697,
      "updatedAt": 1648505804697,
      "id": "624233cc1f242b64841c3985"
    }
    $ curl -XPOST http://localhost:1337/message?text=hola
    {
      "text": "hola",
      "createdAt": 1648505810090,
      "updatedAt": 1648505810090,
      "id": "624233d21f242b4bc71c3986"
    }
    $ curl http://localhost:1337/message
    [
      {
        "text": "hello",
        "createdAt": 1648505804697,
        "updatedAt": 1648505804697,
        "id": "624233cc1f242b64841c3985"
      },
      {
        "text": "hola",
        "createdAt": 1648505810090,
        "updatedAt": 1648505810090,
        "id": "624233d21f242b4bc71c3986"
      }
    ]
    $ curl -XPUT http://localhost:1337/message/624233cc1f242b64841c3985?text=hey
    {
      "text": "hey",
      "createdAt": 1648505804697,
      "updatedAt": 1648505876094,
      "id": "624233cc1f242b64841c3985"
    }
    $ curl -XDELETE http://localhost:1337/message/624233d21f242b4bc71c3986
    {
      "text": "hola",
      "createdAt": 1648505810090,
      "updatedAt": 1648505810090,
      "id": "624233d21f242b4bc71c3986"
    }
    $ curl http://localhost:1337/message
    [
      {
        "text": "hey",
        "createdAt": 1648505804697,
        "updatedAt": 1648505876094,
        "id": "624233cc1f242b64841c3985"
      }
    ]
    ```
