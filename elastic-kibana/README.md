# Start Elastic and Kibana
```
docker-compose up -d
```
Access Kibana UI
```
curl localhost:5601
```

# Journalbeat
For example you can collect logs from syslog

Install journalbeat on each machine

Manually:

https://github.com/evsq/linux/blob/master/guides/journalbeat

Ansible:

https://github.com/evsq/ansible/tree/master/journalbeat