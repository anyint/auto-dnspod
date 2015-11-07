#auto-DNSPOD

1.首先通过DNSPOD API获取域名的Domain ID
curl -X POST https://dnsapi.cn/Domain.List -d 'login_email=api@dnspod.com&login_password=password&format=json'

2.使用Domain ID获取所有记录的ID,并选择您需要自动更新的记录
curl -X POST https://dnsapi.cn/Record.List -d 'login_email=api@dnspod.com&login_password=password&format=json&domain_id=2317346'

3.将获取到的Domain ID、Record ID、用户名和密码替换dnspod.py中响应的内容。

4.启动脚本，并后台自动运行
python /opt/dnspod/dnspod.py > /var/log/dnspod.log 2>&1 &
