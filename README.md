# Sber_Graduate

1.

import numpy as np
sample_array = np.array([[6, 5, 4], [3, 2, 1]])
print(sample_array[1, 1])


ответ
2

6. 
Предположим, что матрица ошибок для нашей модели имеет следующие значения: TP - 300 | TN -150 | FP - 100 | FN - 200. Какое из этого следует утверждение про precision, recall и accuracy?
Исходя из значений матрицы ошибок TP, TN, FP и FN для нашей модели, мы можем рассчитать следующие показатели:

Исходя из значений матрицы ошибок TP, TN, FP и FN для нашей модели, мы можем прояснить, что каждый из этих элементов означает:

1. True Positive (TP) - 300: это количество положительных случаев, которые были правильно распознаны как положительные. В нашем случае, это означает, что модель правильно классифицировала 300 положительных случаев.

2. True Negative (TN) - 150: это количество отрицательных случаев, которые были правильно распознаны как отрицательные. В нашем случае, это означает, что модель правильно классифицировала 150 отрицательных случаев.

3. False Positive (FP) - 100: это количество отрицательных случаев, которые были неправильно распознаны как положительные. В нашем случае, модель неправильно классифицировала 100 отрицательных случаев как положительные.

4. False Negative (FN) - 200: это количество положительных случаев, которые были неправильно распознаны как отрицательные. В нашем случае, модель неправильно классифицировала 200 положительных случаев как отрицательные.

Используя эти значения, мы можем вычислить показатели оценки качества модели, такие как точность (precision), полнота (recall) и общая точность (accuracy). Эти показатели помогают оценить эффективность модели в правильном предсказании классов (положительного или отрицательного).

1. Precision (точность) измеряет, насколько точно модель идентифицирует правильные положительные случаи относительно всех положительных предсказаний (TP + FP). Формула для вычисления precision:

   Precision = TP / (TP + FP)

   В нашем случае:

   Precision = 300 / (300 + 100) = 0.75

   Значит, у нас есть 75% уверенность в том, что наши положительные предсказания являются правильными.

2. Recall (полнота) измеряет, насколько хорошо модель обнаруживает все положительные случаи относительно всех фактически положительных случаев (TP + FN). Формула для вычисления recall:

   Recall = TP / (TP + FN)

   В нашем случае:

   Recall = 300 / (300 + 200) = 0.6

   Значит, наша модель обнаруживает лишь 60% из всех положительных случаев.

3. Accuracy (точность) измеряет общую точность модели, т.е. долю правильных предсказаний относительно общего количества случаев (TP + TN + FP + FN). Формула для вычисления accuracy:

   Accuracy = (TP + TN) / (TP + TN + FP + FN)

   В нашем случае:

   Accuracy = (300 + 150) / (300 + 150 + 100 + 200) = 0.55

   Следовательно, точность или доля правильных ответов нашей модели составляет 55%.

Итак, высчитав эти значения из матрицы ошибок, мы можем сделать следующие утверждения: precision равно 0.75 (75%), recall равно 0.6 (60%), а accuracy равно 0.55 (55%).


7.

Верно ли работает "def softmax(x): return np.exp(x) / np.sum(np.exp(x), axis=0)" приведенная реализация функции softmax?

В формуле softmax для вычисления вероятностей нужно использовать экспоненту от каждого элемента вектора, а затем делить на сумму экспоненты всех элементов вектора.

Ошибка в данной реализации состоит в том, что вместо вычисления суммы экспоненты всех элементов вектора "np.sum(x, axis=0)", выполняется деление на сам вектор "np.sum(x, axis=0)". Это приведет к некорректным результатам, поскольку сумма вероятностей не будет равна 1.

Правильная реализация функции softmax должна быть следующей:
```python
def softmax(x):
    return np.exp(x) / np.sum(np.exp(x), axis=0)
```

В этой редакции функция np.sum(np.exp(x), axis=0) вычисляет сумму экспоненты всех элементов вектора x, а затем делится на эти сумму, чтобы получить правильное вероятностное распределение.


8.

Таблица T1, T2, и T3 имеют 5, 10 и 30 записей соответственно. Есть записи, которые встречаются во всех трех таблицах. Мы сделали cross join всех таблиц. Сколько строк получилось в результате join'a?


Чтобы найти количество строк в результате join'а, нужно умножить количество строк в каждой таблице. В данном случае мы производим cross join всех трех таблиц, то есть каждая строка из таблицы T1 будет комбинироваться с каждой строкой таблицы T2 и каждой строкой таблицы T3.

Таблица T1 имеет 5 строк, таблица T2 имеет 10 строк, а таблица T3 имеет 30 строк. Чтобы найти общее количество строк, нам нужно умножить эти три значения:
5 (строк в T1) * 10 (строк в T2) * 30 (строк в T3) = 1500.

