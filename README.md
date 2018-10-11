# CentOS cloud-init-data image for GNS3 virtual appliance

Generated using the following commands:
```
echo -e "#cloud-config\npassword: centos\nchpasswd: { expire: False }\nssh_pwauth: True" > user-data
echo -e "instance-id: centos\nlocal-hostname: centos" > meta-data
mkisofs -output "centos-cloud-init-data.iso" -volid cidata -joliet -rock {user-data,meta-data}
```
