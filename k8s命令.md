###### 查看pod

`kubectl get pods -nitoa`

###### 进入pod

`kubectl exec -it itoa-task-rc-29853fbd-85f4-4f90-a56f-5472bf202474-nzkcx bash  -nitoa`

###### 查找snmp相关pod

`kubectl get po -nitoa |grep snmp`

###### 查找snmp相关pod，显示所在节点

`kubectl get po -nitoa -owide |grep snmp`

###### 查看pod的日志

`kubectl logs -f itoa-rsyslog-l45bm -nitoa`

###### 查看pod，显示对应的节点

`kubectl get po -nitoa -owide|grep itoa-rsyslog-49tss`

###### 查看pod对应的container

`docker ps |grep itoa-rsyslog-49tss`

###### 重启容器

`docker restart c98ffa5bdc03`

###### 查看pod映射出来的端口

`kubectl get svc -nitoa |grep rsyslog`
或
`kubectl get services -nitoa | grep rsyslog`

###### 查看挂载目录

`docker inspect container_name | grep Mounts -A 20`

###### 创建pod

`kubectl create -f itoa-rsyslog.yaml`

###### 删除pod

`kubectl delete -f itoa-rsyslog.yaml`

###### 修改并创建pod

`cd /opt/matrix/app/install/metadata/ITOA/components`  

`kubectl delete -f service1.yaml`
`kubectl create -f service1.yaml` 

###### 复制文件到pod里

```bash
kubectl cp net-tools-2.0-0.25.20131004git.el7.x86_64.rpm itoa/itoa-rsyslog-6bc6c4fc8b-xrjjg:/packages

# # Copy /tmp/foo local file to /tmp/bar in a remote pod in namespace <some-namespace> 
# kubectl cp /tmp/foo <some-namespace>/<some-pod>:/tmp/bar
```

###### 查看集群中其他节点的ip

`kubectl get node -o wide -n itoa`



查看pod对应的containers

`kubectl describe pod/itoa-collect-multi-8694cd59d4-gqr2t -n itoa`



Do docker images to find out the REPOSITORY and TAG of your local image. Then create a new tag for your local image :

`docker tag sa/intelligent-alarm:1.0.0 matrix-registry.h3c.com:8088/sa/intelligent-alarm:1.0.0`