Таким образом, результат join'а будет содержать 1500 строк.

9.

Результат какого джойна вернет минимальное количество записей (left join, inner join, outer join, cross join)?


Результат с наименьшим числом записей будет возвращен при использовании inner join. 

Inner join возвращает только записи, которые имеют совпадения в обоих таблицах, и исключает все строки, которые не имеют совпадений. Таким образом, результат inner join будет содержать только совпадающие записи из обеих таблиц.

С другой стороны, left join возвращает все записи из левой (первой) таблицы и только совпадающие записи из правой (второй) таблицы. Outer join возвращает все записи из обеих таблиц, включая несовпадающие записи. Cross join производит комбинацию каждой записи из первой таблицы со всеми записями из второй таблицы.

Таким образом, поскольку inner join фильтрует только совпадающие записи, он будет возвращать наименьшее количество строк среди этих четырех типов джойнов.


10.

Если добавить новых переменных в линейную модель , тогда R-squared ?

Если мы добавляем новые переменные в линейную модель, то коэффициент детерминации (R-squared) может измениться. 

Коэффициент детерминации показывает, насколько хорошо линейная модель соответствует фактическим данным. Он представляет долю дисперсии зависимой переменной, которая объясняется моделью. Значение R-squared находится в диапазоне от 0 до 1, где 1 означает, что модель полностью объясняет вариацию данных, а 0 означает, что модель не объясняет вариацию данных вообще.

Когда мы добавляем новые переменные в модель, это может привести к лучшему соответствию модели данным, если эти новые переменные могут объяснить дополнительную вариацию в зависимой переменной. Если новые переменные сильно коррелированы с зависимой переменной и/или существующими предикторами, это может привести к увеличению значения R-squared. Однако, если новые переменные не объясняют значительную дополнительную вариацию, то значение R-squared может не сильно измениться или даже уменьшиться.

Важно помнить, что добавление новых переменных в модель также может увеличить сложность модели и привести к проблеме переобучения, особенно если количество переменных превышает количество доступных наблюдений. Поэтому важно балансировать добавление новых переменных с учетом их релевантности и множественной корреляции с другими переменными.



1.

Вы подбрасываете "справедливую монетку" 5 раз. Оцените, какая вероятность выпадения 4еx или 5 ти орлов?

Если мы подбрасываем справедливую монетку, то у нее есть 2 равновероятных исхода - орел (О) и решка (Р). Вероятность выпадения орла в одном броске равна 0.5, а вероятность выпадения решки также равна 0.5.

Есть несколько способов посчитать вероятность выпадения 4х или 5ти орлов:

1. Вероятность выпадения ровно 4х орлов:
   - Вероятность выпадения орла в одном броске: 0.5
   - Вероятность выпадения решки в одном броске: 0.5
   - Количество сочетаний, при которых можно выбрать 4 броска из 5, чтобы выпал орел: C(5,4) = 5
   - Общая вероятность выпадения ровно 4х орлов: 0.5^4 * 0.5 * 5 = 0.15625

2. Вероятность выпадения ровно 5ти орлов:
   - Вероятность выпадения орла в одном броске: 0.5
   - Количество сочетаний, при которых можно выбрать 5 бросков из 5, чтобы выпал орел: C(5,5) = 1
   - Общая вероятность выпадения ровно 5ти орлов: 0.5^5 * 1 = 0.03125

Теперь мы можем сложить обе вероятности, чтобы получить общую вероятность выпадения 4х или 5ти орлов:

0.15625 + 0.03125 = 0.1875

Таким образом, вероятность выпадения 4х или 5ти орлов при подбрасывании справедливой монетки 5 раз равна 0.1875 или 18.75%.



6.

При решении задач NLP можно использовать предобученные языковые модели, например, BERT. В таких моделях используются слой self-attention. Зачем он необходим?


Давай представим, что ты учишься читать книгу. Когда ты читаешь каждое слово, тебе может потребоваться обращаться назад, чтобы связать его с другими словами в предложении и понять его контекст. Например, если в предложении сказано "Корабль плыл ___ порту", чтобы понять, куда плывет корабль, тебе нужно обратиться назад и прочитать слово "порту". 

В языковых моделях, таких как BERT, слой self-attention выполняет аналогичную задачу. Он позволяет модели "обратить внимание" на важные части текста для более глубокого понимания контекста. Вместо того, чтобы просто последовательно обрабатывать каждое слово по очереди, слой self-attention позволяет модели смотреть на все слова в предложении и определять, какие слова являются наиболее важными для понимания текущего слова.

