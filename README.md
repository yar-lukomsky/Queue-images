Что нужно:
- в `libraries/db.php` - прописаны доступы в БД

Реализация:
- запускаем демоном в фоне скрипт `queue/worker.php`
- он в свою очередь просматривает папку `prepared_files` на наличие нужных ему файлов
- если файлы есть - обрабатывает (создает превью, переносит обработанные файлы в другую папку и записывает в БД информацию о новой картинке), думал сделать через мета-данные картинки, но нашел только как получить данные, при том не все..(
- при переходе по роуту `/?r=form` есть форма через которую загружаются картинки
- потратил времени - 2.5 часа:
    - просмотрел Gearman (вместо него решил реализовать "демон-сервис" - самому быстрее)
    - искал как же все таки изменять мета-данные самой картинки (интереснее чем ложить в бд) - но не нашел как, поэтому данные в базе
    - прописал простенькое API, для CRUD (без create)

В рамках текущей задачи решил не усложнять)
