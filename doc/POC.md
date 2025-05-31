# ArgoCD Proof of Concept (POC) Demo

## Опис

Цей документ містить покрокову інструкцію для розгортання ArgoCD в Kubernetes кластері та отримання доступу до веб-інтерфейсу ArgoCD для демонстрації можливостей платформи.

## Передумови

- Встановлений k3d (Kubernetes in Docker)
- Встановлений kubectl
- Docker Desktop або інший container runtime

## Покрокова інструкція

### Крок 1: Створення Kubernetes кластера

```bash
k3d cluster create argo
```

Створює новий Kubernetes кластер з назвою "argo" за допомогою k3d.

### Крок 2: Перевірка статусу кластера

```bash
kubectl cluster-info
```

Перевіряє статус створеного кластера та виводить інформацію про API сервер.

### Крок 3: Створення namespace для ArgoCD

```bash
kubectl create namespace argocd
```

Створює окремий namespace "argocd" для компонентів ArgoCD.

### Крок 4: Встановлення ArgoCD

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Встановлює ArgoCD, завантажуючи офіційний маніфест з GitHub та застосовуючи його в namespace argocd.

### Крок 5: Доступ до веб-інтерфейсу ArgoCD

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Налаштовує port forwarding - перенаправляє локальний порт 8080 на ArgoCD сервер. Після цього веб-інтерфейс доступний за https://localhost:8080

## Демонстрація роботи

### Відео демонстрація

📹 **Повна демонстрація процесу встановлення та запуску ArgoCD доступна за посиланням:**
[ArgoCD Demo Video](https://drive.google.com/file/d/1YJQX91_Iclz_8l2YnHDyWRhlwGYhOg09/view?usp=sharing)

### Що показано в демо:

1. **Створення кластера** - виконання команди `k3d cluster create argo`
2. **Перевірка кластера** - виконання `kubectl cluster-info`
3. **Створення namespace** - виконання `kubectl create namespace argocd`
4. **Встановлення ArgoCD** - застосування маніфесту з офіційного репозиторію
5. **Доступ до інтерфейсу** - демонстрація роботи з веб-інтерфейсом ArgoCD

## Функціональність ArgoCD

### Основні можливості, продемонстровані в POC:

- **GitOps workflow** - автоматизоване розгортання додатків з Git репозиторіїв
- **Веб-інтерфейс** - зручний UI для управління додатками
- **Sync статус** - відстеження стану синхронізації між Git та кластером
- **Application health** - моніторинг здоров'я додатків
- **Rollback capabilities** - можливість відкату до попередніх версій

## Переваги ArgoCD

1. **Декларативний підхід** - конфігурація зберігається в Git
2. **Автоматична синхронізація** - автоматичне оновлення додатків
3. **Візуалізація** - графічне представлення стану додатків
4. **Безпека** - RBAC та інтеграція з різними провайдерами аутентифікації
5. **Multi-cluster support** - управління кількома кластерами

## Довідкові матеріали

- [Офіційна документація ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
- [ArgoCD Getting Started Guide](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [k3d Documentation](https://k3d.io/)

---

**Дата створення POC:** ${new Date().toLocaleDateString('uk-UA')}  
**Статус:** ✅ Успішно протестовано# ArgoCD Proof of Concept (POC) Demo

## Опис

Цей документ містить покрокову інструкцію для розгортання ArgoCD в Kubernetes кластері та отримання доступу до веб-інтерфейсу ArgoCD для демонстрації можливостей платформи.

## Передумови

- Встановлений k3d (Kubernetes in Docker)
- Встановлений kubectl
- Docker Desktop або інший container runtime

## Покрокова інструкція

### Крок 1: Створення Kubernetes кластера

```bash
k3d cluster create argo
```

Створює новий Kubernetes кластер з назвою "argo" за допомогою k3d.

### Крок 2: Перевірка статусу кластера

```bash
kubectl cluster-info
```

Перевіряє статус створеного кластера та виводить інформацію про API сервер.

### Крок 3: Створення namespace для ArgoCD

```bash
kubectl create namespace argocd
```

Створює окремий namespace "argocd" для компонентів ArgoCD.

### Крок 4: Встановлення ArgoCD

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Встановлює ArgoCD, завантажуючи офіційний маніфест з GitHub та застосовуючи його в namespace argocd.

### Крок 5: Доступ до веб-інтерфейсу ArgoCD

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

Налаштовує port forwarding - перенаправляє локальний порт 8080 на ArgoCD сервер. Після цього веб-інтерфейс доступний за https://localhost:8080

## Демонстрація роботи

### Відео демонстрація

📹 **Повна демонстрація процесу встановлення та запуску ArgoCD доступна за посиланням:**
[ArgoCD Demo Video](https://drive.google.com/file/d/1YJQX91_Iclz_8l2YnHDyWRhlwGYhOg09/view?usp=sharing)

### Що показано в демо:

1. **Створення кластера** - виконання команди `k3d cluster create argo`
2. **Перевірка кластера** - виконання `kubectl cluster-info`
3. **Створення namespace** - виконання `kubectl create namespace argocd`
4. **Встановлення ArgoCD** - застосування маніфесту з офіційного репозиторію
5. **Доступ до інтерфейсу** - демонстрація роботи з веб-інтерфейсом ArgoCD

## Функціональність ArgoCD

### Основні можливості, продемонстровані в POC:

- **GitOps workflow** - автоматизоване розгортання додатків з Git репозиторіїв
- **Веб-інтерфейс** - зручний UI для управління додатками
- **Sync статус** - відстеження стану синхронізації між Git та кластером
- **Application health** - моніторинг здоров'я додатків
- **Rollback capabilities** - можливість відкату до попередніх версій

## Переваги ArgoCD

1. **Декларативний підхід** - конфігурація зберігається в Git
2. **Автоматична синхронізація** - автоматичне оновлення додатків
3. **Візуалізація** - графічне представлення стану додатків
4. **Безпека** - RBAC та інтеграція з різними провайдерами аутентифікації
5. **Multi-cluster support** - управління кількома кластерами

## Довідкові матеріали

- [Офіційна документація ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
- [ArgoCD Getting Started Guide](https://argo-cd.readthedocs.io/en/stable/getting_started/)
- [k3d Documentation](https://k3d.io/)

---

**Дата створення POC:** ${new Date().toLocaleDateString('uk-UA')}  
**Статус:** ✅ Успішно протестованоv