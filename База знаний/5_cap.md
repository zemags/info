**cap** - consistency(согласованность), availability(доступность), partion tolerance(устойчевость к разделению, от изолированных секций корректный отклик). Смысл теоремы в том, что из этих трех свойств в распределенных системах в могу быть только две

- **ca** во всех узлах данные согласованы и есть доступность, в системах с acid (PostgreSQL, MySQL, MariaDB, MS SQL Server, LDAP)
- **cp** в каждый момент целостный результат в условиях даже распада (может не выдать отклик на запрос) (Apache HBase, MongoDB, Redis, MemcasheDB)
- **ap** доступность и устойчивость к распаду, но без целостности (разные nosql) (Cassandra)

**base архитектура**
Basically Available, Soft-state, Eventually consistent — базовая доступность, неустойчивое состояние, согласованность в конечном счёте
- базовая доступность, сбой в какойто части приводит к отказу в осблуживании только незначительной части сессии
- неустойчивое состояние, жертвовать долговременным хранением сессий, фиксация только критических операций
- согласованнсть в конечном счете, вохможность противоречивости даных в некоторых случаях