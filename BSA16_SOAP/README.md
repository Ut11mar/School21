# SOAP04 — Интеграция веб-сервисами SOAP: Клуб любителей домашних животных

## О проекте

Модуль посвящён интеграции систем по протоколу SOAP: формальному описанию контрактов веб-сервисов на языке WSDL, структурам данных на XSD и разбору готового контракта по методике CONTRACT-FIRST. Для учебной задачи «Клуб любителей животных» спроектированы два независимых SOAP-сервиса — `MemberService` (члены клуба) и `PetService` (питомцы), — а их контракты (`member.wsdl`, `pet.wsdl`) последовательно проанализированы в шести упражнениях.

## Что было сделано

- `member.wsdl`, `pet.wsdl`
  Контракты обоих сервисов: структуры данных `Member`/`Pet`, пять операций на каждый сервис (добавление, поиск/чтение, обновление, удаление), сообщения об ошибках (`fault`) и адреса (`endpoint`), по которым сервисы фактически доступны.

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 00**
  Логические части документа WSDL (теги первого уровня): `<definitions>`, `<documentation>`, `<types>`, `<message>`, `<portType>`, `<service>` — с указанием назначения каждой.

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 01**
  Операции раздела `<portType>` обоих сервисов (`AddMember`, `GetAllMembers`, `GetMemberByName`, `UpdateMember`, `DeleteMember` и аналогичный набор для `PetService`) с расшифровкой назначения по имени метода.

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 02**
  Разбор раздела `<schema>`: назначение `<element>`, атрибута `type`, `<complexType>`, `<sequence>`, `minOccurs`/`maxOccurs`, а также правила определения обязательности и множественности элементов.

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 03**
  Обратное проектирование операций `addMember`, `addPet`, `updatePet`, `getAllMembers`: построчный формат входных и выходных сообщений (поле, назначение, тип, признак массива, обязательность).

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 04**
  Сопоставление выходных сообщений `getAllMembers` (массив записей) и `getMemberByName` (единичная запись).

- `Exercises_00-05_SOAP_PetClub_v2.docx` · `Exercises_00-05_SOAP_PetClub.xlsx` — **Exercise 05**
  Определение адресов (`endpoint`) обоих сервисов по разделу `<service>`.

- `SOAP_PetClub_Narrative_v2.docx`
  Пояснительная записка: теоретические основы SOAP/WSDL/XSD, построчный разбор обоих контрактов и содержательное описание каждого упражнения.

## Итоги

После этого модуля WSDL перестал быть просто XML-файлом со странным синтаксисом — это рабочий контракт, по которому можно однозначно понять устройство чужого сервиса, ничего не спрашивая у автора. Подход CONTRACT-FIRST показал разницу между «написать код и подогнать документацию» и «сначала зафиксировать правила игры»: во втором случае ошибки вроде отсутствующего поля или неограниченного набора значений видны сразу при чтении схемы, а не после интеграции. Отдельный урок — техническая проверка контракта: часть несоответствий (например, некорректная ссылка на тип вместо элемента) нашлась только после прогона схемы через валидатор, а не при простом чтении файла.

## Навыки

![SOAP](https://img.shields.io/badge/SOAP-2F5496?style=for-the-badge)
![WSDL](https://img.shields.io/badge/WSDL-6A5ACD?style=for-the-badge)
![XSD%20%2F%20XML](https://img.shields.io/badge/XSD%20%2F%20XML-2E8B57?style=for-the-badge)
![CONTRACT--FIRST](https://img.shields.io/badge/CONTRACT--FIRST-D2691E?style=for-the-badge)
![Валидация%20схем](https://img.shields.io/badge/Валидация%20схем-B22222?style=for-the-badge)
![Реверс--инжиниринг%20API](https://img.shields.io/badge/Реверс--инжиниринг%20API-4B0082?style=for-the-badge)

---

[⬅ Назад к портфолио](../README.md)
