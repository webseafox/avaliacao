# Passo a Passo para subir aplicação 

## 1 – Instalar o minkube 

Linux 

\# curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

\# sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64

--------------------------------------------------------------------------------------------

## 2 – Instalar kubectl 

Linux

\# curl -LO "https://dl.k8s.io/release/**$(**curl -L -s https://dl.k8s.io/release/stable.txt**)**/bin/linux/amd64/kubectl"

\# chmod +x kubectl

\# cp kubectl /usr/local/bin

--------------------------------------------------------------------------------------------

## 3 – Os arquivos necessario estão no repositorio, favor realizar um clone desse repositorio.

\# git clone https://github.com/webseafox/avaliacao.git

--------------------------------------------------------------------------------------------

## 4 – Gerar imagem docker 

\# eval $(minikube docker-env)

\# docker build -t hello-world-app .

Para validar rode 

docker run -p 3000:3000 hello-world-app

--------------------------------------------------------------------------------------------

## 5 – Iniciar o minikube

\# Minikube start 

--------------------------------------------------------------------------------------------

## 6 – Deploy da aplicação.

Kubectl apply –f k8s\*.yaml

Onde deployment realiza a construção do pod 

O services, libera acesso no pod na porta especificada 

E o ingress, libera a entrada das solicitadas

--------------------------------------------------------------------------------------------

## 7 – Habilitar o ingress no minikube

\# minikube addons enable ingress

--------------------------------------------------------------------------------------------

## 8 – Para acessar o minikube, é necessario resolver nome no /etc/hosts

\# echo "$(minikube ip) hello-world.local" | sudo tee -a /etc/hosts

Pode chamar a url (http://hello-world.local)


