# Установка Podkop
Пакет работает на всех архитектурах.
Будет точно работать только на OpenWrt 23.05.

Нужен dnsmasq-full. В автоматическом режиме ставится сам. Вручную надо поставить [самостоятельно](https://github.com/itdoginfo/podkop/blob/952dd6215a2a83d65937cf9e33534c42809091ed/install.sh#L20).

## Автоматическая
```
sh <(wget -O - https://raw.githubusercontent.com/virfev/podkop-v0.2.5/refs/heads/main/install.sh)
```

Скрипт также предложит выбрать, какой туннель будет использоваться. Для выбранного туннеля будут установлены нужные пакеты, а для Wireguard и AmneziaWG также будет предложена автоматическая настройка - прямо в консоли скрипт запросит данные конфига. Для AmneziaWG можно также выбрать вариант с использованием конфига обычного Wireguard и автоматической обфускацией до AmneziaWG.

Для AmneziaWG скрипт проверяет наличие пакетов под вашу платформу в [стороннем репозитории](https://github.com/Slava-Shchipunov/awg-openwrt/releases), так как в официальном репозитории OpenWRT они отсутствуют, и автоматически их устанавливает.

# Обновление
Скрипт обнаружит уже установленный podkop и предложит обновиться. Подтягивается актуальная версия из репозитория [itdoginfo](https://github.com/itdoginfo/podkop)
```
sh <(wget -O - https://raw.githubusercontent.com/virfev/podkop-v0.2.5/refs/heads/main/install.sh)
```

# Удаление
```
opkg remove luci-app-podkop podkop
```

Если был установлен русский язык
```
opkg remove luci-i18n-podkop-ru
```
