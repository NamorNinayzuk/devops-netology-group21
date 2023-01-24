# Домашнее задание к занятию "1. Инфраструктура как код"

## Задача 1. Выбор инструментов. 
 
### Легенда
 
Через час совещание на котором менеджер расскажет о новом проекте. Начать работу над которым надо 
будет уже сегодня. 
На данный момент известно, что это будет сервис, который ваша компания будет предоставлять внешним заказчикам.
Первое время, скорее всего, будет один внешний клиент, со временем внешних клиентов станет больше.

Так же по разговорам в компании есть вероятность, что техническое задание еще не четкое, что приведет к большому
количеству небольших релизов, тестирований интеграций, откатов, доработок, то есть скучно не будет.  
   
Вам, как девопс инженеру, будет необходимо принять решение об инструментах для организации инфраструктуры.
На данный момент в вашей компании уже используются следующие инструменты: 
- остатки Сloud Formation, 
- некоторые образы сделаны при помощи Packer,
- год назад начали активно использовать Terraform, 
- разработчики привыкли использовать Docker, 
- уже есть большая база Kubernetes конфигураций, 
- для автоматизации процессов используется Teamcity, 
- также есть совсем немного Ansible скриптов, 
- и ряд bash скриптов для упрощения рутинных задач.  

Для этого в рамках совещания надо будет выяснить подробности о проекте, что бы в итоге определиться с инструментами:

1. Какой тип инфраструктуры будем использовать для этого проекта: изменяемый или не изменяемый?
1. Будет ли центральный сервер для управления инфраструктурой?
1. Будут ли агенты на серверах?
1. Будут ли использованы средства для управления конфигурацией или инициализации ресурсов? 
 
В связи с тем, что проект стартует уже сегодня, в рамках совещания надо будет определиться со всеми этими вопросами.

### В результате задачи необходимо

1. Ответить на четыре вопроса представленных в разделе "Легенда". 
1. Какие инструменты из уже используемых вы хотели бы использовать для нового проекта? 
1. Хотите ли рассмотреть возможность внедрения новых инструментов для этого проекта? 

Если для ответа на эти вопросы недостаточно информации, то напишите какие моменты уточните на совещании.

### \\..42:
Добрый день уважаемые коллеги мы все привыкли к Docker и K8s, и есть ли смысл в Terraform и Packer? Зачем нам лучшее, комфортное и легкое,  если мы про и можем развернуть изменяемую инфраструктуру с оркестром K8s с контейнерами Docker! Сразу будем бить тяжелой артиллерией по воробьям чтоб аж орлы обоср...простите за мой французкий с помощью Ansible мы и без смит-агентов проживем. В части же приватных облаков нужно использовать управлением конфигураций, а иницилизацию ресурсов оставил для публичного облака.


## Задача 2. Установка Terraform. 

