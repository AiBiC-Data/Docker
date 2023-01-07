FROM python

WORKDIR /app

COPY . /app

CMD ["python", "rng.py"]

#docker run으로 실행시 오류 -> 컨테이너에서 입력을 할수 없음
#docker run -it로 실행
#docker start는 detach모드이므로 -a로 attach모드로 실행한다고 생각할수 있으나 입력이 하나만 됨 따라서 이 방법이 아님
#docker start -a -i 로 실행