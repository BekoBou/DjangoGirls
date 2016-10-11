# DjangoGurl tutorial for macOS

Данный репозиторий — следствие прохождения всех шагов для дальнейшего пояснения и срезания некоторых углов учебника.

Почему я вообще начал писать описание, в котором говорю, что надо что-то делать иначе? Всё очень просто — у меня есть свой опыт, который говорит мне, что данную задачу можно решить проще, или более правильно.

Как пример, в данном документе описан способ альтернативной установки Python 3 потому, что после использование данного метода можно всё удалить одной командой и превести компьютер в состояние, которое у него было до установки (команду приведу в конце).

## Установка

Ты можешь использовать встроенный в систему Terminal.app, но мне больше нравится [iTerm2](http://iterm2.com/).

Установку я рекомендую сделать через [Homebrew](http://brew.sh/):

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Далее ставим Python 3, с ним установится pip3, setuptools, wheel, и обновляем:

```sh
# установка python3
brew install python3
# обновляем
pip3 install --upgrade pip setuptools wheel
```

Далее установим и/или обновим [virtualenv](http://virtualenv.pypa.io/):

```sh
pip3 install --upgrade virtualenv
```

Текстовый редактор я рекомендую [Atom](https://atom.io/) или vim (входит в состав unix систем)

## Проверяем

Далее предоставлен вывод из моего терминала (префикс команд `djangoGirls ~` — это имя текущей команды и приглашение в к вводу в моём терминали, у вас он может отличаться)

```sh
djangoGirls ~ python3 --version
Python 3.5.2
djangoGirls ~ virtualenv --version
15.0.3
```

Далее приступаем к работе.

P.S. Ещё могу посоветовать шрифт для редактора и терминала — [Fira Code](https://github.com/tonsky/FiraCode)

```sh
brew tap caskroom/fonts
brew cask install font-fira-code
```

Меняем шрифт и включаем лигатуры в редакторе (Atom поддерживает из коробки, [инструкция](https://github.com/tonsky/FiraCode/wiki/Atom-instructions)) и терминале (Terminal.app поддерживает, iTerm2 поддерживает только с версии 3.1).

## Удаление

Чтобы удалить всё, что мы наустанавливали через Homebrew и через pip3, надо просто удалить Homebrew. Делается это одной команду из (FAQ)[https://github.com/Homebrew/brew/blob/master/docs/FAQ.md#how-do-i-uninstall-homebrew]. Что делает эта команда? Она скачивает скрипт, который удаляет Homebrew, но так как python3 со всеми файлами и пакетами (setuptools, wheel, pip3, virtualenv) установлен в директорию Homebrew, то всё удалится. Важно понимать, что виртуальные среды внутри проекта останутся в директории проета.

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```
