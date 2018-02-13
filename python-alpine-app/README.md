# Docker file for building container with apache2 and python
I use it to run very simple python scripts  
Container weights only 78 MB.

## Usage

1. Put your python app into application/

2. Build containter, calling it for example alpine/python-myapp:latest
```
docker build -t alpine/python-myapp:latest .
```

3. Run it as daemon, exposing port 8080
```
docker run -p 8080:80 -d alpine/python-myapp

```

4. Test access by running

```
curl http://hostip:8080/cgi-bin/myapp.py
```
