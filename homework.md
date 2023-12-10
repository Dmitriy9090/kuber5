# Создать простой Под (можно использовать тот же, что был на Семинаре). Под должен собирать данные из разных Секретов. Например: username и password брать из одного Секрета, а address и что-то еще (любой параметр) — из другого.

## В первую очередь создадим секреты, с помощью двух разных манифестов

![screen](secret.png)

![screen](secret1.png)

- запустим их поочередной командой **kubeclt apply -f secret.yaml** и соответсвенно **kubeclt apply -f secret.yaml**
- проверим, что секреты созданы командой **kubectl get secrets -n homework**

![screen](secret_run.png)
## Создадим сущность deployment, с помощью манифеста nginx.yaml

![screen](deploy.png)

- командой **kubectl get deploy -n homework** проверяем что deployment создан.

![screen](deploy_run.png)

## Проверяем, что deploy подхавтил секреты из наших файлов **secret.yaml и secret1.yaml** командой *kubectl logs -n homework deployments/secret-deploy nginx*.

![screen](final.png).