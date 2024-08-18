DEPLOYING A SOCK-SHOP MICROSERVICE ON KUBERNETES CLUSTER

PROJECT EXPECTATIONS:

-  Deploy Pipeline
-  Alertmanager
-  Monitoring (Grafana)
-  Logging (Prometheus)
-  Use Prometheus as a monitoring tool
-  Use Terraform or Ansible as the configuration management tool.
-  You can use any IaaS provider of your choice.
-  The application should run on Kubernetes
-  The application should run on HTTPS with a Let’s Encrypt!



PROJECT REQUIREMENT:

- Any IaaS active Service with subscription (AWS was the active service use in this project)
- Install vscode
- Install AWS cli, Kubernetes, helm and terraform


PROJECT STEPS:

1. CREATING VPC AND EKS NODES USING AWS PROVIDER

   ![VPC   EKS NODES](https://github.com/user-attachments/assets/b017339b-4c49-4124-90cf-bfadab612ff0)

   ![EKS MODULES](https://github.com/user-attachments/assets/04045875-71c3-4578-9555-a5eb179b8842)


2. NEXT IS TO INITIALIZE OUR EKS MODULE IN OUR WORKING DIRECTORY USING THE COMMAND (TERRAFORM INIT)

   ![INITIALIZING EKS MODULES](https://github.com/user-attachments/assets/dc79df99-eaba-49a9-b123-4d37f5a11e84)
   


4. NEXT IS TO PROVISION OUR CLUSTER USING THE FOLLOWING COMMAND (TERRAFORM PLAN $ TERRAFORM APPLY-AUTO APPROVE)

   ![PROVISIONING CLUSTER ](https://github.com/user-attachments/assets/e37045ff-8764-491b-ae89-bca27af49d52)


5. NEXT IS TO CHECK THE EKS NODES RESOURCES WE PROVISION IF THEY ARE ALL RUNNING IN THE AWS CONSOLE (EC2, EKS CLUSTER, VPC, AUTO-SCALING GROUP, ETC)


   ![aws service 1](https://github.com/user-attachments/assets/6dc75390-3730-46f2-8129-9287e9ce607c)

   ![aws service 2](https://github.com/user-attachments/assets/1ed56445-a3c9-4540-87a5-e4fa1b99bbd9)

   ![aws service 3](https://github.com/user-attachments/assets/6b4ea6a5-cc01-4f64-bba2-30ddb28c6a5d)

   
6. NOW LET DEPLOY OUR APPLICATION USING THE DEPLOYMENT YAML-FILE THAT WAS SUPPLIED TO US FOR THIS PROJECT (BELOW IS THE YAML-FILE IMAGE)


   ![YAML-FILE ](https://github.com/user-attachments/assets/296ea0ea-2b2e-49b3-b0ac-db3a82a2812b)



7. NEXT IS TO RUN OUR APPLICATION AND CONFIRM IF IT IS RUNNING USING THE COMMAND (Kubectl get pods,svc -n sock-shop). THIS COMMAND WILL LIST ALL THE AVAILABLE PODS AND SERVICES IN THE SOCK-SHOP NAMESPACE.


  ![kubectl get pods](https://github.com/user-attachments/assets/3e8fcc1f-e321-4100-8868-8e60849c934a)


8. NEXT IS TO INSTALL 'INGRESS CONTROLLER'. THE INGRESS CONTROLLER HELP TO ROUTE TRAFFIC TO OUR POD SO THAT WE CAN ACCESS OUR APPPLICATION USING THE INGRESS EXTERNAL IP. TO DO THIS WILL WE NEED A PACKAGE NAME 'HELM'. (HELM IS USE TO ADD OUR INGRESS-NGINX REPO TO OUR LOCAL DEVELOPMENT AREA).


   
  ![ingress-controller](https://github.com/user-attachments/assets/ea484fff-61bc-457b-b194-f5ea75e32473)



9. NEXT IS TO GO TO OUR NAME CHEAP DASH-BAORD TO CREATE AN A-RECORD TO MAP OUR INGRESS EXTERNAL IP ADDRESS TO OUR DOMAIN NAME.  WE WILL ALSO CREATE A C-REORD THAT WILL SERVE & LINK OUR PODS SO WE CAN ACCESS IT USING WEB BROWSER.


    ![A-RECORD DNS](https://github.com/user-attachments/assets/0357ba2c-c994-4937-9e3c-e6982070e43c)




10. NEXT IS TO RUN THE COMMAND 'Kubectl apply -f ingress.yaml' TO APPLY OUR INGRESS RULE AND BE ABLE TO ACCESS OUR APPLICATION USING OUR DOMAIN NAME ON WEB BROWSER.


    ![kubectl -f](https://github.com/user-attachments/assets/241af136-f92a-4186-9227-3f850c822214)




11. NEXT IS TO ACCESS OUR APPLICATION ON OUR WEB BROWSER. (IMAGE BELOW SHOW THAT OUR APPLICATION IS RENDERING THE SOCK-SHOP APP IN OUR BROWSER).


    ![socks2](https://github.com/user-attachments/assets/5974c236-f48f-4c77-b552-9d843ed409e2)

    ![socks1](https://github.com/user-attachments/assets/68bdab22-e29d-4a99-a8c6-6ec41347e550)



12. NEXT IS TO DEPLOY OUR MONITORING AND LOGGING TOOL. TO DO THIS WE WILL USE TWO HELM COMMAND, THE FIRST ONE IS "helm repo add prometheus-community https://prometheus-community.github.io/helm-charts", THE SECOND HELM COMMAND IS "helm search repo prometheus", WHICH IS TO SEARCH FOR OUR PREFER PROMETHEUS FILE THAT WILL BE SUITABLE FOR MONITORING AND LOGGING. THEN WE INSTALL THE HELM FILE PROMETHEUS FILE USING "helm install prome prometheus-community/kube-prometheus-stack -n sock-shop", ONCE IT IS INSTALLED SUCCESFULLY YOU CAN THEN RUN THE COMAND "kubectl get pods,svc -n sock-shop".


    ![PROMETHEUS-INSTALL](https://github.com/user-attachments/assets/4b425e1c-2083-4af3-b7a5-702bb12a016e)



13. NEXT IS TO LOGIN TO OUR GRAFANA & PROMETHUES DASH BAORD AFTER SUCCESFULLY UPDATING OUR YAML-FILE AND COPYING OUR USERNAME AND PASSWORD.


    <img width="1434" alt="grafana image" src="https://github.com/user-attachments/assets/b682d025-c2bb-4121-9e58-f3ad42e219e9">


14. PROMETHEUS BROWSER PAGE. (FOR PROMETHEUS YOU DONT NEED ANY USERNAME LOGIN OR PASSWORD).


    <img width="1437" alt="Prometheus Page" src="https://github.com/user-attachments/assets/f42fec6b-ac72-44c9-b841-39aeddc50fd4">




P.S: FOR HEALTH REASON COULDNT COMPLETE THIS PROJECT - ALERT MANAGER AND CICD IS YET TO BE IMPLEMENTED IN THIS PROJECT. 

P.S.S. HOPEFULLY I WILL IMPLEMENT THE ALERT-MANGER AND CICD WHEN FULLY HEALTHY. 


    



    




   



   





