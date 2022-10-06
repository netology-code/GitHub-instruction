# Инструкция по работе с GitHub

### Навигация:
* [Для чего нужен GitHub](#about)
* [Основные термины](#basicTerms)
* [Регистрация и установка GitHub](#registration)
* [Создание и клонирование репозитория](#createRep)
* [Редактирование файлов](#edit)
* [Работа с разметкой](#markdown)
  
## <a name="about"></a> Для чего нужен GitHub

Нередко в процессе работы перед программистом встает необходимость **публикации своего проекта в общедоступных ресурсах или же синхронизация проделанной работы** с остальными участниками процесса. 

> **Q:** Почему бы просто не сохранять файлы в каком-либо облачном хранилище?  
> **A:** Действительно! Ответ найден, дальнейшие рассуждения бессмысленны.

![no](img/no.gif)
  
Однако в реальности все не так просто. Мы можем воспользоваться облачным хранилищем в случае, если нам необходимо сохранить свой проект до лучших времен, **но развернуть сайт или даже произвести элементарные изменения в коде, непосредственно в облаке, у нас скорее всего не получится**. 

Cущественно осложняет процесс сохранения проекта и возможная необходимость синхронизации вносимых изменений нами и нашими коллегами. Представьте что вы работаете в команде, где над одним файлом в разное время может трудиться несколько человек. В таком случае внесение любых изменений может осуществляться посредством загрузки актуальной версии файла с перезаписью предыдущей. *Но что если изменения вносятся параллельно?* Вероятно придется составлять файл вручную, учитывая все возможные версии файла. *А как быть в ситуации если сотрудники живут в разных часовых поясах? Как хранить историю изменений, авторов, даты внесения правок?*

Все эти вопросы и сложности должны натолкнуть нас на мысль о написании некоторой программы для автоматизации всех процессов связанных с храненим данных, но к счатью подобные программы уже разработаны и доступны нам для использования. Подобные программы принято называть распределенными системами хранения версий *(git)*, а одной из крупнейших таких систем является **GitHub**.

## <a name="basicTerms"></a> Основные термины
Перед началом работы с GitHub рекомендуем вам ознакомиться с базовыми понятиями:
* **Git или Гит** — система контроля и управления версиями файлов.

* **GitHub или Гитхаб** — веб-сервис для размещения репозиториев и совместной разработки проектов.

* <a name="repo"></a>**Репозиторий** — каталог файловой системы, в котором находятся: файлы конфигурации, файлы журналов операций, выполняемых над репозиторием, индекс расположения файлов и хранилище, содержащее сами контролируемые файлы.

* <a name="branch"></a>**Ветка (Branch)** — это параллельная версия репозитория. Она включена в этот репозиторий, но не влияет на главную версию, тем самым позволяя свободно работать в параллельной. Когда вы внесли нужные изменения, то вы можете объединить их с главной версией.

* <a name="fork"></a>**Форк (Fork)** — копия репозитория. Его также можно рассматривать как внешнюю ветку для текущего репозитория. Копия вашего открытого репозитория на Гитхабе может быть сделана любым пользователем, после чего он может прислать изменения в ваш репозиторий через пулреквест.

*  <a name="clone"> **Клонирование (Clone)** — скачивание репозитория с удалённого сервера на локальный компьютер в определённый каталог для дальнейшей работы с этим каталогом как с репозиторием.

## <a name="registration"></a> Регистрация и установка GitHub
Чтобы начать работу с сервисом GitHub, вам необходимо завести учетную запись.  
Для регистрации аккаунта перейдите на [официальный сайт GitHub](https://github.com/) и нажмите на кнопку "Sign Up" (зарегистрироваться).

![img](img/img1.png)

В процессе регистрации вам будет предложено ввести обязательные данные:
* адрес электронной почты
* пароль
* имя пользователя

![img](img/img2.png)

После регистрации на указанную вами почту придет письмо с просьбой подтверждения регистрации. Для завершения регистрации пройдите по ссылке, указанной в письме.

<a name="deskApp"></a> Скачаем и установим на наш компьютер GitHub Desktop. Для этого перейдите на [сайт](https://desktop.github.com/) и скачайте приложение для своей операционной системы.

![img](img/img3.png)

Установите и запустите программу. При первом запуске вам необходимо будет указать логин и пароль от [Гитхаба](https://github.com/). **Обратите внимание, что адрес электронной почты должен соответствовать почте пользователя на GitHub**

![img](img/img4.png)

## <a name="createRep"></a> Создание и клонирование репозитория

Если вы впервые используете GitHub, вам потребуется создать [репозиторий](#repo) (процесс копирования существующего репозитория будет [рассмотрен позже](#cloneRep)). Для создания репозитория на главном экране приложения [GitHub Desktop](#deskApp) выберите пункт "Create a New Repository on your hard drive".

![img](img/img5.png)

Для создания репозитория вам необходимо ввести его название, описание и выбрать папку на вашем компьютере, куда будут сохраняться файлы. Нажмите на кнопку "Create repository" и дождитесь завершения процесса создания репозитория. В итоге на вашем компьютере появится папка, которую можно использовать для разработки проекта.

![img](img/img6.png)

О том как перенести данные локального репозитория на сервер, для того чтобы все файлы отображались в браузерной версии GitHub и были доступны для просмотра и скачивания другими пользователями, мы расскажем в блоке ["Редактирование файлов"](#edit).

<a name="cloneRep"></a> В случае, если у вас уже есть репозиторий на GitHub, его можно [клонировать](#clone). На главном экране приложения выберите пункт "Clone a Repository from the Internet".

![img](img/img7.png)

В открывшемся окне выберите один из ваших репозиториев, установите путь для клонирования репозитория и нажмите на кнопку "Clone". 

![img](img/img8.png)

После этого файлы репозитория начнут скачиваться на ваш компьютер. **Это может занять некоторое время, о чем вам просигнализирует полоса загрузки**.
  
## <a name="edit"></a> Редактирование файлов
## <a name="markdown"></a> Работа с разметкой
