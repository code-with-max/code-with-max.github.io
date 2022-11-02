---
layout: post
title: "Java keystore. Создание защищенного хранилища и пары ключей для подписи Android приложений в Godot"
categories: [GameDev, Godot]
tag:        [gamedev, godot, keystore, android]
---

# Java keystore
##### Создание защищенного хранилища и пары ключей для подписи Android приложений в Godot


Создать хранилище ключей отладки:

```bash
keytool -keyalg RSA -genkeypair -alias androiddebugkey -keypass android -keystore debug.keystore -storepass android -dname "CN=Android Debug,O=Android,C=US" -validity 9999 -deststoretype pkcs12
```


Создать хранилище ключей релиза:

```bash
keytool -v -genkey -keystore mygame.keystore -alias mygame -keyalg RSA -validity 10000
```


Сменить пароль на самом хранилище:

```bash
keytool -keypass "previous password" -new "new password" -keystore "keystore location"
```

или

```bash
keytool -storepasswd -keystore my.keystore
```


Сменить пароль на ключе:

```bash
keytool -keypasswd  -alias <key_name> -keystore my.keystore
```
