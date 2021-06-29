# Android Interview Questions And Answers

  ![Android Interview Questions Coderefer Thumbnail](/assets/android-interview-questions-cr-thumbnail.jpg)

### Curated List of Real-time Android Interview Questions. Found Any Errors / Want to help fellow developers? - Create a pull request in  [Github](https://github.com/vamsitallapudi/Android-Interview-Questions-And-Answers).

Quick Jump to Topics:
 * [Core Android](#core-android)
 * [Java Interview Questions](/java/README.md)
 * [Kotlin Interview Questions](/kotlin/README.md)
 * [Dagger](#dagger-2-related-questions)
 * [RxJava](#rxjava-related-questions)
 * [Kotlin](#kotlin)

### Core Android

-   **What are SOLID Principles? How they are applicable in Android?**<br/>
    A) SOLID объединяет в себе все лучшие практики разработки программного обеспечения 
    на протяжении многих лет для создания приложений хорошего качества. 
    Понимание принципов SOLID поможет нам писать чистый и элегантный код. 
    Это помогает нам писать код с помощью SOC (Separation of Concerns - разделение проблем). 
    SOLID Principles - это аббревиатура от: 
    1. S stands for Single Responsibility Principle(SRP) - У каждого элемента только одна зона ответственности 
    2. O stands for Open Closed Principle - Программные объекты, такие как классы, функции, модули, должны быть открыты для расширения, но закрыты для модификации.
    3. L stands for Liskov Substitution Principle - Производный класс должен использоваться через интерфейс базового класса, при этом пользователю не нужно знать разницу. 
    4. I stands for Interface Segregation - Ни один клиент не должен зависеть от методов, которые он не использует. 
    5. D stands for Dependency Inversion - 
       1. Модули высокого уровня не должны напрямую зависеть от модулей низкого уровня. Вместо этого оба должны зависеть от абстракций.
       2. Абстракции не должны зависеть от деталей. Детали должны зависеть от абстракций.

    [Learn More about SOLID principles with Android Examples Here.](https://www.coderefer.com/blog/solid-principles-in-android-with-kotlin-examples/)

-   **Android Architecture**<br/>
    A) <br/>
    ![Android Architecture Image](/assets/android-architecture.png)

-   **What are Android Components?**<br/>
    A) 1) Activities,
    2) Intent and broadcast receivers,
    3) Services,
    4) Content Providers,
    5) Widgets and Notifications

-   **What is an Application class?**<br/>
    A) Класс приложения - это базовый класс в вашем приложении, 
    который запускается до того, как будут вызваны все другие классы, 
    такие как Activities или services. Здесь вы можете поддерживать глобальное состояние 
    вашего приложения. Хотя расширение класса Application НЕ является обязательным, 
    вы можете сделать это, предоставив собственную реализацию, создав подкласс и 
    указав полное имя этого подкласса в качестве атрибута "android:name" 
    в вашем файле AndroidManifest.xml <application> тег.
    
-   **What is a Context? What are different types of Contexts?**<br/>
    A) Как следует из названия, это контекст текущего приложения или объекта. 
    Контекст похож на дескриптор среды, в которой в настоящее время работает ваше 
    приложение.
     В основном мы используем два типа контекста. 
    Контекст Application, область действия которого распространяется на все 
    приложение и контекст Activity, область действия которого зависит от 
    жизненного цикла Activity.
-   **What is an Activity?**<br/>
    A) Activity предоставляет окно, в котором приложение рисует свой 
    пользовательский интерфейс. Это окно обычно заполняет экран, 
    но может быть меньше экрана и располагаться поверх других окон. 
    Как правило, одно Activity реализует один экран в приложении. 
    Например, одно из действий приложения может реализовывать экран настроек, 
    в то время как другое действие реализует экран выбора фотографии.
-   **Activity Lifecycle**<br/>
    A)<br/>
    ![Activity Lifecycle Image](/assets/activity_lifecycle.png)

-   **Fragment Lifecycle**<br/>
    A)<br/>
    ![Fragment Lifecycle Image](/assets/fragment_lifecycle.png)

-   **Service Lifecycle**<br/>
    A)<br/>
    ![Fragment Lifecycle Image](/assets/service_lifecycle.png)

-   **What is the correlation between activity and fragment life cycle?**<br/>
-   A) <br/>
    Here is how Activity's and Fragment's lifecyle are called together:
    ![Activity Fragment Lifecycle](/assets/activity-fragment-lifecycles.png)

-   **Is there any scenario where onDestoy() will be called without calling onPause() and onStop()?**<br/>
    A) Если мы вызовем метод finish () внутри onCreate () нашей Activity, то onDestroy () будет вызываться напрямую.
