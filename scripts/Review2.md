Добрый день,

Ответ на ваш вопрос: вы же сделали не геттер, когда метод определеяется через get myId, а просто метод myId, соответственно когда вы делаете вызов метода, то вызывать надо userInfo.myId() -- если хотитче чтобы без скобок, то метод должен быть определен так:
 
  get getId() {
    return this.id;
  }

Если вы вызывали метод корректно, то может быть из-за асинхронности в том месте, где был вызов в тот момент не получен ответ с данными от сервера.

## Надо исправить
- У вас все еще уйма лишних запросов в консоли, для загрузки страницы нужно 2 GET запроса -- один к картам, другой к юзеру, у вас 3 к юзеру, но и потом еще ворох запросов по лайкам, но зачем, вы ведь при первом обращении к картам все уже получили. Это исправляйте, нельзя так сервер укладывать. Исправлено!
- см. комментарии в Script, Avatar и UserInfo +
- Массу запросов генерирует CardList там надо поработать +
- Аватара кусто при загрузке все еще на месте, ее надо в css убрать +
- Ваша цель -- 2 GET запроса при загрузке. +
- Приложил скриншот с запросами

Исправляйте и присылайте, я попросил вам +2 дня к дедлайну