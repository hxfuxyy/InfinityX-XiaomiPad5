# Руководство по получению root

## Метод 1: KernelSu-Next
Для установки KernelSu-Next просто скачайте последнюю версию менеджера [```Здесь```](https://github.com/KernelSU-Next/KernelSU-Next/releases)

## Готово!


## Метод 2: Magisk

# Что потребуется
- [```Образ Recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Перезагрузка в **fastboot**
- Загрузите NABU в **fastboot**, удерживая кнопку **`уменьшения громкости`** во время перезагрузки

- Подключите его к ПК/ноутбуку с помощью кабеля

### Загрузка модифицированного recovery
> Находясь в режиме fastboot, замените `путь\к\recovery.img` на реальный путь к файлу образа
```cmd
fastboot boot путь\к\recovery.img
```

### Установка Magisk
- Скачайте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на ПК/ноутбук
> Замените `путь\к\magisk.apk` на реальный путь к файлу magisk.apk
```cmd
adb push путь\к\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Перезагрузка в Android
> Если устройство не загружается, перезагрузите вручную, удерживая кнопку питания
```cmd
adb reboot
```

### Завершение настройки
- Настройте устройство, затем скачайте и установите [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), если он ещё не установлен.
- Откройте приложение **Magisk** и следуйте инструкциям на экране — устройство перезагрузится через несколько секунд.


## Готово!
