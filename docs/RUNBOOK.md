# Runbook

## Service

- Name: `receipt-api`
- Team: `Commerce`
- Owner: `mooref068@gmail.com`
- Cost center: `commerce`

## First Checks

```bash
kubectl get rollout receipt-api -n receipt-api-dev
kubectl get pods -l app.kubernetes.io/name=receipt-api -n receipt-api-dev
kubectl logs -l app.kubernetes.io/name=receipt-api -n receipt-api-dev
```

## Health

```bash
curl https://receipt-api.dev.platform.ohanyere.internal/healthz
curl https://receipt-api.dev.platform.ohanyere.internal/readyz
curl https://receipt-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo receipt-api -n receipt-api-dev
```

Escalate to `Commerce` through `mooref068@gmail.com` if rollback does not restore service.