Self-attention работает следующим образом: каждому слову в предложении назначается вес, который показывает, насколько важным оно является для понимания контекста. Затем модель использует эти веса, чтобы сконцентрироваться на наиболее значимых словах при анализе контекста текущего слова. Это позволяет модели улавливать более сложные зависимости между словами и более точно предсказывать значения их в контексте.

Таким образом, слой self-attention в предобученных языковых моделях, таких как BERT, необходим для улучшения понимания контекста текста и создания более точных и выразительных предсказаний или анализа текста в задачах NLP.


7. В iт-отделе 6 сотрудников. Директор один раз в день оплачивает обед одному, случайно выбранному сотруднику. Какая вероятность, что за шестидневную неделю он оплатить обеды всем?

Давай представим, что у тебя есть шесть разноцветных конфет в руке, а каждая конфета представляет одного из сотрудников из iт-отдела. Каждый день директор выбирает одну случайную конфету и оплачивает обед сотруднику, представленному этой конфетой. Ты хочешь узнать вероятность того, что за шестидневную неделю все шесть конфет будут выбраны.

Начнем со случая, в котором у тебя есть только одна конфета в руке. Вероятность выбора этой конфеты составляет 1 из 6, так как у тебя есть 6 разных конфет. 

Теперь представь, что ты выбираешь вторую конфету. У тебя осталось только 5 конфет, и вероятность выбрать любую из этих оставшихся конфет составляет 1 из 5.

Ты можешь продолжать этот процесс для третьей, четвертой, пятой и шестой конфеты, уменьшая количество оставшихся конфет на одну и выбирая одну конфету каждый раз.

Теперь, чтобы найти вероятность выбрать все шесть конфет, мы можем перемножить все вероятности выбора каждой конфеты:

(1/6) * (1/5) * (1/4) * (1/3) * (1/2) * (1/1) = 1/720 ≈ 0.00139

Таким образом, вероятность того, что директор оплатит обеды всем шести сотрудникам за шестидневную неделю, составляет примерно 0.00139 или около 0.139%.


8.

Какие из приведенных моделей не относятся к дискриминативным (Conditional Random Fields, Hidden Marvok Trees, Maximum Entropy Markov Models, Naive Bayes)?


Давай представим, что у тебя есть четыре коробки с животными внутри: коробка 1 - Random Fields, коробка 2 - Hidden Marvok Trees, коробка 3 - Maximum Entropy Markov Models, коробка 4 - Naive Bayes. Мы хотим определить, какие из этих коробок не относятся к дискриминативным моделям.

Итак, давай посмотрим на каждую коробку и попробуем понять, является ли модель внутри коробки дискриминативной:

1. Random Fields: Да, модель Conditional Random Fields (CRF) относится к дискриминативным моделям. Так что эта коробка относится к дискриминативным моделям.

2. Hidden Marvok Trees: Нет, модель Hidden Marvok Trees (HMT) не относится к дискриминативным моделям. Эта модель используется для моделирования генеративных вероятностных моделей, а не дискриминативных.

3. Maximum Entropy Markov Models: Да, модель Maximum Entropy Markov Models (MEMM) также относится к дискриминативным моделям. Так что эта коробка относится к дискриминативным моделям.

4. Naive Bayes: Да, модель Naive Bayes тоже относится к дискриминативным моделям. Хотя она имеет предположение о независимости признаков, она все равно является дискриминативной моделью.

Итак, из четырех коробок, только вторая коробка "Hidden Marvok Trees" содержит модель, которая не относится к дискриминативным моделям. Остальные три модели (CRF, MEMM и Naive Bayes) являются дискриминативными моделями.


9.

как нельзя найти медианное значение для столбца "Price" с помощью Pandas? (df.Price.median() | df["Price"].quantile(0.5) | df["Price"].median() | median(df["Price"]) )


Давай представим, что у тебя есть специальный ящик с числами внутри, которые представляют значения цены для разных товаров. Мы хотим найти медианное значение (число, которое находится посередине, когда все числа упорядочены по возрастанию или убыванию) для столбца "Price" с помощью Pandas.

1. df.Price.median(): Возьми эту коробку с числами и найди среднее значение. Но ой, в Pandas, чтобы найти медиану, мы используем метод "median()", а не "mean()" (среднее значение). Поэтому этот способ неправильный.

2. df["Price"].quantile(0.5): Здесь мы берем нашу коробку с числами и находим значение, которое находится на 50% месте. Это прямо как разделять коробку наполовину и найти значение посередине. Отлично, это метод, который можно использовать, чтобы найти медиану!

3. df["Price"].median(): Этот способ похож на второй способ, но использует метод "median()" вместо "quantile()". Здесь мы снова находим значение, которое находится посередине, так что это правильный способ!

