sudo apt install python3-pip
pip install virtualenv
python3 --version
python3 -m venv env
source env/bin/activate
pip list
pip freeze > requirements.txt
pip install -r requirements.txt
deactivate
pip install Flask
python3 app/wsgi.py
docker-compose up -d

ocker-compose down
docker-compose build --no-cache
docker-compose up -d --build --scale app=3