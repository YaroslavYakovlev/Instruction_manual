# Instruction_manual
Описание как работать с GitHub


Делаем git init в папке с проектом

Создаем(корректируем) файлы

Делаем git add FILE1 FILE2 ...  - это внести файлы для коммита

              ИЛИ
              
Делаем git add. - это внести все изменения и новые файлы 

Делаем git commit -m "commit comment" (создаем коммит и пишем комментраий)

Подготавливаем репозиторий на GitHub (если взаранее не подготовлен)

Делаем git remote add origin https://github.com....... (это позволяет подключится к удаленному репозиторию)

Затем делаем git push --set-upstream origin master (отправляем изменения на  удаленный репозиторий)

----------------------------------------------------------------------------------------------------------------------------

ДЛЯ КОМПИЛЯЦИИ:

Вариант 1:

Пишем к командной строке проекта - g++ main.cpp -o start

где, main.cpp это имя файла, который компилируем,

а команда -o start создает исполняемы файл с именем start в той же директории

Затем создается исполняемый файл и просто его запускае из той же деректории (пример .\start)

Вариант 2:

Жмем терминал -> Настроить задачи сборки по умолчанию -> C/C++:g++.exe сборка активного файла

Создается tasks.json, и можем собирать через ctrl+shift+b.

Затем так же создается исполняемый файл и просто его запускае из той же деректории (пример .\start)

----------------------------------------------------------------------------------------------------------------------------

НАСТРОЙКА DEBBUGER:

В разделе debbug жмем "Запусить и отладка"

Выбираем C++(GDB/LLDB) и выбираем g++.exe - Сборка и отладка активного файла

Создается launch.json

----------------------------------------------------------------------------------------------------------------------------

CMake:

Для того чтобы собрать проект через CMake необходимо:
Создать папку build в проекте.
Создать папку src и пренести туда все проекты.

Прописать строчик в CMakeLists.txt:

cmake_minimum_required(VERSION 3.16)

project(Template_Project)

set(SOURCE main.cpp)

add_executable(${PROJECT_NAME} ${SOURCE})

Генерируем конкретный MakeFile через MinGW:

PS D:\ProjectCPP\TestCMake\build> cmake ..\src -G "MinGW Makefiles"   

Собрать проект в build:

PS D:\ProjectCPP\TestCMake\build> cmake --build . 

Потом можно запускать стартовый файл из папки build
.\TestCMake.exe
