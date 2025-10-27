# Remplace Buster par Bullseye (version encore maintenue)
FROM python:3.8-bullseye

LABEL maintainer="seb"

# Copie des fichiers nécessaires
COPY requirements.txt student_age.py /

# Mise à jour et installation des dépendances
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
        python3-dev libsasl2-dev libldap2-dev libssl-dev && \
    rm -rf /var/lib/apt/lists/*

# Installation des dépendances Python
RUN pip3 install --no-cache-dir -r /requirements.txt

# Volume et port
VOLUME ["/data"]
EXPOSE 5000

# Lancement de ton script
CMD ["python3", "./student_age.py"]