# Система поддержки принятия решений для врачей-онкологов
## Документация проекта

### 1. Цели и предпосылки
#### 1.1 Текущий бизнес-процесс

- Не во всех регионах РФ отделения онкологии/гематологии проводят высокотехнологичное лечение.
- Пациентам приходится обращаться в центры/институты в крупных городах.
- Центры/институты в крупных городах перегружены, так как им отправляют самые разные запросы со всех уголков страны.
- Иногда пациенты напрямую обращаются к врачам-онкологам для консультации.
- Для проведения онлайн-консультации между врачами и пациентами используются такие инструменты, как `электронная почта` и `ТелеМед`.
- Однако оба эти инструмента не приспособлены для проведения онлайн-консультаций и хранения и обработки данных пациентов.
- Кроме того, из-за высокой загруженности врачи в институтах/центрах могут вовремя не проанализировать критические случаи

#### 1.2 Выявленные проблемы

- У врачей-онкологов нет удобного инструмента для проведения онлайн-консультаций
- Врачам необходим инструмент для ускорения принятия решений, так как в такой сфере, как онкология, очень важно вовремя отследить изменения опухоли
- Молодым врчам требуется много времени для анализа более 200 изображений

#### 1.3 Цели и предпосылки

- Цель – разработать инструмент для взаимодейтсвия врачей и пациентов, в который будут интегрированы системы классификации изображений (есть/нет опухоли) и сегментации опухолей
- Цель итерации – запустить пилот и отдать его на тестирования заказчикам (БГМУ – Башкирский Государственный Медицинский Университет)
- Использование ML позволит ускорить процесс принятия врачом решения.

#### 1.4 Бизнес-требования и ограничения

- В рамках пилота мы работаем с МРТ-снимками головного мозга
- __Использование ML ни в коем случае не призвано заменить врача__. Результаты работы ML моделей __не будут__ показываться пациентам
- C4 Context Level:  
![C4 Context Level](https://github.com/bs-muu/.github/blob/main/images/ai-screen-it-C4_Context_-_For_Presentation.drawio.png)  
- Врач и пациент будут взамодействовать через Redmine (`Тасктрекер`/`Система взаимодействия пациентов и врачей`). Врач будет создавать для конкрентного пациента "проект", затем будет отправлять приглашение пациенту в этот проект. Пациент сможет выложить в проект свой МРТ-снимок, который автоматически будет проанализирован ML моделями 
- Успешным пилотом будет считаться после получения положительной обратной связи от заказчиков после первого тестирования

### 2. Методология
#### 2.1 Постановка задачи

- Мы будем решать задачу __классификации__ изображений и семантической __сегментации__ для попиксельной обработки изображения.
- Классификация изобажений необходима:
  - Для фильтрации нерелевантных изображений для обучения модели сегментации;
  - Классификация позволит подсветить врачу изображения, на которые стоит обратить внимание в первую очередь.
- Сегментация изображений необходима:
  - Врач сможет показать пациенту изображение с выделенной опухолью;
  - Врач сможет проследить динамику изменения опухоли;
  - Дополнительная проверка для врача.

#### 2.2 Этапы решения задачи

| № спринта | Даты спринта | Описание работ во время спринта | 
| ------------- | ------------- | ------------- |
| 1 | 26.10.2023 – 02.11.2023  | что-то |
| 1 | 02.11.2023 – 16.11.2023 | что-то |
| 1 | 16.11.2023 – 23.11.2023  | что-то |
| 1 | 23.11.2023 – 30.11.2023  | что-то |
| 1 | 30.11.2023 – 07.12.2023  | что-то |
| 1 | 07.12.2023 – 14.12.2023  | что-то |
| 1 | 14.12.2023 – 21.12.2023  | что-то |
| 1 | 21.12.2023 – 28.12.2023  | что-то |

### 3. Пилот
#### 3.1 Что считается успешным пилотом

- Успешным пилотом будет считаться после получения положительной обратной связи от заказчиков после первого тестирования

#### 3.2 Архитектура решения

- Activity Diagram:  
![Activity Diagram](https://github.com/bs-muu/.github/blob/main/images/ai-screen-it-Activity%20diagram.drawio.png)  

- C4 Context Level:  
![C4 Context Level](https://github.com/bs-muu/.github/blob/main/images/ai-screen-it-C4_Context_-_For_Presentation.drawio.png)
- C4 Container Level для `Системы взаимодействия пациентов и врачей`:  
![C4 Container Level](https://github.com/bs-muu/.github/blob/main/images/ai-screen-it-C4%20Container.drawio.png)

#### 3.3 Безопасность данных

- Так как у нас ведется работа с персональными данными пациентов, мы понимаем важность зашиты персональных данных.
- Вся работа у нас ведется на нашем собственном сервере. Данные пациентов зашифрованы.

### 4. Команда проекта
#### 4.1 Менторы

| Имя Фамилия | Должность |
| ------------- | ------------- |
| Рамиль Зайнуллин  | Инициатор и Куратор проекта  |
| Дмитрий Головин  | Архитектор, Разработчик ПО  |
| Эндже Валиахметова | Врач нейроонколог НМИЦ им. Бурденко |

#### 4.2 Студенты 1 курса AI Talent Hub

| Имя Фамилия | Должность |
| ------------- | ------------- |
| Артем Даняев | ML Engineer |
| Михаил Бекусов | ML Engineer |
| Константин Калиновский | ML Engineer |
| Александр Лакиза | Product Manager |
| Сергей Китаев | Разработчик ПО |

### 5. Полезные материалы
- [Презентация 18.12.2023 на проектном семинаре](https://docs.google.com/presentation/d/1jmd8ZPJN2W_otuVlJMtpkSThPnvUJVPi6uIuxa3TRTQ/edit?usp=sharing)




















