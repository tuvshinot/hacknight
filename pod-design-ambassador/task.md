**Task**

This setup will need to meet the following specifications:

 - The pod should have the name fruit-service.
 - The fruit-service pod should have a container that runs the legacy fruit service image: linuxacademycontent/legacy-fruit-service:1.
 - The fruit-service pod should have an ambassador container that runs the haproxy:1.7 image and proxies incoming traffic 
 on port 80 to the legacy service on port 8775 (the HAProxy configuration for this is provided below).
 - Port 80 should be exposed as a containerPort. Note that you do not need to expose port 8775.
 - The HAProxy configuration should be stored in a ConfigMap called fruit-service-ambassador-config.
 - The HAProxy config should be provided to the ambassador container using a volume mount that places the data from the 
 ConfigMap in a file at /usr/local/etc/haproxy/haproxy.cfg.
 - haproxy.cfg should contain the following configuration data:
