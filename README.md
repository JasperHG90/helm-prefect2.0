https://github.com/PrefectHQ/server/tree/master/helm/prefect-server

https://docs.prefect.io/orchestration/agents/kubernetes.html#requirements

1. build dockerfile
2. run orion server with

```
docker run -p 4200:4200 prefect orion start --host 0.0.0.0
```

3. create workflow and copy id

3. run agent with:

```
docker run -e PREFECT_API_URL=http://127.0.0.1:4200/api --network=host prefect agent start '<WORKFLOW-ID>'
```
