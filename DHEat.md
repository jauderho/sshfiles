# DHEat

Use these commands to address DHEat (CVE-2002-20001). See https://www.positronsecurity.com/blog/2024-04-23-an-analysis-of-dheat-dos-against-ssh-in-cloud-environments/ for more details.

```
sudo iptables -I INPUT -p tcp --dport 22 -m state --state NEW -m recent --set
sudo iptables -I INPUT -p tcp --dport 22 -m state --state NEW -m recent --update --seconds 10 --hitcount 10 -j DROP
sudo ip6tables -I INPUT -p tcp --dport 22 -m state --state NEW -m recent --set
sudo ip6tables -I INPUT -p tcp --dport 22 -m state --state NEW -m recent --update --seconds 10 --hitcount 10 -j DROP
```
