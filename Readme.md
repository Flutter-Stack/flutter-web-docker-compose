$ docker-compose up -d


One time activity


https://github.com/lgvalle/firebase-tools-docker

<!-- > docker run -p 9005:9005 -u node -it lgvalle/firebase-tools-docker sh -->

Run flutter-web-docker-compose_firebase-tools image and configure firebase login
----------------------------------------------------------------------------
$ docker run -u node -p 9005:9005  -it flutter-web-docker-compose_firebase-tools  /bin/sh  

/ $ firebase login
? Allow Firebase to collect anonymous CLI usage and error reporting information? Yes

Visit this URL on any device to log in:
https://accounts.google.com/o/oauth2/auth?client_id=xxxxxo849e6.apps.googleusercontent.com&scope=email%20openid%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fcloudplatformprojects.readonly%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Ffirebase%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fcloud-platform&response_type=code&state=176507547&redirect_uri=http%3A%2F%2Flocalhost%3A9005

Waiting for authentication...


commit changes to the container
--------------------------------------------
$ docker commit --message "Add firebase login" kind_mclean


Login and verfiy
--------------------------------------
luis@mbp > docker run -u node -p 9005:9005  -it flutter-web-docker-compose_firebase-tools  /bin/sh  

/ $ firebase list

/usr/app $ firebase list



Add alias in your bashrc file
------------------------------------------------------------------------------------------------------------------
alias fire='docker run -v $PWD:/usr/app -w /usr/app -p 9005:9005 -u node -it flutter-web-docker-compose_firebase-tools sh --name=flutter-web-docker-compose_firebase-tools'