-   **How do we save and restore an activity's state during screen screen rotation?**<br/>
    A) Мы можем использовать onSaveInstanceState (bundle: Bundle) для сохранения состояния активности внутри bundle. 
    Затем мы можем использовать onRestoreInstanceState (bundle) для восстановления состояния активности.
-   **What is a Loader in Android?**<br/>
    A) Примечание. (Загрузчик устарел. Мы должны использовать комбинацию ViewModels и LiveData вместо использования загрузчиков). Загрузчик используется для получения данных от поставщика содержимого и кэширования результатов при изменении конфигурации, чтобы избежать дублирования запросов. Некоторые реализации загрузчиков, такие как CursorLoader, могут реализовывать наблюдателя для отслеживания любых изменений данных и затем запускать перезагрузку.
-   **What is an Intent Filter?**<br/>
    A) Intent Filter - очень мощная функция платформы Android. 
    Они предоставляют возможность запускать действие, основанное не только на 
    явном запросе, но и на неявном. Например, явный запрос может указывать системе: 
    «Запустить действие отправки электронной почты в приложении Gmail». 
    В отличие от этого неявный запрос сообщает системе: 
    «Запустить экран отправки электронной почты в любом действии, которое может 
    выполнить эту работу». Когда пользовательский интерфейс системы спрашивает 
    пользователя, какое приложение использовать для выполнения задачи, 
    это срабатывает Intent Filter. Вот пример того, как объявить Intent Filter в 
    AndroidManifest:    
    ```xml
    <activity android:name=".ExampleActivity" android:icon="@drawable/app_icon">
      <intent-filter>
          <action android:name="android.intent.action.SEND" />
          <category android:name="android.intent.category.DEFAULT" />
          <data android:mimeType="text/plain" />
      </intent-filter>
    </activity>
    ```


-   **What is an Intent?**<br/>
    A) Это своего рода сообщение или информация, которые передаются компонентам. Он используется для запуска активности, отображения веб-страницы, отправки SMS, отправки электронной почты и т. Д.
  
-   **What are the different types of Intents?**<br/>
    A) There are two types of intents:  
    * Явные намерения указывают, какое приложение будет удовлетворять намерение, 
    путем предоставления либо имени пакета целевого приложения, либо полного имени 
    класса компонента. Обычно вы будете использовать явное намерение для запуска 
    компонента в собственном приложении, потому что вам известно имя класса действия 
    или службы, которую вы хотите запустить. Например, вы можете запустить новое 
    действие в своем приложении в ответ на действие пользователя или запустить службу 
    для загрузки файла в фоновом режиме.  
    * Неявные намерения не именуют конкретный компонент, а вместо этого объявляют 
    общее действие, которое необходимо выполнить, что позволяет компоненту из другого 
    приложения обрабатывать его. Например, если вы хотите показать пользователю 
    местоположение на карте, вы можете использовать неявное намерение, чтобы запросить 
    у другого совместимого приложения указанное местоположение на карте.
    
    **What is AAPT?**<br/>
    A) AAPT2 (Android Asset Packaging Tool) - это инструмент сборки, 
    который Android Studio и Android Gradle Plugin используют для компиляции и 
    упаковки ресурсов вашего приложения. AAPT2 анализирует, индексирует и 
    компилирует ресурсы в двоичный формат, оптимизированный для платформы Android.
-   
-   **What is HandlerThread?**<br/>
    A) HandlerThread - это удобный класс для запуска потока с Looper.

-   **What is a Looper?**<br/>
    A) Looper - это класс, используемый для циклического прохождения очереди сообщений, прикрепленной к потоку. Любой поток состоит только из одного лупера.
    Вы можете получить доступ к очереди сообщений текущего потока, используя **Looper.myQueue()**.
   По умолчанию поток останавливается после завершения выполнения. Но, например, если 
    мы возьмем основной поток Android, он не должен останавливаться при выполнении.
   Обычно поток не может быть повторно использован после завершения его работы. 
    Но поток с Looper остается активным до тех пор, пока вы не вызовете метод quit, 
    поэтому вам не нужно создавать новый экземпляр каждый раз, когда вы хотите 
    запустить задание в фоновом режиме.
   Скорее, он должен проходить через исполняемые файлы (сообщения), которые ему 
    назначены, чтобы работать должным образом. Для получения дополнительной 
    информации обратитесь к этой [link](https://stackoverflow.com/a/34522758/3424919).
-   **What is a Message Queue?**<br/>
    A) MessageQueue - это очередь со списком сообщений, которые необходимо обработать. Android поддерживает MessageQueue в основном потоке.
    [More Info](https://medium.com/@ankit.sinhal/messagequeue-and-looper-in-android-3a18c7fc9181)

-   **What is a Message ?**<br/>
    A) Сообщение содержит описание и произвольный объект данных, который может быть отправлен обработчику. В основном он используется для обработки / отправки некоторых данных по потокам.
