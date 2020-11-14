FROM google/dart
ADD ./dart-sass-1.29.0-linux-x64.tar.gz /opt/
WORKDIR /opt/dart-sass
ENTRYPOINT ["/opt/dart-sass/sass", "--watch", "/css"]
