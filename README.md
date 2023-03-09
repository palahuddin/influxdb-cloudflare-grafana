# Worker Script Generate Cloudflare Data to InfluxDB Grafana

Reference: https://github.com/jorgedlcruz/cloudflare-grafana

## CronJob Get CloudFlare Data

```bash
kubectl delete secret influxdbv1-worker
kubectl create secret generic influxdbv1-worker --from-file=script=cf.sh
kubectl delete -f influx-db-worker.yaml --grace-period=0 --force
kubectl apply -f influx-db-worker.yaml
sleep 10
kubectl logs -f pod/influxdbv1-worker 
```