-   **What is a Service?**<br/>
    A) Service - это компонент, у которого нет пользовательского интерфейса и который может выполнять длительные операции, такие как загрузка файлов, воспроизведение музыки и т. Д., Которые могут выполняться даже при выходе из приложения. По умолчанию служба работает в основном потоке. Это может вызвать ошибки ANR. Чтобы избежать этого, мы можем запустить службу, создав новый фоновый поток или используя IntentService, который может работать в фоновом режиме. [Подробнее.](Https://developer.android.com/guide/components/services)
  IntendServiсe запускается один раз (в отдельном потоке), выполняет работу и останавливается. Если пришел новый интенд, пока первый работает, то он положится в очередь
  
-   **How to Stop a Service?**<br/>
    A) Чтобы остановить службу от активности, мы можем вызвать метод stopService (Intent intent). Чтобы остановить службу от самой себя, мы можем вызвать метод stopSelf ().
-   **What are different types of services?**<br/>
    A) These are the three different types of services:

    **Foreground Service:**
    Служба переднего плана выполняет некоторую операцию, заметную для пользователя. Например, звуковое приложение будет использовать службу переднего плана для воспроизведения звуковой дорожки. Службы переднего плана должны отображать уведомление. Службы переднего плана продолжают работать, даже если пользователь не взаимодействует с приложением. <br/>
    **Background Service:**
    Фоновая служба выполняет операцию, которая напрямую не замечается пользователем. Например, если приложение использует службу для сжатия своего хранилища, обычно это фоновая служба. Однако существуют ограничения на использование фоновых служб из Android API 26 и выше. Мы можем использовать WorkManager, чтобы отложить выполнение этих фоновых задач. <br/>
    **Bound Service:**
    Служба привязывается, когда компонент приложения привязывается к ней, вызывая bindService (). Связанная служба предлагает интерфейс клиент-сервер, который позволяет компонентам взаимодействовать со службой, отправлять запросы, получать результаты и даже делать это между процессами с межпроцессным взаимодействием (IPC). Связанная служба работает только до тех пор, как другой компонент приложения привязан к нему. Несколько компонентов могут быть привязаны к службе одновременно, но когда все они отключаются, служба уничтожается системой.
    [Read More](https://developer.android.com/guide/components/services#Types-of-services)

-   **Bound Service vs UnBounded service?**<br/>
    A) Связанная служба запускается с помощью метода bindService (). Как упоминалось выше, система уничтожает связанную службу, когда к ней не обращается ни один компонент приложения.  
       UnBounded служба (запущенная служба) запускается с помощью метода startService (). После запуска он будет работать бесконечно, даже если компонент приложения, запустивший его, будет уничтожен.
    
-   **When does a Bound Service stops?**<br/>
    A) Связанная служба будет автоматически остановлена системой, когда все привязанные к ней компоненты приложения перестанут слушать.  <br/><br/>
    
    **What is the difference between START_NOT_STICKY, START_STICKY AND START_REDELIVER_INTENT?**<br/>
    A) **START_NOT_STICKY:**<br/>
    Если система убивает службу после onStartCommand (), то она не воссоздают службу, если нет ожидающего намерения. Это самый безопасный вариант, позволяющий избежать запуска вашей службы, когда в ней нет необходимости, и когда ваше приложение может просто перезапустить любые незавершенные задания. <br/>
    **START_STICKY:**<br/>
    Если система завершает работу службы после возврата из onStartCommand (), то она воссоздает службу и вызывает onStartCommand (), но повторно не отправляет последний интенд. Вместо этого система вызывает onStartCommand () с нулевым интендом, если нет ожидающих интендов запустить службу. В этом случае эти намерения будут доставлены. Это подходит для медиаплееров (или аналогичных служб), которые не выполняют команды, но работают бесконечно и ждут задания. <br/>
    **START_REDELIVER_INTENT:**<br/>
    Если система завершает работу службы после возврата из onStartCommand (), то она воссоздает службу и вызывает onStartCommand () с последним интендом, которое было доставлено сервису. Любые ожидающие интенды доставляются по очереди. Это подходит для служб, которые активно выполняют работу, которая должна быть немедленно возобновлена, например, загрузка файла. 
    

