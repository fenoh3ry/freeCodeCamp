<table>
    <tr>
        <td> Прочтите эти рекомендации на </td>
        <td><a href='/CONTRIBUTING.md'> English </a></td>
        <td><a href='/docs/chinese/CONTRIBUTING.md'> 中文 </a></td>
        <td><a href='/docs/russian/CONTRIBUTING.md'> Русском </a></td>
        <td><a href='/docs/arabic/CONTRIBUTING.md'> عربى </a></td>
        <td><a href='/docs/spanish/CONTRIBUTING.md'> Español </a></td>
        <td><a href='/docs/portuguese/CONTRIBUTING.md'> Português </a></td>
    </tr>
</table>

# Как локально отлавливать получение исходящих электронных писем без их реальной отправки (требуется только для рабочих процессов электронной почты)

> **Заметка:** Это **необязательный** шаг - требуется только при работе с рабочими процессами электронной почты

## Вступление

Некоторые рабочие процессы электронной почты (например обновление электронной почты пользователя) требуют чтобы внутренний сервер через api отправлял электронные письма. Во время разработки вы можете использовать инструмент для локального отлавливания электронной почты, вместо того чтобы использовать реального поставщика электронной почты и отправлять реальные электронные письма. MailHog - это один из таких средств тестирования электронной почты для разработчиков, который ловит электронные письма, отправляемые вашим локальным экземпляром freeCodeCamp.

## Установка MailHog

Установите и запустите MailHog (зависит от установленной ОС):


- [Установка MailHog на macOS](#installing-mailhog-on-macos)
- [Установка MailHog на Windows](#installing-mailhog-on-windows)
- [Установка MailHog на Linux](#installing-mailhog-on-linux)

### Установка MailHog на macOS

 
Как установить MailHog на macOS с помощью [Homebrew](https://brew.sh/):



```bash
brew install mailhog
brew services start mailhog
```

Данные команды установят и запустят службу MailHog в фоновом режиме.

Затем вы можете перейти к непосредственному [использованию MailHog](#using-mailhog).

### Установка MailHog на Windows

Загрузите последнюю версию MailHog с [официального репозитория](https://github.com/mailhog/MailHog/releases). Выберите ссылку для вашей версии Windows (32 или 64 бит) и файл .exe будет загружен на ваш компьютер.

После завершения загрузки, кликните на файл. Возможно, вы получите уведомление брандмауэра Windows где вам нужно будет разрешить доступ к MailHog. Как только вы это сделаете, стандартная подсказка командной строки Windows откроется с уже запущенным MailHog.

Чтобы закрыть MailHog, закройте командную строку. Чтобы запустить его снова, кликните тот же файл .exe. Вам не нужно загружать каждый раз новый файл.

Затем вы можете перейти к [использованию MailHog](#using-mailhog).

### Установка MailHog на Linux

Сначала установите [Go](https://golang.org).

Для систем на базе Debian, таких как Ubuntu и Linux Mint, выполните команду:


```bash
sudo apt-get install golang
```

Для CentOS, Fedora, Red Hat Linux и других систем на основе RPM выполните команду:

```bash
sudo dnf install golang
```

Или:

```bash
sudo yum install golang
```


Задайте путь к Go:

```bash
echo "export GOPATH=$HOME/go" >> ~/.profile
echo 'export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin' >> ~/.profile
source ~/.profile
```

Затем установите и запустите MailHog:

```bash
go get github.com/mailhog/MailHog
sudo cp /home/$(whoami)/go/bin/MailHog /usr/local/bin/mailhog
mailhog
```
Теперь вы можете перейти к [использованию MailHog](#using-mailhog).

## Использование MailHog

После того, как вы установили MailHog и запустили его, вам нужно открыть почтовый ящик MailHog в своем браузере, открыть новую вкладку или окно и перейти по адресу [http://localhost:8025](http://localhost:8025).

Теперь вы должны увидеть экран, как показано ниже:

![MailHog Скриншот 1](/docs/images/mailhog/1.jpg)

Когда ваша freeCodeCamp сборка отправит электронное письмо, вы увидите его на экране, как показано ниже:

![MailHog Скриншот 2](/docs/images/mailhog/2.jpg)

Откройте почту, и вы увидите две вкладки, где вы можете просмотреть содержимое: обычный текст и источник. Убедитесь, что вы находитесь на вкладке обычного текста.

![MailHog Скриншот 3](/docs/images/mailhog/3.jpg)

Любые ссылки в письме так же должны быть доступны для просмотра.

## Полезные ссылки

- По любым другим вопросам, связанным с MailHog или инструкциями по пользовательским настройкам, вы можете ознакомиться в [официальном репозитории MailHog](https://github.com/mailhog/MailHog).
