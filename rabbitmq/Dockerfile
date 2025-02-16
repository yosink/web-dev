FROM rabbitmq:3.10-management

COPY ./rabbitmq_delayed_message_exchange-3.10.2.ez /plugins/rabbitmq_delayed_message_exchange-3.10.2.ez

RUN rabbitmq-plugins enable --offline rabbitmq_delayed_message_exchange