# GPU Kubernetes Lab

## Описание

В работе был развернут одноузловой Kubernetes-кластер с NVIDIA GPU, установлен NVIDIA GPU Operator, настроен мониторинг GPU через Grafana/Prometheus и проведено сравнение трёх режимов использования GPU:

1. Exclusive GPU
2. Time-slicing
3. MPS

Для сравнения использовалась одинаковая PyTorch-нагрузка: многократное матричное умножение `torch.matmul(A, B)` на GPU Tesla T4.

## Окружение

| Параметр | Значение |
|---|---|
| OS | Ubuntu 22.04.5 LTS |
| Kubernetes | v1.34.8 |
| GPU | Tesla T4 |
| GPU memory | 14.56 GB |
| NVIDIA Driver | 580.105.08 |
| CUDA runtime | 13.0 |
| Container runtime | containerd |

## Структура репозитория

```text
report/       — PDF-отчёт
manifests/    — Kubernetes YAML-манифесты и конфиги device plugin
logs/         — логи benchmark-запусков