-   **What is Pending Intent?**<br/>
    A)Ожидающее намерение - это токен, который вы даете внешнему приложению 
    (например, NotificationManager, AlarmManager, Home Screen AppWidgetManager или 
    другим сторонним приложениям), который позволяет стороннему приложению 
    использовать разрешения вашего приложения для выполнения заранее определенного 
    фрагмента кода. Он определяет задачу, которую необходимо выполнить в будущем.
-   **What is an Intent Service?**<br/>
    A) IntentService - это подкласс службы, который может выполнять задачи с использованием рабочего потока, в отличие от сервисов, которые блокирует основной поток.
-   **What is the method that differentiates it to make Service run in background?**<br/>
    A) onHandleIntent () - это метод, который помогает IntentService запускать определенный блок кода, объявленный внутри него, в рабочем / фоновом потоке.
-   **How to Stop an IntentService?**<br/>
    A) IntentService автоматически останавливается после выполнения своей работы. Нам не нужно явно вызывать какие-либо методы для остановки IntentService, в отличие от Service, для которого требуется stopSelf () или StopService(intend: Intend).
-   **When Intent Service is Useful?**<br/>
    A) IntentService может использоваться в длинных задачах, обычно без связи с основным потоком. Если требуется связь, можно использовать обработчик основного потока или широковещательные намерения. Другой случай использования - когда необходимы обратные вызовы (задачи, запускаемые намерением).
-   **Advantage of Retrofit over Volley?**<br/>
    A) Retrofit типобезопасный. Безопасность типов означает, что компилятор будет проверять запросы и типы переменных объекта ответа во время компиляции и выдает ошибку, если вы пытаетесь присвоить переменной неправильный тип.
-   **Advantage of Volley over Retrofit?**<br/>
    A) Android Volley имеет очень продуманный и гибкий механизм кеширования. Когда запрос сделан через Volley, сначала кеш проверяется на Response. Если он найден, он извлекается и анализируется, в противном случае он обращается к сети для извлечения данных. По умолчанию дооснащение не поддерживает кеширование.


-   **What are different launch modes available in Android?**<br/>
    A) Существует четыре режима запуска Activity в Android, а именно:
    1) <b>standard</b> : Создает новый экземпляр операции в задаче, из которой она запускается каждый раз. Если не объявлен, это режим по умолчанию.
     <br/> Например: если у нас есть стек действий A-> B-> C, если мы снова запустим действие C в стандартном режиме, стек действий теперь будет A-> B-> C-> C. Мы видим, что в стеке действий присутствуют два экземпляра C.
       
    1) <b>singleTop</b> : То же, что и стандарт, за исключением того, что если действие находится наверху стека, будет использоваться тот же экземпляр. Теперь существующее действие вверху получит намерение через вызов своего метода onNewIntent ().
      <br/> Например: если у нас есть стек активности A-> B-> C, если мы снова запустим Activity C в режиме singleTop, стек активности останется A-> B-> C. Однако, если мы запустим B, то B будет добавлен как новый экземпляр в стек (A-> B-> C-> B).
       
    2) <b>singleTask</b> : Будет создана новая задача, и действие будет создаваться в корне этой новой задачи всякий раз, когда мы используем режим запуска как singleTask. Однако, если уже существует отдельная задача с таким же экземпляром, система вызовет метод этого действия onNewIntent () для маршрутизации намерения. Одновременно может существовать только один экземпляр активности.
     <br/> Например: если наш стек действий - A-> B-> C и если мы запустим D с помощью singleTask, это будет A-> B-> C -> [D]. Здесь фигурные скобки представляют стек в отдельной задаче. Если мы вызываем E в стандартном режиме, то это будет A-> B-> C -> [D-> E]. <br/>
     Если у нас есть A-> B-> C и если мы снова вызовем B, используя режим запуска singleTask, стек теперь будет A -> [B] с B в отдельной задаче. Действие C будет уничтожено.
       
    1) <b>singleInstance</b> : То же, что и отдельная задача, за исключением того, что в задаче создается новое действие, и никакие другие действия не могут быть запущены в этой задаче. Эта задача навсегда будет содержать только эту деятельность. Если мы используем стандартные или singleTop для запуска других действий, они запускаются в другие задачи.
     <br/> Например: если стек Activity - A-> B и теперь мы запустили C, используя режим запуска singleInstance, новый стек будет A-> B -> [C]. Теперь, если мы вызовем новую активность D из C, она будет запущена в отдельную задачу. Теперь новый стек будет A-> B -> [C] -> [D]. Теперь, если мы запустим E из действия B, тогда новый стек будет A-> B-> E [C] -> [D]. Если мы вызовем C снова, будет вызван onNewIntent () of C, и новый стек будет A-> B-> E -> [C] [D].
       
    You can read more about them [here](https://developer.android.com/guide/components/activities/tasks-and-back-stack#ManifestForTasks).

-   **How do you declare the launch mode in your application?**<br/>
    A) через манифест в теге активности. Например, -> android: launchMode = "singleTask"

