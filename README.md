Logstash
=========

Роль предназначена для установки и конфигурирования сервиса Logstash  


Компоненты роли
--------------
__Роль состоит из следующих playbooks:__  

1. main.yml - установка и настройка Logstash  
2. ssl.yml - создание директории для сертификатов и добавление SSL сертификатов (playbook запускается, если переменная logstash_clients_configs_use_ssl > 0)  

Описание переменных
--------------

__logstash_version__ - версия Logstash  

__java_version__ - версия java (определяется в зависимости от версии logstash. Если версия logstash < 7.0.0, то установиться java 8 иначе установится java 11)  

__logstash_repo__ - ссылка на пакет Logstash

__logstash_config_dir__ - директория в которой хранятся файлы конфигурации logstash

__logstash_pipelines_config_dir__ - директория в которой хранятся файлы конфигурации logstash pipelines 

__logstash_elasticsearch_url__ - адрес Elasticsearch в который будут отправляться данные из logstash  

__logstash_listen_port_beats__ - порт на который слушает filebeat

__logstash_indexname__ - имя отправляемого в Elasticsearch  идекса  

__logstash_conf_templates__ - переменная используется для деплоя файла конфигурации logstash на хост  

__logstash_jvm_options__ - переменная используется для деплоя конфигурации logstash jvm опций на хост  

__logstash_pipelines_conf__ - переменная используется для деплоя конфигурации logstash pipelines на хост

__logstash_clients_configs_path__ - переменная используется для деплоя файлов  pipelines на хост (деплой будет осуществляться только если переменная use_logstash_clients_configs > 0) 

__use_logstash_clients_configs__ - использовать logstash pipelines ( 0 | 1)

__logstash_clients_configs_use_ssl__ - использовать ssl сертификаты ( 0 | 1)

__logstash_ssl_key_dir__ - директория в которой будет располагаться SSL ключ    

__logstash_ssl_certificate_dir__ - директория в которой будет располагаться SSL сертификат

__logstash_ssl_authorities_dir__ - директория в которой будет располагаться SSL authorities key 
 
__logstash_service_state__ - статус сервиса zabbix-server ( "reloaded", "restarted", "started", "stopped" ) 

__logstash_service_enabled__ - добавить ли процесс zabbix-server в автозагрузку ("true", "false")
