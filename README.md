# ubuntu-firewall

 ![linolong's GitHub stats](https://github-readme-stats.vercel.app/api?username=linolong&show_icons=true&theme=radical)

 Alibabacloud 开启实例后 ssh访问经常断掉

 ping ip 正常。
 检查后是防火墙的原因。

---

## **更新环境：**
 
 <div class="snippet" markdown="1">

```
apt update -y
```


## **安装 curl**
 
 <div class="snippet" markdown="1">

```
apt install -y curl
```
 

## **添加dns**
 
 <div class="snippet" markdown="1">

```
 echo 'nameserver 223.5.5.5'>>/etc/resolv.conf 

 echo 'nameserver 223.6.6.6'>>/etc/resolv.conf 

 echo 'nameserver 8.8.8.8'>>/etc/resolv.conf 

 echo 'nameserver 8.8.4.4'>>/etc/resolv.conf 

```

---

##  **安装ufw**
  <div class="snippet" markdown="1">

```
sudo apt-get install ufw
```
 

## **检查防火墙的状态**
 
   <div class="snippet" markdown="1">

```
sudo ufw status
```


###### 显示为inactive


## **查询防火墙版本**
 
   <div class="snippet" markdown="1">

```
sudo ufw version
```
 


## **开启/关闭防火墙**
 
  <div class="snippet" markdown="1">

```
sudo ufw enable
```

 <div class="snippet" markdown="1">

```
sudo ufw disable
```

---

## **启用**
 
   <div class="snippet" markdown="1">

```
sudo ufw enable
```

   <div class="snippet" markdown="1">

```
sudo ufw default deny
```

 
###### 运行上诉两条命令后，开启系统防火墙，且开机自启，并关闭外部对本机的访问，但本机访问外部正常。

## **开启/禁用端口**
 
   <div class="snippet" markdown="1">

```
 sudo ufw allow [service]
```

   <div class="snippet" markdown="1">

```
 sudo ufw deny [service]
```


---

## **UFW 使用范例**
 
* #### 允许 80 端口
 
   sudo ufw allow 80/tcp

* #### 禁用 80 端口
 
   sudo ufw delete allow 80/tcp

* #### 允许 smtp 端口
 
   sudo ufw allow smtp

* #### 删除 smtp 端口的许可
 
   sudo ufw delete allow smtp

* #### 允许某特定 IP 访问所有的本机端口
 
   sudo ufw allow from 192.168.xx.xxx 
 
* #### 删除某特定 IP的规则
 
   sudo ufw delete allow from 192.168.xx.xxx

* #### 另外的表达式
 
   sudo ufw allow proto udp 192.168.x.1 port 50 to 192.168.x.2 port 50
 
