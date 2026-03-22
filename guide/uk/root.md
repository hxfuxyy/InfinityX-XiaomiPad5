# Гайд з отримання root

## Метод 1: KernelSu-Next
Для встановлення KernelSu-Next просто завантажте останню версію менеджера [```Тут```](https://github.com/KernelSU-Next/KernelSU-Next/releases)

## Готово!


## Метод 2: Magisk

# Що потрібно
- [```Образ Recovery```](https://github.com/ArKT-7/twrp_device_xiaomi_nabu/releases/tag/mod-win)
  
- [```Android Platform Tools```](https://developer.android.com/studio/releases/platform-tools)

- [```Magisk.apk```](https://github.com/topjohnwu/Magisk/releases/latest)
  
### Перезавантаження у **fastboot** 
- Завантажте NABU у **fastboot**, утримуючи кнопку **`зменшення гучності`** під час перезавантаження

- Підключіть планшет до ПК/ноутбука за допомогою кабелю

### Завантаження модифікованого recovery
> Перебуваючи в режимі fastboot, замініть `шлях\до\recovery.img` на реальний шлях до файлу образу
```cmd
fastboot boot шлях\до\recovery.img
```

### Встановлення Magisk
- Завантажте [`magisk.apk`](https://github.com/topjohnwu/Magisk/releases/latest) на ПК/ноутбук
> Замініть `шлях\до\magisk.apk` на реальний шлях до файлу magisk.apk
```cmd
adb push шлях\до\magisk.apk /tmp/magisk.zip && adb shell twrp install /tmp/magisk.zip
```

#### Перезавантаження в Android
> Якщо пристрій не завантажується, перезавантажте вручну, утримуючи кнопку живлення
```cmd
adb reboot
```

### Завершення налаштування
- Налаштуйте пристрій, потім завантажте та встановіть [Magisk](https://github.com/topjohnwu/Magisk/releases/latest), якщо він ще не встановлений.
- Відкрийте застосунок **Magisk** і дотримуйтесь інструкцій на екрані — пристрій перезавантажиться через кілька секунд.


## Готово!