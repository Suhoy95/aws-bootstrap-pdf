# Route 53

Amazon Route 53 — это масштабируемый DNS (Domain Name System) сервис.
В менеджере бюджета нам потребуется получать электронные письма,
а также отправлять электронные уведомления. Для этого нам потребуется доменная зона,
от которой будет посылаться наши сообщения. Далее описывается, как можно
создать ее. Подразумевается, что у вас есть зарегистрированный домен и
вы можете делигировать его поддомены Амазону.

[Документация AWS Route 53 для разработчиков](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html/)

## Создание доменной зоны

![Кнопка создания доменной зоны](../img/route53-create-zone-button.png)

![Введите название вашей зоны](../img/route53-creating.png)

![Интерфейс редактирования DNS-запесей созданной зоны. Красным выделены адреса DNS-серверов Амазон, которым нужно делигировать данную подзону](../img/route53-nameservers.png)

![Для делигирования подзоны, нужно создать соответствующие NS-записи в вашем домене](../img/route53-dns.png)

После добавления этих записей придется подождать некоторое время, пока информация
о изменении DNS актуализируется в сети.

## Дополнительные источники

Сетевая служба DNS идейно производит довольно простую задачу:
каждому IP-адресу она сопоставляет какое-либо имя. В локальной
сети, вы можете настроить свой DNS-сервер и создать сайты видимые в
пределах вашей сети, что может быть удобно для компаний. Одним из
таких серверов является [BIND](https://habrahabr.ru/post/137587/).