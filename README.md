# Time-Series-Prediction
Predict PJME_MW to 1 day consumption  

Предсказание потребления энергии


Data: PJME_MW.csv

Time_series_PJME.ipynb - Working report on the modeling process - Рабочий отчет о процессе формирования моделей
Test_Time_series_PJME.ipynb - Test functions for using the model - Тестовые процедуры для использования модели

model_weight.h5 - model Neuro Net (LSTM) weight -  веса модели
final_scaler.sav - Scaler Object - Объект для масштабирования признаков
final_select.sav - Объект для отбора признаков


Данные почасовые 
Предсказание делаем на 24 часа вперед
Для предсказания используем предисторию на 7 дней назад и среди признаков есть признак с окном обработки 1 год (скользящее среднене - надо поменять на экспоненциальный)

Для запуска модели в тестирование используем Test_Time_series_PJME.ipynb:
 - переходим в Googl Colaboratory
 - Выбираем "Среда выполнения/выполнить все"
 - запуск модели с данными:
    Path = '/content/cloned-repo/'  # путь к файлам модели
    t=5 # интервал
    T = 20000  # Сдвиг начальной точки тестов
    y_work=model_work(data_test.iloc[-T-t:-t], Path)


Модель построена в Time_series_PJME.ipynb:
1. Анализ данных и их очистка
2. Построение признаков
3. Отбор признаков
4. Построение первичных моделей и их сравнение
5. Сеточный поиск для модели (LSTM+Conv+Dense)
6. Формирование финальной модели
7. Построение функций для работы с моделью



