Склонировать репоз + все сабмодули:
$ git clone https://github.com/chaconinc/MainProject
$ git submodule init # инициализация конфигурационного файла (файлов) сабмодулей
$ git submodule update # извлечение данных всех сабмодулей и переключение на коммит, указанный в основном проекте (в конфиг. файле сабмодулей)

$ git clone --recursive https://github.com/chaconinc/MainProject # или вот так вместо трех предыщущих команд

Как внести изменения в сабмодуль:
$ cd <submodule>
$ git checkout master # или другой бранч, т.к. по дефолту сабмодуль находится в detached HEAD режиме
$ git commit -am 'unicode support' # делаем коммит

Как скачать изменения в сабмодулях (rebase или merge на ваш вкус):
$ git submodule update --remote --rebase
$ git submodule update --remote --merge


Как пушить коммиты:
1. Либо пушим вначале изменения во все сабмодули, а потом в основной репоз
2. Либо делаем это одной командой из основного репоза:
$ git push --recurse-submodules=check # пушит изменения в основном репозитории, но перед этим проверяет, нет ли незакомиченных изменений в сабмодулях. Если таковые есть, то прерывает процесс
$ git push --recurse-submodules=on-demand # пушит все коммиты в сабмодулях, а также в основной модуль