GetDepartment
=============

.. http:get:: /admin/GetDepartment

    :query boxId: идентификатор ящика
    :query departmentId: идентификатор подразделения

    :reqheader Authorization: необходимые данные для :doc:`авторизации <../../Authorization>`

    :statuscode 200: операция успешно завершена
    :statuscode 400: данные в запросе имеют неверный формат или отсутствуют обязательные параметры
    :statuscode 401: в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные
    :statuscode 402: закончилась подписка на API
    :statuscode 403: доступ к ящику с предоставленным авторизационным токеном запрещен или запрос сделан не от имени администратора
    :statuscode 404: в указанном ящике нет подразделения с указанным идентификатором
    :statuscode 405: используется неподходящий HTTP-метод
    :statuscode 500: при обработке запроса возникла непредвиденная ошибка

**Тело ответа:** :doc:`../../proto/Departments/Department`

Возвращает информацию о подразделении организации. Запрос доступен только администраторам организации.

**Пример запроса с использованием C# SDK**:

*Внимание!* В SDK соответсвующий метод имеет название *GetDepartmentByFullId*. Метод *GetDepartment* отвечает за вызов к другому методу API :doc:`../../http/GetDepartment`.

.. code-block:: csharp

    var department = api.GetDepartmentByFullId(token, boxId, departmentId);