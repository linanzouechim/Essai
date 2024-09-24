# conteneurisation d'un site web statique
FROM python:3.8-buster
MAINTAINER linanzouechim (linanzouechim@gmail.com)
ADD student_age.py /
RUN apt update -y && apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
ADD requirements.txt /
RUN pip3 install -r /requirements.txt
VOLUME ["/data"]
EXPOSE 5000
CMD [ "python3", "./student_age.py" ]
# Attention, ne pas oublier de faire un bindmount du fichier
#student_age.json . Donc la commande du lancement du containeur sera:
#  docker run -d --name studentlistcon -v ${PWD}/student_age.json:/data/student_age.json -p 4000:5000 studentlistimg