<p align="center">
<img width="15%" title="Reqres.in" src="media/icons/reqres_logo.png" href="https://reqres.in/" alt="Reqres.in">
</p>

# Проект по автоматизации тестовых сценариев для компании [Reqres.in](https://reqres.in/)

## 🔽 Содержание
- Используемый стек
- Реализованные проверки
- Запуск тестов из терминала
- Запуск тестов из Jenkins
- Сборка в Jenkins
- Содержание Allure-отчета
- Пример Allure-отчета
- Отчет и кейсы в Allure-TestOps
- Уведомления в Telegram с использованием бота

## 🔽 Используемый стек

<p align="center">
<img width="7%" title="IntelliJ IDEA" src="media/icons/intellij-idea-svgrepo-com.svg" alt="IntelliJ IDEA">
<img width="7%" title="Java" src="media/icons/java-svgrepo-com.svg" alt="Java">
<img width="7%" title="Allure Report" src="media/icons/Allure.svg" alt="Allure Report">
<img width="7%" title="Gradle" src="media/icons/gradle-svgrepo-com.svg" alt="Gradle">
<img width="7%" title="JUnit5" src="media/icons/Junit5.svg" alt="JUnit5">
<img width="7%" title="Allure TestOps" src="media/icons/Allure_TestOps.svg" alt="Allure TestOps">
<img width="7%" title="GitHub" src="media/icons/github-badge-svgrepo-com.svg" alt="GitHub">
<img width="7%" title="Jenkins" src="media/icons/Jenkins.svg" alt="Jenkins">
<img width="7%" title="Telegram" src="media/icons/Telegram.svg" alt="Telegram">
<img width="7%" title="RestAssured" src="media/icons/RestAssured.svg" alt="RestAssured">
</p>

Тесты в данном проекте написаны на языке <code>Java</code>, сборщик - <code>Gradle</code>. <code>JUnit 5</code> задействован в
качестве фреймворка модульного тестирования. Использован так же подход <code>RestAssured</code>.
Для удаленного запуска реализована джоба в <code>Jenkins</code> с формированием Allure-отчета и отправкой результатов
в <code>Telegram</code> при помощи бота. Тесты, описанные в коде и их результаты автоматически синхронизируются <code>Allure TestOps</code>.

## 🔽 Реализованные проверки

* Проверка успешного создания пользователя
* Проверка успешного создания пользователя без имени
* Проверка успешного создания пользователя без профессии
* Проверка успешного создания пользователя без данных
* Проверка отправки запроса с недекларированным параметром

## 🔽 Запуск автотестов

### Запуск тестов из терминала

```
gradle clean ApiTests
```

При выполнении данной команды в терминале IDE тесты запустятся локально.

### Запуск тестов из Jenkins

```
clean ApiTests
```

## <img width="4%" style="vertical-align:middle" title="Jenkins" src="media/icons/Jenkins.svg"> Сборка в [Jenkins](https://jenkins.autotests.cloud/job/C34-khabarov_ilya-Diplom-API/)

Для запуска сборки необходимо перейти в раздел <code>Buld with parameters</code>, выбрать нужные параметры запуска
автотестов и нажать кнопку <code>Build</code>.
<p align="center">
<img title="Jenkins Build" src="media/report_media/allure_job_parameters.png" alt="Jenkins Build">
</p>
После выполнения сборки, в блоке <code>Builds</code> напротив номера сборки появятся значки <code>Allure Report</code> и <code>Allure TestOps</code>, при клике на которые откроется страница со сформированным html-отчетом и тестовой документацией соответственно.

## 🔽 Содержание Allure-отчета

* Шаги теста
* Шаги проверок
* Запрос и ответ

## <img width="4%" style="vertical-align:middle" title="Allure Report" src="media/icons/Allure.svg"> Пример [Allure-отчета](https://jenkins.autotests.cloud/job/C34-khabarov_ilya-Diplom-API/3/allure/)

<p align="center">
<img title="Allure Overview" src="media/report_media/allure_tests_result_example.png" alt="Allure Overview">
</p>

## <img width="4%" style="vertical-align:middle" title="Allure TestOps" src="media/icons/Allure_TestOps.svg"> Отчет и кейсы в [Allure-TestOps](https://allure.autotests.cloud/launch/47045)
В результате запуска job'ы в Jenkins в дипломном проекте в Allure TestOps добавлется отчет и кейсы.
<p align="center">
<img title="Allure TestOps" src="media/report_media/allure_testops_results.png" alt="Allure TestOps">
</p>

## <img width="4%" style="vertical-align:middle" title="Telegram" src="media/icons/Telegram.svg"> Уведомления в Telegram с использованием бота

После завершения сборки специальный бот, созданный в <code>Telegram</code>, автоматически обрабатывает и отправляет
сообщение с отчетом о прогоне тестов.

<p align="center">
<img width="70%" title="Telegram Notifications" src="media/report_media/telegram_report.png" alt="Telegram Notifications">
</p>
