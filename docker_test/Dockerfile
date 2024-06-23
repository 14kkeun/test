# 베이스 이미지 선택
FROM python:3.12.4-slim

# 필요한 패키지 설치
RUN apt-get update && apt-get install -y \
    gcc \
    default-libmysqlclient-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# 작업 디렉터리 설정
WORKDIR /app

# 종속성 파일 복사
COPY requirements.txt /app/

# 종속성 설치
RUN pip install --no-cache-dir -r requirements.txt

# 소스 코드 복사
COPY . /app/

# 포트 설정
EXPOSE 8000

# 명령어 설정
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
