# Catalogo-ops

[Repositório de Código](https://github.com/Adenilson365/devopslabs01-catalogo)

- Armazena os manifestos a serem aplicados no Kubernetes usando ArgoCD.

### Estrutura de pastas

```
.
├── application
│   ├── config
│   │   └── otel-configmap.yaml
│   ├── deployments
│   │   └── deployment.yaml
│   └── services
│       └── service.yaml
└── README.md

```

### Dependências de aplicação

- Banco de dados Postgres

### Aplicar no cluster antes dessa aplicação:

- Configmap db-config
- Secrets: catalogo-secret

- db-config

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: db-config
  namespace: api
data:
  DB_HOST: "<Host-DB>"
```

- catalogo-secret

```YAML
apiVersion: v1
kind: Secret
metadata:
  name: catalogo-secret
  namespace: api
type: Opaque
data:
  DB_USER: user
  DB_PASSWORD: pass
  DB_DATABASE: database
```

### Changes:

- 18/04/2024 - Adiciona hook para alertas durante etapas de sync para canal telegram.
