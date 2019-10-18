使用pemkey登陆linux su -i 切换到root 

设置root的密码
sudo passwd root #输入2次密码给root用户设定密码

sed -ri 's/^#?(PasswordAuthentication)\s+(yes|no)/\1 yes/' /etc/ssh/sshd_config
sed -ri 's/^#?(PermitRootLogin)\s+(yes|no)/\1 yes/' /etc/ssh/sshd_config #修改配置文件
sed -ri 's/^/#/;s/sleep 10"\s+/&\n/' /root/.ssh/authorized_keys

vi /etc/ssh/sshd_config PasswordAuthentication yes  #运行使用密码登陆
service sshd restart
touch /root/.Xauthority