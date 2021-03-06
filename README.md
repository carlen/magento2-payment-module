# beGateway Payment Module for Magento 2 CE

[Русская версия](#Модуль-оплаты-begateway-для-magento-2-ce)

This is a Payment Module for Magento 2 Community Edition, that gives you the ability to process payments through payment service providers running on beGateway platform.

## Requirements

  * Magento 2 Community Edition 2.x (Tested up to __2.1.3__)
  * [beGateway PHP API library v2.7.x](https://github.com/beGateway/begateway-api-php) - (Integrated in Module)
  * PCI DSS certified server in order to use ```beGateway Direct```

*Note:* this module has been tested only with Magento 2 __Community Edition__, it may not work as intended with Magento 2 __Enterprise Edition__

## Installation (composer)

  * Install __Composer__ - [Composer Download Instructions](https://getcomposer.org/doc/00-intro.md)

  * Install __beGateway Gateway__

    * Install Payment Module

        ```sh
        $ composer require begateway/magento2-payment-module
        ```

    * Enable Payment Module

        ```sh
        $ php bin/magento module:enable BeGateway_BeGateway
        ```

        ```sh
        $ php bin/magento setup:upgrade
        ```
    * Deploy Magento Static Content (__Execute If needed__)

        ```sh
        $ php bin/magento setup:static-content:deploy
        ```    

## Installation (manual)

  * [Download the Payment Module archive](https://github.com/beGateway/magento2-payment-module/archive/master.zip), unpack it and upload its contents to a new folder ```<root>/app/code/BeGateway/BeGateway/``` of your Magento 2 installation

  * Install beGateway PHP API Library

    ```sh
    $ composer require begateway/begateway-api-php
    ```

  * Enable Payment Module

    ```sh
    $ php bin/magento module:enable BeGateway_BeGateway --clear-static-content
    ```

    ```sh
    $ php bin/magento setup:upgrade
    ```

  * Deploy Magento Static Content (__Execute If needed__)

    ```sh
    $ php bin/magento setup:static-content:deploy
    ```   

## Configuration

  * Login inside the __Admin Panel__ and go to ```Stores``` -> ```Configuration``` -> ```Sales``` -> ```Payment Methods```
  * If the Payment Module Panel ```beGateway``` is not visible in the list of available Payment Methods,
  go to  ```System``` -> ```Cache Management``` and clear Magento Cache by clicking on ```Flush Magento Cache```
  * Go back to ```Payment Methods``` and click the button ```Configure``` under the payment method ```beGateway Checkout``` or ```beGateway Direct``` to expand the available settings
  * Set ```Enabled``` to ```Yes```, set the correct credentials, select your prefered transaction types and additional settings and click ```Save config```

## Configure Magento over secured HTTPS Connection

This configuration is needed for ```beGateway Direct``` Method to be usable.

Steps:

  * Ensure you have installed a valid SSL Certificate on your Web Server & you have configured your Virtual Host correctly.
  * Login to Magento 2 Admin Panel
  * Navigate to ```Stores``` -> ```Configuration``` -> ```General``` -> ```Web```
  * Expand Tab ```Base URLs (Secure)``` and set ```Use Secure URLs on Storefront``` and ```Use Secure URLs in Admin``` to ```Yes```
  * Set your ```Secure Base URL``` and click ```Save Config```
  * It is recommended to add a **Rewrite Rule** from ```http``` to ```https``` or to configure a **Permanent Redirect** to ```https``` in your virtual host

## Test data

If you setup the module with default values, you can use the test data to make a test payment:

  * Shop Id ```361```
  * Shop Secret Key ```b8647b68898b084b836474ed8d61ffe117c9a01168d867f24953b776ddcb134d```
  * Checkout Domain ```checkout.begateway.com```
  * Gateway Domain ```demo-gateway.begateway.com```

### Test card details

  * Card number ```4200000000000000```
  * Card name ```John Doe```
  * Card expiry date ```01/20``` to get a success payment
  * Card expiry date ```10/20``` to get a failed payment
  * CVC ```123```

# Модуль оплаты beGateway для Magento 2 CE

Модуль оплаты для Magento 2 Community Edition, который даст вам возможность начать принимать платежи через провайдеров платежей, использующих платформу beGateway.

## Требования

  * Magento 2 Community Edition 2.x (тестировалось на версиях до __2.1.3__)
  * [beGateway PHP API библиотека v2.7.x](https://github.com/beGateway/begateway-api-php) - (поставляется с модулем)
  * PCI DSS сертифицированный сервер, чтобы принимать платежи через ```beGateway Direct```

*Примечание:* этот модуль тестировался только с Magento 2 __Community Edition__ и может работать не стабильно с Magento 2 __Enterprise Edition__

## Установка (composer)

  * Установите __Composer__ - [инструкция по установке Composer](https://getcomposer.org/doc/00-intro.md)

  * Установите __beGateway Gateway__

    * Установите модуль оплаты

        ```sh
        $ composer require begateway/magento2-payment-module
        ```

    * Включите модуль оплаты

        ```sh
        $ php bin/magento module:enable BeGateway_BeGateway
        ```

        ```sh
        $ php bin/magento setup:upgrade
        ```

    * Создайте статичный контент Magento (__выполните если необходимо__)

        ```sh
        $ php bin/magento setup:static-content:deploy
        ```    

## Установка (ручная)

  * [Скачайте архив модуля](https://github.com/beGateway/magento2-payment-module/archive/master.zip), распакуйте его и скопируйте его содержимое в новую директорию ```<root>/app/code/BeGateway/BeGateway/``` вашей Magento 2 инсталляции

  * Установите beGateway PHP API библиотеку

    ```sh
    $ composer require begateway/begateway-api-php
    ```

  * Включить модуль оплаты

    ```sh
    $ php bin/magento module:enable BeGateway_BeGateway --clear-static-content
    ```

    ```sh
    $ php bin/magento setup:upgrade
    ```

  * Создайте статичный контент Magento (__выполните если необходимо__)

    ```sh
    $ php bin/magento setup:static-content:deploy
    ```   

## Настройка

  * Войдите в личный кабинет администратора и перейдите в ```Магазины``` -> ```Конфигурация``` -> ```Продажи``` -> ```Методы оплаты```
  * Если панель модуля оплаты ```beGateway``` не видна в списке доступных методов оплаты, то перейдите в ```Система``` -> ```Управление кэшем``` и очистите Magento кэш, нажав ```Очистить кэш Magento```
  * Вернитесь назад в ```Методы оплаты``` и нажмите кнопку ```Настроить``` под способом оплаты ```beGateway Checkout``` или ```beGateway Direct```, чтобы раскрыть доступные настройки
  * Выберите ```Да``` в выпадающем списке параметра ```Включено```, задайте данные вашего магазина, выберите тип операции, доступные способы оплаты и прочие настройки. Нажмите ```Сохранить конфигурацию```, чтобы их сохранить

## Настройть Magento для работы через шифрованное соединение

Данная настройка необходима для использования способа оплаты ```beGateway Direct```.

Шаги (названия параметров могут отличаться из-за различных пакетов русификации Magento):

  * Убедитесь, что вы установили рабочий SSL сертификат на вашем веб-сервере и произвели необходимые настройки.
  * Зайдите в панель администратора Magento 2
  * Перейдите в ```Магазины``` -> ```Конфигурация``` -> ```Основное``` -> ```Веб```
  * Раскройте закладку ```Базовые URLs (безопасные)``` и установите ```Использовать защищённые URL в магазине``` и ```Использовать защищённые URL в панели администрирования``` в ```Да```
  * Задайте ваш ```Базовый защищённый URL``` и нажмите ```Сохранить конфигурацию```
  * Рекомендуем добавить **Rewrite Rule** с ```http``` на ```https``` или настроить **Permanent Redirect** на ```https``` в настройках вашего веб-сервера

## Тестовые данные

Вы можете использовать приведенные ниже тестовые данные, чтобы протестировать оплату.

  * Id магазина ```361```
  * Секретный ключ магазина ```b8647b68898b084b836474ed8d61ffe117c9a01168d867f24953b776ddcb134d```
  * Домен страницы оплаты ```checkout.begateway.com```
  * Домен платежного шлюза ```demo-gateway.begateway.com```

### Тестовая карта

  * Номер карты ```4200000000000000```
  * Имя на карте ```John Doe```
  * Срок действия для успешной оплаты ```01/20```
  * Срок действия для неуспешной оплаты ```10/20```
  * CVC ```123```
