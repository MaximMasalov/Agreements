# Agreements
Need to install libraries from file "requirements.txt". 

To do this, in the terminal of your project, enter the command:
  
    pip install -r requirements.txt
    
# Task:
Необходимо реализовать минималистичное Django приложение с админкой и одним REST методом.

# Description:

## General
Модуль предназачен для анализа дискаунт соглашений между компаниями-партнёрами.
Понятие 1 - Соглашение о скидке (Agreement)
Понятие 2 - Период соглашения (Period)
Понятие 3 - Компания (Company)
Понятие 4 - Страна (Country)
Понятие 5 - Ответственное лицо (Negotiator)
Agreement имеет дату начала и окончания, компанию с которой заключается скидка, ответственное лицо (negotiator)
Оборот по кредиту, оборот по дебету (экспорт/импорт).
Period - дата начала и окончания, статус (описание ниже).
Внутри одного соглашения может быть несколько периодов.
Внутри соглашения периоды не пересекаются.
Дата начала соглашения может быть меньше даты начала первого периода.
Точно также, дата окончания может быть больше даты окончания последнего периода.
Company - название, страна.
Country - 3-alpha iso code, name
Negotiator - пользователь, который отвечает за соглашение. Должен быть также джанго пользователем.
Status - состояние периода, может быть: New, Active, Reconciliation, Closed

## Админка
Для всех объектов должна быть удобная админка.
Надо предусмотреть поиск, фильтры согласно эргономике использования.
Agreement должен отображать Periods с помощью tabular inline.

## UI
Пользовательский интерфейс показывает ссылку Admin на главной странице.

## API
Необходимо реализовать API для календаря соглашений: https://drive.google.com/file/d/11f_AthRwxbIM-SOxsGpd3yR0jihexla7/view?usp=sharing
Цифра, которая отображается в месяце - это количество соглашений, которые оканчиваются в этом месяце.
Соглашение оканчивается в этом месяце означает, что дата окончания последнего периода содержится в данном месяце.
/agreements/calendar/ - должна возвращать данные в JSON такого формата:
{
2014: [0, 0, 0, 0, 0, 0, 0, 0, 12, 1, 0, 5],
2015: [1, 0, 0, 4, 0, 0, 0, 1, 7, 10, 0, 4]
}
2014, 2015 - это года
Массивы - индекс означает номер месяца, число - количество оканчивающихся соглашений.
Запрос должен поддерживать следующие фильтры:
country, negotiator, company.
Например: ?country=1,2,7&negotitator=4,8
Число - это id объекта.

# Requirements:

## General:

Provide fixtures that contain test data: several agreements with several periods

## Will be a plus:

1. Unit tests

2. Coding style

3. 1 tab equals to 3 spaces

4. Code should correspond to industrial standards: pep8, pylint et al.

## Results:

You need to provide information about hours spent on this task, preferrably with split by subtasks.
