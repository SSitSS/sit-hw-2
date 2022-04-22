FROM gcc:latest as build

RUN apt-get update && \
    apt-get install -y \
	 cmake \
	 python3-pip \ 
	&& python3 -m pip install Flask

RUN useradd -ms /bin/bash techproguser 
USER techproguser 
WORKDIR /home/techproguser

COPY . /home/techproguser

RUN mkdir build && \ 
	cd build && cmake .. && make && cd ..

CMD ["python3", "app.py"] 
