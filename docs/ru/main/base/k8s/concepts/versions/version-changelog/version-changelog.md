## Kubernetes 1.23.13 <a id="v1-23-13"></a>

**Важные изменения в Kubernetes:** теперь Kubernetes собран на Golang 1.17.13.

**Исправлены уязвимости:**

- [CVE-2022-3172](https://bugzilla.redhat.com/show_bug.cgi?id=2127804): агрегированный сервер API `kube-apiserver` может привести к перенаправлению клиентов.
- [CVE-2021-25749](https://bugzilla.redhat.com/show_bug.cgi?id=2127808): логика `runAsNonRoot` пропускается для Windows-контейнеров.

Подробнее об этих и других изменениях в [официальной документации Kubernetes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.23.md#v12313).

## Kubernetes 1.23.6 <a id="v1-23-6"></a>

**Изменения в сервисе Kubernetes aaS:** добавлена [интеграция с IAM облака VK Cloud](https://mcs.mail.ru/docs/ru/base/k8s/concepts/access-management).

**Важные изменения в Kubernetes:**

- Функциональность [FlexVolume](https://github.com/kubernetes/community/blob/master/sig-storage/volume-plugin-faq.md#flexvolume) переведена в статус deprecated (устаревшая).
- Функциональность специфичных [флагов для klog](https://kubernetes.io/docs/concepts/cluster-administration/system-logs/#klog) переведена в статус deprecated (устаревшая).
- Функциональность [IPv4/IPv6 dual-stack networking](https://github.com/kubernetes/enhancements/tree/master/keps/sig-network/563-dual-stack) переведена в статус general availability (публичный доступ).
- Функциональность HorizontalPodAutoscaler v2 переведена в статус general availability (публичный доступ).
- Функциональность Generic Ephemeral Volume переведена в статус general availability (публичный доступ).
- Функциональность Skip Volume Ownership change переведена в статус general availability (публичный доступ).
- Функциональность Allow CSI drivers to opt-in to volume ownership and permission change переведена в статус general availability (публичный доступ).
- Функциональность [PodSecurity](https://kubernetes.io/docs/concepts/security/pod-security-admission/) переведена в статус beta.
- `kubelet` теперь поддерживает CRI v1 API.
- Функциональность структурирования логирования переведена в статус beta.
- Функция ServerSideFieldValidation возвращает предупреждение, если объект Kubernetes в запросе содержит неизвестные или дублированные поля.
- Проверка языка выражений для CRD переведена в статус alpha.
- Функциональность OpenAPI v3 переведена в статус alpha.

Подробнее об этих и других изменениях в [официальной документации Kubernetes](https://kubernetes.io/blog/2021/12/07/kubernetes-1-23-release-announcement/).

## Kubernetes 1.22.6 <a id="v1-22-6"></a>

**Изменения в сервисе Kubernetes aaS:**

-   На узлах кластера используется операционная система [AlmaLinux](https://wiki.almalinux.org) версии 9.
-   По умолчанию устанавливается ограничение на потребляемые вычислительные ресурсы ([limit ranges](https://kubernetes.io/docs/concepts/policy/limit-range/)) для пространств имен (namespace).

**Важные изменения в Kubernetes:**

-   Компонент PodSecurityPolicy заменен на [alpha-версию PodSecurity](https://github.com/kubernetes/enhancements/issues/2579).
-   Компонент [Memory Manager](https://github.com/kubernetes/enhancements/issues/1769) переведен в статус beta.
-   Добавлена новая функциональность [API Server Tracing](https://github.com/kubernetes/enhancements/issues/647), находится в статусе alpha.
-   Добавлена новая функциональность [Generic data populators](https://github.com/kubernetes/enhancements/issues/1495) для постоянных томов (Persistent Volumes), находится в статусе alpha.
-   Добавлена новая версия формата конфигурации для kubeadm: [v1beta3](https://github.com/kubernetes/enhancements/issues/970).
-   Тперь Kubernetes control plane всегда использует [CronJobs-контроллер версии 2](https://github.com/kubernetes/enhancements/issues/19).
-   Теперь все компоненты Kubernetes control plane на узлах (включая kubelet, kube-proxy и container runtime) [могут быть запущены от имени пользователей, которые не являются суперпользователями (non-root)](https://github.com/kubernetes/enhancements/issues/2033). Эта функциональность находится в статусе alpha.

Подробнее об этих и других изменениях в [официальной документации Kubernetes](https://kubernetes.io/blog/2021/08/04/kubernetes-1-22-release-announcement/).

## Kubernetes 1.21.4 <a id="v1-21-4"></a>

**Изменения в сервисе Kubernetes aaS:** на узлах кластера используется операционная система [AlmaLinux](https://wiki.almalinux.org) версии 8.

**Важные изменения в Kubernetes:**

-   Функциональность [CronJob](https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/) переведена в статус stable.
-   Добавлена поддержка неизменяемых (immutable) [Secret](https://kubernetes.io/docs/concepts/configuration/secret/#secret-immutable) and [ConfigMap](https://kubernetes.io/docs/concepts/configuration/configmap/#configmap-immutable).
-   Добавлена поддержка [IPv4/IPv6 Dual-Stack](https://kubernetes.io/docs/concepts/services-networking/dual-stack/).
-   Добавлена поддержка [Graceful Node Shutdown](https://kubernetes.io/docs/concepts/architecture/nodes/#graceful-node-shutdown).
-   Добавлена поддержка [PersistentVolume Health Monitor](https://kubernetes.io/docs/concepts/storage/volume-health-monitoring).
-   Упрощена процедура поддержки системы сборки Kubernetes.
-   Функциональность PodSecurityPolicy [переведена в статус deprecated](https://kubernetes.io/blog/2021/04/06/podsecuritypolicy-deprecation-past-present-and-future) (устаревшая).
-   Параметр topologyKeys для Service переведен в статус deprecated (устаревший).

Подробнее об этих и других изменениях в [официальной документации Kubernetes](https://kubernetes.io/blog/2021/04/08/kubernetes-1-21-release-announcement/).

## Kubernetes 1.20.4 <a id="v1-20-4"></a>

**Изменения в сервисе Kubernetes aaS:**

-   [Среда исполнения](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) (runtime) кластера заменена на [CRI-O](https://cri-o.io/).
-   Изменен [формат хранения логов](../../../../../additionals/cases/cases-logs/case-fluent-bit).

**Важные изменения в Kubernetes:**

-   Компонент среды исполнения [Dockershim](https://kubernetes.io/blog/2022/05/03/dockershim-historical-context/) переведен в статус deprecated (устаревший).
-   Функциональность [Volume Snapshot](https://kubernetes.io/docs/concepts/storage/volume-snapshots/) Operations переведена в статус stable.
-   Функциональность [API Priority and Fairness](https://kubernetes.io/docs/concepts/cluster-administration/flow-control/) (APF) теперь включена по умолчанию.
-   Команда `kubectl alpha debug` [переведена в статус beta](https://kubernetes.io/docs/tasks/debug/debug-application/debug-running-pod/) и становится `kubectl debug`.

Подробнее об этих и других изменениях в [официальной документации Kubernetes](https://kubernetes.io/blog/2020/12/08/kubernetes-1-20-release-announcement/).