-   **How to handle crashing of AsyncTask during screen rotation?**<br/>
    A)Один из способов - отменить AsyncTask, используя метод cancel () для его экземпляра. Он вызовет метод onCancelled () AsyncTask, где мы сможем выполнить некоторые действия по очистке, такие как скрытие индикатора выполнения и т. Д.
     Лучший способ справиться со сбоем AsyncTask - создать RetainFragment, то есть фрагмент без пользовательского интерфейса, как показано в приведенной ниже сути: https://gist.github.com/vamsitallapudi/26030c15829d7be8118e42b1fcd0fa42
     Мы также можем избежать этого сбоя, используя RxJava вместо AsyncTask, поскольку мы будем подписываться и отказываться от подписки в методах onResume () и onPause () соответственно. В качестве альтернативы мы можем использовать компонент, учитывающий жизненный цикл активности - LiveData.
-  **What is a RetainFragment?**<br/>
    Как правило, фрагменты уничтожаются и воссоздаются вместе со своими родительскими Activity всякий раз, когда происходит изменение конфигурации. Вызов setRetainInstance (true) позволяет нам обойти этот цикл уничтожения и воссоздания, уведомляя систему о необходимости сохранения текущего экземпляра фрагмента при воссоздании действия.
-  **Difference between serializable and parcelable? Why android introduced Parcelable?**<br/>
    A) Serializable использует отражение, а для parcelable разработчики из команды Android написали собственный код, который выполняет ручную сортировку (преобразование данных в поток байтов) и демаршалинг (преобразование потока байтов обратно в исходные данные). Обычно Parcelable считается быстрее, чем Serializable.
-  **What is Reflection?**<br/>
    A) Отражение - это API, который используется для проверки или изменения поведения методов, классов и интерфейсов во время выполнения. Необходимые классы для отражения присутствуют в пакете java.lang.reflect.
-  **How to reduce your app size?**<br/>
    A)
     1. установка minifyEnabled в значение true
     2. установка shrinkResources в true
     3. использование пакета вместо apk в консоли разработчика
     4. преобразование изображений в векторные чертежи.

-   **What is the advantage of using Retrofit over AsyncTask?**<br/>
    A) Retrofit сокращает количество стандартного кода за счет внутреннего использования библиотеки GSON, которая помогает автоматически анализировать файл json.
     Retrofit - это типобезопасная библиотека. Это означает - он проверяет, не присвоен ли неправильный тип данных переменным во время самой компиляции.    More use-cases at: https://stackoverflow.com/a/16903205/3424919

-   **How to handle multiple network calls using Retrofit?**<br/>
      A) В Retrofit мы можем вызывать операции асинхронно, используя метод enqueue (), а для синхронного вызова операций мы можем использовать метод execute (). Кроме того, мы можем использовать оператор zip () из RxJava для выполнения нескольких сетевых вызовов с использованием библиотеки Retrofit.
-   **What is the role of Presenter in MVP?**<br/>
    A) Presenter должен действовать как посредник между view и моделью. 
    Он извлекает данные из модели и возвращает их в формате view. Но в отличие от 
    типичного MVC, он также решает, что происходит, когда вы взаимодействуете с view.
-   **What is the advantage of MVVM over MVP?**<br/>
    A) В MVP Presenter отвечает за обновления данных просмотра, а также операции с данными, где, как и в MVVM, ViewModel не содержит никаких ссылок на View. Выбор изменений из ViewModel является обязанностью View. Это помогает в написании более удобных в обслуживании тестовых случаев, поскольку ViewModel не зависит от View.
-    **When to use AsyncTask and when to use services?**<br/>
    A) services полезны, когда вы хотите запускать код, даже когда Activity вашего 
     приложения не открыта. AsyncTask - это вспомогательный класс, используемый для 
     запуска некоторого кода в отдельном потоке и публикации результатов в основном 
     потоке. Обычно AsyncTask используется для небольших операций, а services - для 
     длительных операций.
-    **When to use a service and when to use a thread?**<br/>
    A) Мы будем использовать поток, когда хотим выполнять фоновые операции, когда 
     приложение работает на переднем плане. Мы будем использовать service, даже 
     если приложение не запущено.
