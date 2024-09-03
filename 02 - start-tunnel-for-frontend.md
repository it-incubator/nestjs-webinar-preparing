# Запуск front-end части приложения
Для того чтобы было удобнее разрабатывать наше backend-приложение, воспользуемся уже готовым [frontend-приложением](https://nest-webinar-front.vercel.app)
 
## 1. Использование тоннеля
Перейдя по ссылке мы увидим поле для ввода **Base URL**. Сюда надо вставить адрес нашего api сервера. 
Так ка наше приложени запущено локально, нам необходимо воспользоваться специальный приложением, которое
позволит делать запросы на наш backend, развернутый локально, через интернет.

### 1.1 ngrok

 - переходим на [официальный сайт ngrok](https://ngrok.com)
 - регистрируемся, логинимся
 - нас перекинет в раздел **Getting Started/Setup & Installation**
 - выбираем нужную ОС
 - выполняем в терминале 3 команды:  
1) установка ngrok  
2) настройка установка auth-token в конфиг ngrok'а   
3) запуск туннеля. Поменяем http://localhost:8080 на http://localhost:5001 (на котором запущено back-end приложение)

![ngrok](https://production-it-incubator.s3.eu-central-1.amazonaws.com/file-manager/Image/0bba4e1d-6c93-4aaf-8cd9-bf1feff9aef1_ngrok-inst.png)


 - в терминале увидим адрес туннеля:  
![ngrok-run](https://production-it-incubator.s3.eu-central-1.amazonaws.com/file-manager/Image/ed9a1505-7fd5-4f3b-9303-c765d6cf7a74_ngrok-run.png)
 - вставляем его в BaseUrl input frontend приложения:  
![baseUrl](https://production-it-incubator.s3.eu-central-1.amazonaws.com/file-manager/Image/0f3a0ab0-be30-4057-ad54-04ea84ec2433_webin-front-base-url.png)
 - Теперь можем зарегистрировать пользователя (этот эндпоинт уже реализован) и перейти на страницу со списком пользователей. Мы увидим нашего нового пользователя в списке  
![ex](https://production-it-incubator.s3.eu-central-1.amazonaws.com/file-manager/Image/0b50c6b2-409c-4879-851e-569d3f7c1951_front-ex.png)

## 1.2 localhost run
Альтернатива ngrok 
 - Просто выполняем команду в терминале 
```bush
ssh -R 80:localhost:5001 localhost.run
```
и получаем туннель тут же в терминале: https://some.life, например `https://ac2643a7c2cb3.lhr.life`