# dcmake

Ubuntu base image with preinstall `cmake`, `clang`, `conan` and `poco`. Suitable for your `C++` project that uses Poco <https://pocoproject.org/>.

## Build
```shell
$ make build
```

## Create Dockerfile
```
FROM wuriyanto/dcmake

WORKDIR /app/cpoco/

ADD . /app/cpoco

RUN mkdir build \
    && cd build \
    && cmake .. \
    && make

EXPOSE 8000

ENTRYPOINT [ "./build/cpoco" ]
```