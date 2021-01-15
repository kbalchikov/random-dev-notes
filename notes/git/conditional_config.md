---
tags: [git]
title: conditional config
created: '2021-01-15T18:27:15.216Z'
modified: '2021-01-15T18:48:25.534Z'
---

# conditional config

В git есть возможность настроить email, имя и другие параметры отдельно для всех репозиториев внутри определенных каталогов. Это может быть полезно, к примеру, если вы хотите использовать определенные параметры для ваших рабочих проектов, не переопределяя глобальный конфиг гита. Для этого в каталоге `%USERPROFILE%` (`~` в Linux) найдите файл `.gitconfig` с глобальным конфигом. Рядом с ним создайте файл `.gitconfig-company` с таким содержимым:
```
[user]
	name = Firstname Lastname
	email = my@email.com
```
В `.gitconfig` в самом конце добавьте:
```
[includeIf "gitdir:C:/dev/company/"]
  path = .gitconfig-company
```
Теперь во всех гитовых проектах в каталоге `C:\dev\company` подхватываются данные из `.gitconfig-company`. Убедиться, что все работает как надо, можно гитовыми командами, вызвав их из нужного каталога:
```
git config --show-origin --get user.name
git config --show-origin --get user.email
```

Источники:
* https://git-scm.com/docs/git-config#_includes
* https://stackoverflow.com/questions/8801729/is-it-possible-to-have-different-git-configuration-for-different-projects
* https://stackoverflow.com/questions/43919191/git-2-13-conditional-config-on-windows