4. median(df["Price"]): Ну здесь мы пытаемся найти медиану, но используем функцию "median()" вместо метода Pandas. Панды тут не знают, о какой функции ты говоришь, потому что они знакомы только с методами. Так что этот способ не будет работать.

Итак, чтобы найти медианное значение для столбца "Price" с помощью Pandas, правильные способы - это df["Price"].quantile(0.5) и df["Price"].median(). Оба они помогут тебе найти медиану твоих чисел в столбце "Price".


5. Нам надоело самим принимать решения, поэтому мы хотим обучить Decision Tree на большом наборе данных. Какие варианты помогут сократить время на обучение?


Конечно, могу объяснить! Обучение Decision Tree на большом наборе данных может занять довольно много времени, но есть несколько вариантов, которые могут помочь ускорить этот процесс:

1. Размер обучающего набора: Уменьшить размер обучающего набора данных может существенно сократить время обучения. Вы можете случайным образом выбрать подмножество данных или использовать методы для сбалансированного сокращения выборки, чтобы сохранить репрезентативность данных.

2. Предварительная обработка данных: Отчистка и предварительная обработка данных могут убрать шум, аномалии и неинформативные факторы. Это может ускорить процесс обучения, так как Decision Tree будет работать с более чистыми и полезными данными.

3. Подбор параметров: Попробуйте провести подбор параметров Decision Tree, таких как глубина дерева или критерии разделения, чтобы найти оптимальные значения. Это может помочь улучшить производительность Decision Tree и сократить время обучения.

4. Использование параллельных вычислений: Если у вас есть возможность использовать параллельные вычисления, например, при обучении на GPU или распределенных системах, это может значительно ускорить процесс обучения.

5. Использование алгоритмов сжатия или усечения: Некоторые алгоритмы, такие как Random Forest или Gradient Boosting, могут предложить более быстрые альтернативы для обучения, при этом сохраняя точность модели.

Использование комбинации этих методов может помочь вам сократить время на обучение Decision Tree и получить результаты быстрее.

Теперь по варинатам сбера
(увеличить глубину дерева, уменьшить глубину дерева, увеличить learning rate, уменьшить количество деревьев) – варианты сбера


Обучение Decision Tree на большом наборе данных может занять много времени, и варианты, которые вы предложили, влияют на производительность и точность модели. Давайте рассмотрим каждый из них отдельно и их влияние на время обучения:

1. Увеличить глубину дерева: Увеличение глубины дерева может привести к более сложной модели, которая лучше подстроится под тренировочные данные. Однако, это может также увеличить время обучения, поскольку дерево будет иметь больше уровней и будет более требовательным к вычислениям.

2. Уменьшить глубину дерева: Уменьшение глубины дерева может упростить модель, сделав ее менее сложной и менее склонной к переобучению. Это может помочь сократить время обучения, так как дерево будет более поверхностным. Однако, это также может снизить точность модели.

3. Увеличить learning rate: Увеличение learning rate позволяет модели быстрее "обучаться" на данных, так как каждое обновление модели будет более значимым. Это может помочь ускорить процесс обучения, поскольку модель будет быстрее приближаться к оптимальному решению. Однако, слишком высокий learning rate может привести к нестабильным результатам или пропуску оптимального решения.

4. Уменьшить количество деревьев: Уменьшение количества деревьев в модели может сократить время обучения, так как изучается меньшее количество деревьев. Однако, это может также уменьшить точность модели, особенно если исходное значение было выбрано оптимально.

Из этих вариантов, уменьшение глубины дерева, увеличение learning rate и уменьшение количества деревьев могут помочь сократить время обучения. Однако, важно понимать, что изменение этих параметров может иметь свои последствия для точности модели. Рекомендуется проводить эксперименты с разными значениями и оценивать, как время обучения, так и качество модели, чтобы найти оптимальный баланс.


4.
Какой метод используют при построение линейной регрессии?
(Maximum Likelihood, Logarithmic Loss, Least Square Error, Ни один из методов не подходит)

Метод наименьших квадратов (least square error) широко применяется при построении линейной регрессии.

Метод наименьших квадратов является основным методом для оценки коэффициентов и построения линейной регрессии. Он минимизирует сумму квадратов расстояний (ошибок) между исходными данными и значениями, предсказываемыми линейной моделью.

Суть метода заключается в том, чтобы найти такие значения параметров (наклона и пересечения), которые минимизируют ошибку предсказания на основе имеющихся данных. Модель линейной регрессии строится таким образом, чтобы предсказанные значения как можно ближе совпали с фактическими значениями.

В итоге, метод наименьших квадратов применяется для нахождения оптимальной прямой (линии), которая наилучшим образом соответствует зависимости между входными и выходными данными.

Поэтому, можно сказать, что метод наименьших квадратов является примарным методом, используемым при построении линейной регрессии.
