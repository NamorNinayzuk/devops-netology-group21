Домашнее задание к занятию "5. Оркестрация кластером Docker контейнеров на примере Docker Swarm"
Как сдавать задания
Обязательными к выполнению являются задачи без указания звездочки. Их выполнение необходимо для получения зачета и диплома о профессиональной переподготовке.
Задачи со звездочкой (*) являются дополнительными задачами и/или задачами повышенной сложности. Они не являются обязательными к выполнению, но помогут вам глубже понять тему.
Домашнее задание выполните в файле readme.md в github репозитории. В личном кабинете отправьте на проверку ссылку на .md-файл в вашем репозитории.
Любые вопросы по решению задач задавайте в чате учебной группы.
________________________________________
Важно!
Перед отправкой работы на проверку удаляйте неиспользуемые ресурсы. Это важно для того, чтоб предупредить неконтролируемый расход средств, полученных в результате использования промокода.
Подробные рекомендации здесь
________________________________________
Задача 1
Дайте письменные ответы на следующие вопросы:
•	В чём отличие режимов работы сервисов в Docker Swarm кластере: replication и global?
•	Какой алгоритм выбора лидера используется в Docker Swarm кластере?
•	Что такое Overlay Network?
#############################################################################
## ОтветЪ
Для replicated указывают сколько идентичных задач нужно запустить, например можно развернуть  сервис HTTP с тремя репликами, каждая из которых обслуживает один и тот же контент. А вот global – запускает одну задачу на каждой ноде, при этом предварительного заданного количества задач нет. Каждый раз, когда будет добавлена нода в рой, оркестратор будет создавать задачу, а планировщик назначать новой ноде задачу.
#############################################################################
Задача 2
Создать ваш первый Docker Swarm кластер в Яндекс.Облаке
Для получения зачета, вам необходимо предоставить скриншот из терминала (консоли), с выводом команды:
docker node ls

#############################################################################
## ОтветЪ


#############################################################################

Задача 3
Создать ваш первый, готовый к боевой эксплуатации кластер мониторинга, состоящий из стека микросервисов.
Для получения зачета, вам необходимо предоставить скриншот из терминала (консоли), с выводом команды:
docker service ls

#############################################################################
## ОтветЪ


#############################################################################

Задача 4 (*)
Выполнить на лидере Docker Swarm кластера команду (указанную ниже) и дать письменное описание её функционала, что она делает и зачем она нужна:
# см.документацию: https://docs.docker.com/engine/swarm/swarm_manager_locking/
docker swarm update --autolock=true

