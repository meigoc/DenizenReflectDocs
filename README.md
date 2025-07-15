# DenizenReflectDocs
Документация под DenizenReflect (private addon, not public)

```java
// <--[command]
// @Name Reflect
// @Syntax reflect [new:<class> (args:<list>)|static_get:<class> field:<name>|static_set:<class> field:<name> value:<obj>|static_call:<class> method:<name> (args:<list>)|instance_get:<object> field:<name>|instance_set:<object> field:<name> value:<obj>|instance_call:<object> method:<name> (args:<list>)] (save:<id>)
// @Required 1
// @Maximum -1
// @Short Предоставляет прямой доступ к внутреннему Java-коду сервера.
// @Group DenizenReflect
//
// @Description
// Команда reflect — это мощный и опасный инструмент, позволяющий напрямую взаимодействовать с Java-классами, объектами, методами и полями.
// Это позволяет взаимодействовать с любым плагином или внутренностями сервера без необходимости в отдельном интеграционном аддоне.
//
// ПРЕДУПРЕЖДЕНИЕ: Эта команда предназначена только для опытных пользователей. Неправильное использование может легко привести к сбоям сервера, повреждению данных или уязвимостям безопасности.
// Весь доступ контролируется файлом 'plugins/DenizenReflect/config.yml'.
//
// Эта команда поддерживает ~wait. Настоятельно рекомендуется использовать её как waitable-команду (например, '- ~reflect ...') для любых потенциально медленных операций,
// чтобы предотвратить зависания сервера.
//
// --- Действия ---
//
// - `new:<class_name>`: Создаёт новый экземпляр объекта.
//   (args:<list_of_objects>): Необязательно — аргументы конструктора.
//
// - `static_get:<class_name> field:<field_name>`: Получает значение статического поля.
//
// - `static_set:<class_name> field:<field_name> value:<object>`: Устанавливает значение статического поля.
//
// - `static_call:<class_name> method:<method_name>`: Вызывает статический метод.
//   (args:<list_of_objects>): Необязательно — аргументы метода.
//
// - `instance_get:<JavaObjectTag> field:<field_name>`: Получает значение поля экземпляра объекта.
//
// - `instance_set:<JavaObjectTag> field:<field_name> value:<object>`: Устанавливает значение поля экземпляра объекта.
//
// - `instance_call:<JavaObjectTag> method:<method_name>`: Вызывает метод экземпляра объекта.
//   (args:<list_of_objects>): Необязательно - аргументы метода.
//
// ---
// Аргумент `(save:<id>)` может использоваться с любым действием, которое возвращает значение, чтобы сохранить результат для дальнейшего использования через теги.
// Сохранённое значение будет JavaObjectTag, либо преобразованным объектом Denizen, если это возможно.
//
// @Tags
// <JavaObjectTag.class_name>
// <JavaObjectTag.is_instance_of[<class_name>]>
// <JavaObjectTag.as_denizen>
// <entry[saveName].result> возвращает объект, полученный в результате вызова reflection.
//
// @Usage
// Используется для создания нового Java ArrayList и добавления элемента в него.
// - ~reflect new:java.util.ArrayList save:my_list
// - ~reflect instance_call:<entry[my_list].result> method:add args:<list_single[Hello World]>
// - narrate "List content: <entry[my_list].result.as_denizen>"
//
// @Usage
// Используется для получения статического значения из класса конфигурации другого плагина.
// - ~reflect static_get:com.some.plugin.Config field:someSetting save:setting
// - narrate "Setting value is: <entry[setting].result.as_denizen>"
//
// -->
```