-   **What is a Handler?**<br/>
    A) Обработчик позволяет отправлять и обрабатывать объекты Message и Runnable, 
    связанные с MessageQueue потока. Каждый экземпляр Handler связан с одним потоком и 
    очередью сообщений этого потока. Когда вы создаете новый обработчик, он 
    привязывается к потоку / очереди сообщений потока, который его создает - 
    с этого момента он будет доставлять сообщения и исполняемые файлы в эту очередь 
    сообщений и выполнять их по мере выхода из очереди сообщений. Обычно мы будем 
    использовать класс обработчика, когда хотим повторять задачу каждые несколько секунд.
-   **How to save password safely in Android?**<br/>
    A) Using Android Keystore<br/>
    <https://medium.com/@josiassena/using-the-android-keystore-system-to-store-sensitive-information-3a56175a454b>

-  **What is Alarm Manager?**<br/>
    A) AlarmManager - это класс, который помогает планировать запуск кода вашего 
   приложения в определенный момент времени или через определенные промежутки времени 
   в будущем. Когда срабатывает alarm, intend, который был зарегистрирован 
   для него, транслируется системой, автоматически запуская целевое приложение, 
   если оно еще не запущено. Зарегистрированные сигналы сохраняются, 
   пока устройство находится в спящем режиме (и может дополнительно разбудить 
   устройство, если они сработают в течение этого времени), но будут сброшены, 
   если оно будет выключено и перезагружено.
-   **How can I get continuous location updates in android like in Google Maps?**<br/>
-   **Как я могу получать постоянные обновления местоположения в Android, как в Google Maps?**<br/>
    A) Мы можем использовать провайдер местоположения Fused в Android, чтобы установить в нем наш интервал.
    https://stackoverflow.com/a/41500910/3424919


### Android Security Related
-   **How do you know if the device is rooted?**<br/>
    A) Мы можем проверить, установлен ли на устройстве apk superUser или он содержит файл su или папку xbin. В качестве альтернативы вы можете использовать библиотеку RootBeer, доступную в GitHub.    <br/>
    For code part, click [Here](https://stackoverflow.com/a/35628977/3424919).
-   **What is Symmetric Encryption?**<br/>
    A) Симметричное шифрование занимается созданием парольной фразы и шифрованием файла с ее помощью. Затем серверу необходимо отправить ключ клиенту, чтобы клиент мог расшифровать. Здесь проблема заключается в отправке этого ключа для расшифровки файла. Если хакеры могут получить доступ к этому ключу, они могут неправильно использовать данные.
-   **What is Asymmetric Encryption?**<br/>
    A) Используя такие алгоритмы, как RSA, сервер генерирует 2 ключа - открытый ключ и закрытый ключ. Затем сервер выдает клиентам открытый ключ. Затем клиент шифрует конфиденциальные данные этим открытым ключом и отправляет их обратно на сервер. Теперь, когда закрытый ключ есть только у сервера, только он может расшифровать данные. Это наиболее эффективный способ отправки данных между клиентом и сервером.
     <br/>
     Примером этого асимметричного шифрования являются HTTPS с использованием сертификата SSL, биткойн и т. Д.
    For more info, refer to this [video](https://youtu.be/AQDCe585Lnc)


### Android Battery Related
-   **How do you reduce battery consumption?**<br/>
    A) 
     1. Никогда не опрашивайте сервер на предмет обновлений.
     2. Синхронизируйте только при необходимости. В идеале выполняйте синхронизацию, когда телефон подключен к сети Wi-Fi и подключен к сети.
     3. Отложите свою работу с помощью WorkManager.
     4. Сожмите свои данные.
     5. Отложите немедленные запросы до тех пор, пока телефон не будет подключен или не будет включен Wi-Fi. Радио Wi-Fi потребляет значительно меньше батареи, чем мобильное радио.

-   **How do you improve battery while fetching location for an app?**<br/>
    A) 
     1. Изменив точность -> мы можем использовать setPriority () на PRIORITY_LOW_POWER.
     2. Изменив частоту получения местоположения -> мы можем использовать setInterval (), чтобы указать временной интервал.
     3. Увеличивая задержку -> После нашего вызова мы можем ждать дольше - мы можем использовать setMaxWaitTime () для установки большого тайм-аута.   


### Dagger 2 Related Questions:

-   **What is Dependency Injection Pattern?**<br/>
    A) Шаблон внедрения зависимостей - это то место, где, если нашему объекту требуется другой объект, он будет передан нашему объекту вместо того, чтобы нам нужно было создавать этот объект. Этот другой объект называется зависимостью.
