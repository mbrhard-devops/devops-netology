# devops-netology

# Домашнее задание к занятию «Системы контроля версий» - `Маховский Виктор`

### Инструкция по выполнению домашнего задания

1. Сделайте fork [репозитория c шаблоном решения](https://github.com/netology-code/sys-pattern-homework) к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/gitlab-hw или https://github.com/имя-вашего-репозитория/8-03-hw).
2. Выполните клонирование этого репозитория к себе на ПК с помощью команды `git clone`.
3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
   - впишите вверху название занятия и ваши фамилию и имя;
   - в каждом задании добавьте решение в требуемом виде: текст/код/скриншоты/ссылка;
   - для корректного добавления скриншотов воспользуйтесь инструкцией [«Как вставить скриншот в шаблон с решением»](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md);
   - при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md).
4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`).
5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
6. Любые вопросы задавайте в чате учебной группы и/или в разделе «Вопросы по заданию» в личном кабинете.

---

### Задание 1. Создать и настроить репозиторий для дальнейшей работы на курсе
В рамках курса вы будете писать скрипты и создавать конфигурации для различных систем, которые необходимо сохранять для будущего использования. Сначала надо создать и настроить локальный репозиторий, после чего добавить удалённый репозиторий на GitHub.

---

#### ОТВЕТ:
`Код :`
```
git clone git@github.com:mbrhard-devops/devops-netology.git
cd devops-netology
git config --global user.name "Viktor M"
git config --global user.email mbrhard.devops@gmail.com
git status
git diff
git diff --staged
git add .
git commit -m "Home 15-1 v.1"
git push -u origin main
```

---

### Создание файлов .gitignore и второго коммита
```

*.tfstate, *.tfstate.* - Содержат актуальное описание инфраструктуры
*.tfvars, *.tfvars.json - Переменные с параметрами развертывания (пароли, приватные ключи) 

.terraform/ - Локальная директория с плагинами и модулями
.terraform.tfstate.lock.info - Файл блокировки состояния
crash.log, crash.*.log - Логи сбоев Terraform

override.tf, *_override.tf - Файлы локального переопределения ресурсов
.terraformrc, terraform.rc - Персональные настройки CLI Terraform (прокси, плагины)

*.dot — файлы графов
planout — файлы планов

```

---

### Доработка

`Что будет игнорироваться:`
```
.terraform/` Любая директория с именем .terraform
*.tfstate` Любой файл с расширением tfstate
*.tfstate.* Любой файл, содержащий `.tfstate. и любым расширение (например default.tfstate.backup)
crash.log  Файл crash.log
crash.*.log Файлы, начинающиеся с crash. и с расширением .log (например crash.error.log)
*.tfvars` | Любой файл, имя которого заканчивается на .tfvars
*.tfvars.json Любой файл, имя которого заканчивается на .tfvars.json
override.tf | Файл с именем override.tf
override.tf.json Файл с именем override.tf.json
*_override.tf Любой файл, заканчивающийся на _override.tf
*_override.tf.json Любой файл, заканчивающийся на _override.tf.json
.terraform.tfstate.lock.info Файл с именем .terraform.tfstate.lock.info
!example_override.tf Ффайл example_override.tf не будет игнорироваться
*tfplan* Любой файл, в имени которого встречается tfplan
.terraformrc Файл с именем .terraformrc
terraform.rc Файл с именем terraform.rc
*.dot Любой файл заканчивающийся на .dot
planout Файл с именем planout
```

---

# Update
