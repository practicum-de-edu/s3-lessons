# Спринт 3

* Скопируйте проект в директорию:
```shell script
git clone ...
```
* Перейдите в директорию c проектом:
```shell script
cd s3-lessons
```
* Создайте [виртуальное окружение](https://docs.python.org/3/library/venv.html) и активируйте его:
```shell script
python3 -m venv venv
```
или для Windows
```shell script
python -m venv venv
```
Проверить, что виртуальное окружение создано можно командой ls - в списке с файлов и директорий вы увидите директорию venv

* Активируйте его:
```shell script
source venv/bin/activate
```
или в Windows
```shell script
source venv/Scripts/activate
```
или альтернативный способ для Windows
```shell script
.\venv\Scripts\activate.bat
```

* Обновите pip до последней версии:
```shell script
pip install --upgrade pip
```
* Установите зависимости:
```shell script
pip install -r requirements.txt
```

Для настройки airflow выполните команду:

`docker compose up airflow-init`


Для запуска Airflow и выполнения заданий выполните:

`docker compose up -d`

Перед запуском тестов убедитесь что запущен контейнер.

Для остановки:
`docker compose down`

Если у Вас не установлен python 3.8 то самое время сделать это. 

Поключние к БД:
При выполнении первого задания вы получите параметры подключения. Используйте их на протяжении всего спринта.

Airflow доступен по адресу http://localhost:8080
```
login: airflow
password: airflow
```

## Примечание

Даги импортируются из папки `dags` каждые 5 секунд.
Если даг не импортировался проверьте ошибки в  
Если ошибок нет и даг не появился в списке дагов то перезапустите контейнеры `docker compose restart`


По окончании спринта остановите контейнеры и удалите образы с системы:
`docker compose down --volumes --rmi all`
