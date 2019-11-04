# vic_homelab 
#Date : November 2019 

SAMPLE EXCERCISES FOR BEGINEERS 

In this repository we are going to have working examples with different scenarios :

Our setup details : 

1. vCenter 6.7  
2. esxi hosts : 6.7 
3. Storage: vSAN 
4. Networks: NSX-V
  Bridge network PG - created
  Management network PG - Created 
  Container network PG - Created 
 5. VIC 1.5.4 ( latetst available) 
 6. Deploy VIC host using following command: 
      create 
        --target homelabvc01.vsphere.local/VIC_COMPUTE_CLUSTER 
        --user 'administrator@vsphere.local' 
        --password 'VMware@12345' 
        --no-tlsverify 
        --force 
        --bridge-network vxw-dvs-564-virtualwire-21-sid-2144-NSX-VIC-Bridge
        --bridge-network-range 192.168.125.0/12 
        --dns-server 10.126.193.47  
        --public-network vxw-dvs-564-virtualwire-21-sid-2144-NSX-public
        --container-network vxw-dvs-564-virtualwire-21-sid-2144-NSX-Container:public 
        --container-network-firewall vxw-dvs-564-virtualwire-21-sid-2144-NSX-Container:open 
        --compute-resource 'TEST_CLUSTER' 
        --image-store DATASTORE_VSAN 
        --timeout 20m 
        --endpoint-cpu 4  
        --memory 30000
        --endpoint-memory 8192 
        --volume-store DATASTORE_VSAN/volumes:default 
        --thumbprint 09:21:29:EF:0G:DE:78:9D:FG:89:DF:8F:89:3S:89:0A:FF:67:ZX 
        --name MyFirstVCH
        
    7. Once you run the above command you should get a message
    
          msg="Initialization of appliance successful"
          msg="VCH ID: vm-89467"
          msg="VCH Admin Portal:"
          msg="https://10.12.1.2:2378"
          msg="VCH Default Bridge Network Range: 192.168.125.0/12"
          msg="VCH Default Bridge Network Width: 16"
          msg="Published ports can be reached at:"
          msg=10.12.1.2
          msg="Management traffic will use:"
          msg=10.12.1.2
          msg="Docker environment variables:"
          msg="DOCKER_HOST=10.12.1.2:2376 COMPOSE_TLS_VERSION=TLSv1_2"
          msg="Environment saved in MyFirstVCH/MyFirstVCH.env"
          msg="Connect to docker:"
          msg="docker -H 10.12.1.2:2376 --tls info"
          msg="Installer completed successfully"

    8. Use any of the docker client to connect to the doker host ( DOCKER_HOST=10.12.1.2:2376) and follow the scripts in the repository 

Please leave a comment/feedback/suggestions 