-   **What is Service Locator Pattern?**<br/>
    A) Шаблон Service Locator использует центральный реестр, известный как Service Locator, который по запросу предоставляет объекты для нашего класса. Этот шаблон подвергается серьезной критике за то, что он является анти-шаблоном.
-   **What is Anti-Pattern?**<br/>
    A) Антишаблон - это определенные шаблоны в разработке программного обеспечения, которые считаются плохой практикой программирования. <br/>
    For more, click [Here](https://stackoverflow.com/a/980616/3424919).

-   **What is the use-case of @BindsInstance Annotation?**<br/>
    A) @BindsInstance используется для привязки доступных данных во время создания 
    Компонента. Например, хотя мне нужно было построить dagger граф и имя пользователя 
    уже доступно мне, я могу привязать это имя пользователя к этому dagger графу 
    зависимостей следующим образом:    
    ```java
        @Component.Builder
        interface Builder {
            @BindsInstance Builder userName(@UserName String userName);
            AppComponent build();
        }
    ```


-   **What is the use-case of @Module Annotation?**<br/>
    A) @Module - это аннотация, используемая в классе для того, чтобы Dagger заглядывал внутрь него и предоставлял зависимости. Мы можем объявлять методы внутри класса модуля, которые заключены в аннотацию @Provides.
-   **What is the use-case of @Provides Annotation?**<br/>
    A) Аннотация @Provides используется для метода в классе Module и может возвращать / предоставлять объект Dependency.
-   **What is the use-case of @Component Annotation?**<br/>
    A) @Component используется в интерфейсе или абстрактном классе. Dagger использует этот интерфейс для создания класса реализации с полностью сформированной реализацией с внедрением зависимостей, используя модули, объявленные вместе с ним. Этому сгенерированному классу будет предшествовать Dagger. Например, если я создаю интерфейс с именем ProgramComponent с аннотацией @Component, Dagger сгенерирует класс с именем DaggerProgramComponent, реализующий интерфейс ProgramComponent.
-   **What is the use-case of @Scope Annotation?**<br/>
    A) @Scope - это аннотация, используемая в интерфейсе для создания new Custom Scope. Объявление Scope помогает сохранить единственный экземпляр класса, пока существует его область видимости. Например, в Android мы можем использовать @ApplicationScope, чтобы объект существовал, пока приложение работает, или @ActivityScope, чтобы объект был доступен до тех пор, пока действие не будет уничтожено.
-   **What is the use of Qualifier in Dagger?**<br/>
    A) Мы часто оказываемся в ситуации, когда нам потребуется несколько объектов с разными значениями экземпляра. Например, нам нужно объявить Студента («Вамси») и Студента («Кришна»). В таком случае мы можем использовать квалификатор, чтобы сообщить Dagger, что нам нужно несколько экземпляров одного и того же класса. Реализация Qualifier по умолчанию использует аннотацию @Named, например, @Named ("student_vamsi") и @Named ("student_krishna").
     Если мы хотим создать настраиваемый квалификатор, мы будем использовать @Qualifier для объявления интерфейса настраиваемого квалификатора.
-   **What is the use-case of @Inject Annotation in Dagger?**<br/>
    A) Аннотация @Inject используется для запроса Dagger для предоставления соответствующего объекта. Мы используем @Inject в конструкторе, полях (в основном там, где конструктор недоступен, например, действиях, фрагментах и т. Д.) И методах.
### RxJava Related Questions:

More additional info to get started with RxJava is available at:
[Getting Started with RxJava2](https://www.coderefer.com/rxandroid-tutorial-getting-started/)

-   **What is an Observable in RXJava2?**<br/>
    A) Observable просто передает данные тем, кто на него подписался. Вся эмиссия осуществляется асинхронно подписчикам. Простой Observable можно создать следующим образом:
    ```java
    // RxAndroid Tutorial - Adding Observable
    Observable<String> stringObservable = Observable.just("Hello Reactive Programming!");
    ```
-   **What is an Observer in RXJava2?**<br/>
    A) Observer потребляет данные, передаваемые Observable. Для этого Observer должен подписаться на Observable. Пример показывает, как создать Observable в RxJava2.    
    ```java
    // RxAndroid Tutorial - Adding observer
    Observer<String> stringObserver = new Observer<String>() {
            @Override
            public void onSubscribe(Disposable d) {
            }

            @Override
            public void onNext(String s) {
                Toast.makeText(MainActivity.this, s, Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onError(Throwable e) {
            }

            @Override
            public void onComplete() {
            }
        };
    ```

