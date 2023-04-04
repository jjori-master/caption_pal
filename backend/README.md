# Django 개발 환경 설정



## 0. 로컬 개발 환경

1. OS : Windows 10
2. 터미널 : Powershell
3. IDE: Pycharm 2022.1.4
4. Python version : 3.10.10
5. Django version : 4.1.7



## 1. Pycham Interpreter 설정

1. file > settings > Project: backend > Python Interpreter 
2. Interpreter 종류로 Docker docker 선택
3. docker-compose.yml 파일 선택
4. Service : web 선택



## 2. Django 프로젝트 생성

> 해당 작업은 프로젝트 극 초기에 실행하여 더 이상 실행할 필요가 없습니다.

```bash
$> docker-compose run web django-admin startproject config /app
```



## 3. Django 지원 활성

1.  settings > Languages & Frameworks > Django
2. Enable Django Support 체크
3. Django project root 설정
4. Settings 설정 : config\settings.py
5. Manage script 설정 : mange.py



## 4. DB 설정

1. postgreSQL 15.2

2. config\settings.py  DATABASES에 아래와 같이 설정
   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.postgresql',
           'NAME': os.getenv('POSTGRES_DB'),
           'USER': os.getenv('POSTGRES_USER'),
           'PASSWORD': os.getenv('POSTGRES_PASSWORD'),
           'HOST': os.getenv('POSTGRES_HOST', 'localhost'),
           'PORT': os.getenv('POSTGRES_PORT', '5432'),
       }
   }
   ```

3. 해당 사항은 프로젝트 극 초기에만 적용



## 5. migration

1.  Tools > Run manage.py task 실행
2. console에 migrate 실행