[Официальный сайт Terraform](https://www.terraform.io/).   
В связи с недоступностью ресурсов для загрузки Terraform на территории РФ, вы можете воспользоваться VPN или использовать зеркало YandexCloud:      
[Ссылки для установки открытого ПО](https://github.com/netology-code/devops-materials/blob/master/README.md)

Установите терраформ при помощи менеджера пакетов используемого в вашей операционной системе.
В виде результата этой задачи приложите вывод команды `terraform --version`.

### \\..42:
![image](https://user-images.githubusercontent.com/109209673/214405864-29737885-2b9b-46fb-8452-40d05738b8b3.png)


## Задача 3. Поддержка легаси кода. 

В какой-то момент вы обновили терраформ до новой версии, например с 0.12 до 0.13. 
А код одного из проектов настолько устарел, что не может работать с версией 0.13. 
В связи с этим необходимо сделать так, чтобы вы могли одновременно использовать последнюю версию терраформа установленную при помощи
штатного менеджера пакетов и устаревшую версию 0.12. 

В виде результата этой задачи приложите вывод `--version` двух версий терраформа доступных на вашем компьютере 
или виртуальной машине.


### \\..42:

запускаем через symlink
                                                                                                                                                                                                         
┌──(root㉿kali)
└─# ls -lah /home/kali/Downloads/terraform-0.12.0                                 
total 404K
drwxrwxr-x 39 kali kali 4.0K Jan 24 15:07 .
drwxr-xr-x  3 kali kali 4.0K Jan 24 15:03 ..
drwxrwxr-x  2 kali kali 4.0K May 22  2019 addrs
drwxrwxr-x  7 kali kali 4.0K May 22  2019 backend
-rw-rw-r--  1 kali kali 1.8K May 22  2019 BUILDING.md
drwxrwxr-x  5 kali kali 4.0K May 22  2019 builtin
-rw-rw-r--  1 kali kali  13K May 22  2019 CHANGELOG.md
-rw-rw-r--  1 kali kali 2.0K May 22  2019 checkpoint.go
-rw-rw-r--  1 kali kali  165 May 22  2019 CODEOWNERS
drwxrwxr-x 11 kali kali 4.0K May 22  2019 command
-rw-rw-r--  1 kali kali 9.2K May 22  2019 commands.go
drwxrwxr-x  6 kali kali 4.0K May 22  2019 communicator
drwxrwxr-x  5 kali kali 4.0K May 22  2019 config
-rw-rw-r--  1 kali kali 9.2K May 22  2019 config.go
drwxrwxr-x  6 kali kali 4.0K May 22  2019 configs
-rw-rw-r--  1 kali kali 6.1K May 22  2019 config_test.go
-rw-rw-r--  1 kali kali 1.1K May 22  2019 config_unix.go
-rw-rw-r--  1 kali kali  852 May 22  2019 config_windows.go
drwxrwxr-x  5 kali kali 4.0K May 22  2019 contrib
drwxrwxr-x  2 kali kali 4.0K May 22  2019 dag
drwxrwxr-x  2 kali kali 4.0K May 22  2019 digraph
-rw-rw-r--  1 kali kali  837 May 22  2019 Dockerfile
drwxrwxr-x  3 kali kali 4.0K May 22  2019 docs
drwxrwxr-x  2 kali kali 4.0K May 22  2019 e2e
drwxrwxr-x  3 kali kali 4.0K May 22  2019 examples
drwxrwxr-x  2 kali kali 4.0K May 22  2019 flatmap
drwxrwxr-x  3 kali kali 4.0K May 22  2019 .github
-rw-rw-r--  1 kali kali  359 May 22  2019 .gitignore
-rw-rw-r--  1 kali kali 6.2K May 22  2019 go.mod
-rw-rw-r--  1 kali kali  53K May 22  2019 go.sum
-rw-rw-r--  1 kali kali    7 May 22  2019 .go-version
drwxrwxr-x 26 kali kali 4.0K May 22  2019 helper
-rw-rw-r--  1 kali kali 2.4K May 22  2019 help.go
drwxrwxr-x  2 kali kali 4.0K May 22  2019 httpclient
drwxrwxr-x  6 kali kali 4.0K May 22  2019 internal
drwxrwxr-x  5 kali kali 4.0K May 22  2019 lang
-rw-rw-r--  1 kali kali  16K May 22  2019 LICENSE
-rw-rw-r--  1 kali kali 9.3K May 22  2019 main.go
-rw-rw-r--  1 kali kali 5.3K May 22  2019 main_test.go
-rw-rw-r--  1 kali kali 5.6K May 22  2019 Makefile
drwxrwxr-x  2 kali kali 4.0K May 22  2019 moduledeps
-rw-rw-r--  1 kali kali 2.1K May 22  2019 panic.go
drwxrwxr-x  5 kali kali 4.0K May 22  2019 plans
drwxrwxr-x  5 kali kali 4.0K May 22  2019 plugin
-rw-rw-r--  1 kali kali  882 May 22  2019 plugins.go
drwxrwxr-x  2 kali kali 4.0K May 22  2019 providers
drwxrwxr-x  2 kali kali 4.0K May 22  2019 provisioners
-rw-rw-r--  1 kali kali 8.6K May 22  2019 README.md
drwxrwxr-x  5 kali kali 4.0K May 22  2019 registry
drwxrwxr-x  3 kali kali 4.0K May 22  2019 repl
drwxrwxr-x  3 kali kali 4.0K May 22  2019 scripts
-rw-rw-r--  1 kali kali  159 May 22  2019 signal_unix.go
-rw-rw-r--  1 kali kali  128 May 22  2019 signal_windows.go
drwxrwxr-x  4 kali kali 4.0K May 22  2019 state
drwxrwxr-x  4 kali kali 4.0K May 22  2019 states
drwxrwxr-x  4 kali kali 4.0K May 22  2019 svchost
-rw-rw-r--  1 kali kali  637 May 22  2019 synchronized_writers.go
drwxrwxr-x  3 kali kali  12K May 22  2019 terraform
drwxrwxr-x  2 kali kali 4.0K May 22  2019 test-fixtures
-rw-rw-r--  1 kali kali  251 May 22  2019 .tfdev
drwxrwxr-x  2 kali kali 4.0K May 22  2019 tfdiags
drwxrwxr-x  4 kali kali 4.0K May 22  2019 tools
-rw-rw-r--  1 kali kali 1.5K May 22  2019 .travis.yml
-rw-rw-r--  1 kali kali 3.0K May 22  2019 Vagrantfile
drwxrwxr-x  8 kali kali 4.0K May 22  2019 vendor
drwxrwxr-x  2 kali kali 4.0K May 22  2019 version
-rw-rw-r--  1 kali kali  241 May 22  2019 version.go
drwxrwxr-x  7 kali kali 4.0K May 22  2019 website
                                                                                                                                                                                                           
┌──(root㉿kali)
└─# sudo ln -s /home/kali/Downloads/terraform-0.12.0  /usr/local/bin/terraform0.12.31
                                                                                                                                                                                                           
┌──(root㉿kali)
└─# terraform0.12.31 -version                                                               
Terraform v0.12.31
on linux_amd64

Your version of Terraform is out of date! The latest version
is 1.3.7. You can update by downloading from https://www.terraform.io/downloads.html
                                                                                                                                                                                                           
┌──(root㉿kali)
└─# terraform -version 
Terraform v1.3.6
on linux_amd64

---

### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---
