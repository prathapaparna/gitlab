# gitlab-setup

```
yum install wget -y
yum install curl postfix ca-certificates openssh-server openssh-clients  -y 
yum install policycoreutils  -y
systemctl enable sshd
systemctl start  sshd
systemctl status sshd
systemctl enable postfix
systemctl start  postfix
 systemctl status postfix
yum install firewalld  -y
systemctl enable firewalld
systemctl start firewalld
  systemctl status firewalld
firewall-cmd --permanent --add-service=http
systemctl reload firewalld
curl -sS  https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.rpm.sh | sudo bash
yum install gitlab-ee -y
rpm -qa | grep gitlab-ee
gitlab-ee-14.4.2-ee.0.el8.x86_64
ps -ax | grep gitlab-ee
15698 ?        Ss     0:00 gpg-agent --homedir /var/cache/dnf/gitlab_gitlab-ee-source-dec25c9057808fd2/pubring --use-standard-socket --daemon
16208 ?        Ss     0:00 gpg-agent --homedir /var/cache/dnf/gitlab_gitlab-ee-06493dc3ae677d64/pubring --use-standard-socket --daemon
sudo gitlab-ctl status
```

```
#Reset Password for logging to GitLab
https://docs.gitlab.com/ee/security/reset_user_password.html
sudo gitlab-rake "gitlab:password:reset"
Enter username: root
Enter password:
Confirm password:
Password successfully updated for user with username root.
#After changing password reconfigure gitlab-ctl
gitlab-ctl reconfigure
Allow the traffic in security group and find the Ip address of the server and test in the browser
http://52.91.215.236/users/sign_in
enter the reset username and password , it will display the home page of GitLab UI

```
