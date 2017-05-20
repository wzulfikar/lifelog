# ubuntu ntp
- if using aws, open outbound port 123 (anywhere) to allow ntp ← u've got bitten by this once, wildan (Wed, 26 Apr 2017)
- restart ntp (and reload latest config) 

```
sudo service ntp stop # stop ntp
sudo ntpd -gq -c /etc/ntp.conf # reload config
sudo service ntp start # start ntp again
```
- check ntp status: `ntpq -p`

http://time.to.pullthepl.ug/blog/2012/8/29/easy-ntp-stats-without-ntpstat/

http://stackoverflow.com/questions/29418250/is-there-an-ntp-server-i-should-be-using-when-using-amazons-ec2-service-to-comb

---

Note:
time spent to figure this: 45 mins


---

manually adjust clock using google's time:
`sudo date -s "$(curl -s --head http://google.com | grep ^Date: | sed 's/Date: //g')"`
ref: https://superuser.com/questions/635020/how-to-know-current-time-from-internet-from-command-line-in-linux
