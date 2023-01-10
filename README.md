## Description 

### **Requirements**:
* minikube or kubernetes installed
* kubectl installed
* helm installed

## A. Clone of the Repo
```
git clone https://github.com/waltersimo/helm-package-web-calculator.git
cd helm-package-web-calculator
```

## B. Installation and Deployment

1. Installation with Helm
Test
```
helm template calculator-web-app > all-in-one.yml
```
Installation
```
helm install calculator-web-app --generate-name
```

2. Packaging
```
helm package calculator-web-app
```

3. Port forward of the frontend service
```
kubectl port-forward -n calculator-web-app svc/service-frontend-calculator 8000:80
```

4. Port forward of the backend service
```
kubectl port-forward -n calculator-web-app svc/service-backend-calculator 8001:80
```

Remark: If you run the code on a virtual server with no graphical interface, you can create ssh tunner for forwded port as follows:
```
ssh -f username_Instance@IP_Instance -L 8000:localhost:8000 -N
ssh -f username_Instance@IP_Instance -L 8001:localhost:8001 -N
```

5. See the deployed web application with the url
```
http://localhost:8080
```
*Walter Simo*