-   **How to Subscribe / Unsubscribe in RXJava?**<br/>
    A) Мы можем заставить Observer подписаться на Observable следующим образом:
    ```java
    // RxAndroid tutorial - observer subscribing to observable
    stringObservable.subscribe(stringObserver);
    ```

-   **What are the different types of Observables in RxJava?**<br/>
    A)1) single
    2) Maybe
    3) Completable
    4) Observable
    5) Flowable

-   **What is a Single in RxJava?**<br/>
    A) Single в RxJava - это Observable, который выдает только один элемент, если завершен, или возвращает ошибку.
-   **What is Maybe in RxJava?** <br/>
    A) A Maybe в RxJava используется, когда Observable необходимо выдать значение, отсутствие значения или ошибку.
-   **What is Completable in RxJava?** <br/>
    A) Completable в RxJava - это Observable, который просто выполняет задачу и ничего не генерирует, если завершено. Он возвращает ошибку, если что-то не получается.
     Это похоже на реактивную концепцию runnable.
-   **What is Back Pressure in RxJava?**<br/>
    A) Обратное давление - это состояние, при котором ваш наблюдаемый (publisher) создает больше событий, чем может обработать ваш подписчик.
-   **What is Flowable in RxJava?** <br/>
    A) Flowable в RxJava используется, когда Observable испускает больше данных, чем Observer может принять. Другими словами, Flowable может справиться с противодавлением, а Observable - нет.
-   **What is a Cold Observable?**<br/>
    A) Холодный Observable - это Observable, который не испускает элементы, пока подписчик не подпишется. Если у нас более одного подписчика, Cold Observable будет отправлять каждую последовательность элементов всем подписчикам один за другим.
-   **What is a Hot Observable?**<br/>
    A) Горячий наблюдаемый - это Наблюдатель, который будет испускать предметы.
-   **Hot Observables vs Cold Observables**<br/>



### Kotlin
      
- **infix функции**      
      <img src="https://user-images.githubusercontent.com/56442323/123546026-af6fb580-d763-11eb-80b6-db3c32589c5d.png" alt="drawing" width="400"/>  
      Используется для пар ``“sdk” to “df”``
      
- **val** - не меняется именно ссылка

- **Nullable**       
      elvis: ``val l = b?.length ?: -1`` - присвой, если не null       
      !! operator: the not-null assertion operator - конвертирует в not null или бросает exeption       

- **for loop**  
      ``for (index in indexes)        
        for (index in 1...3)``

- **swith -> when**        
      в case можно указать диапазон   
      или тип
      
- **filter** и прочее для колекций    
      ``list.filter{ it.length > 3 }.groupBy{ it.lenght }`` - это лямбда
      
- **Collections**   
      ``val ar: Array = arrayOfInt(1, 2, 3)``
      
- **Classes**   
      init, constructor
      
- **open** - модификатор, чтобы можно было переопределять класс/метод. Классы по умолчанию public final
      
- **data class**   
      Класс, в котором данные из конструктора сразу присваиваются всем полям + генерируются гетер/сетер, функции equals, hashcode, copy, toString
      
- **sealed class** - прокаченный enum, чтобы задать некую иерархию наследования, делать по статусам. Под капотом - абстрактный класс джавы      
      <img src="https://user-images.githubusercontent.com/56442323/123546901-3ffbc500-d767-11eb-9dde-1435d709d55d.png" alt="drawing" width="400"/>     
      от него наследуются какие-то другие классы и потом через when какой-то создается
      
- **модификаторы доступа**      
      <img src="https://user-images.githubusercontent.com/56442323/123547741-a0d8cc80-d76a-11eb-82f2-d6d351544918.png" alt="drawing" width="400"/>        
      
- **extentions** - в любом классе можно переопределить любой публичный метод, по капотом static метод     
      <img src="https://user-images.githubusercontent.com/56442323/123547854-15ac0680-d76b-11eb-909a-629c66ff93f1.png" alt="drawing" width="400"/>        

- **лямбды**      
      <img src="https://user-images.githubusercontent.com/56442323/123547994-ad115980-d76b-11eb-99e5-8810200d1785.png" alt="drawing" width="400"/>        
      return -> invoke    
      return@ -> return из внешней функции
      доступ к внешним переменным  
      
- **сравнения**     
      == - как equals     
      === - сравнение по значению в ссылке    
      
- **Доп классы**     
      Unit - аналог void    
      Nothing - его нельзя создать, используется для функций, которые ничего не вернут, например, кидают exeption или уходят в бесконечный цикл    
      Any - аналог Object в java, обозначает любой объект     

      
