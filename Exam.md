# 1. Что такое Service и Ingress? - основные понятия, виды ресурсов + манифесты для каждого типа ресурсов
Service - It is the interface of communicating with pods. 
  We need to communicate with pods. Ip pod is a temporary because pod may down or refresh. You need to communicate with pods with static API. Here is it, we introduce 
  Service as a layer that helps to communicate to pods. The service tracks pods and can redirect requests to them.
  Service types:
   * ClusterIp - This is the type of connection with group of Nodes or Pods. It is simmiliar type if u want connect to group of pods
   * NodePort - This is the type of connection to Node directly. Use this type of service we can directly connect to Node and then connect to pods.
   * Inside) - This is the type of connection between Pods inside k8s. 

Ingress - It is a http request controller which is the enter to k8s. Ingress can redirect requests, between Services, and load balancing.
  Ingress has main part which is called Ingress Controller. Ingress Controller has a lot of implementations. They have own prof and cons. 
  
  
Manifests:
 1. Service
  api: /app/Serivce
  name:
  label:
  metadata:
  template:
    http:
      backend:
        some-server-name:
          kind:
          port:
          targetPort:
          ? NodePort:
          ? ClusterIp:
 2. Ingress
  api: /?/Ingress
  name:
  label:
  metadata:
    type:
    ingress-controller:
  template:
    rules:
    
# 2. Проблема двойной траты, параметры транзакции, пропускная способность сети.

  In centrialized finance system we have troubleshooting with the Double fees. Howeover, Centrializer finance system can manage this fees and deny it.
  In decentrialized finance system, like a blockchain, we have blocks which cannot have the Double fees. Block in blockchain is a Notes with transactions, 
  hash of previous block and metadata (mining time, miner name). That block validates by Nodes in blockchain and they are giving approf to it. If block has 
  the Double fees, it will be a wrong block and will be rejected by Nodes.
  
  Transaction parameters:
    * Transfer from (Address)
    * Transfer to (Address)
    * Amount
    * Data (message)
    * Sign?
    
  Network capacity (NC)
    Some blockchains have very low NC (Ethereum) or very high NC (Solana). It depends on the consensus mechanism and state of blockchain Network. 
    In the POW we can`t maximize NC because our miners dont have the computing power. In the POS we dont need the computing power and mining new block make faster (High Nc).
    Add to problem the POW with the computing power, miners need extra fees which got for work. ...

  
  
  
