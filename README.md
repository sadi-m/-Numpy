# -Numpy
The concepts of vectorization, indexing and translation of NumPy, fast and versatile, are the actual standards of computing with arrays today.
#Этот код генерирует вектор из 1000 нормально распределенных случайных чисел и строит две гистограммы:
#С числом "карманов" (столбцов) по правилу квадратного корня (√n).
#По правилу Стерджесса (log₂(n) + 1).
#Гистограммы показывают распределение данных с разным количеством столбцов.
# ваш код здесь
import numpy as np
import matplotlib.pyplot as plt

# Параметры
n = 1000  # Размер вектора
mu = 0  # Среднее
sigma = 1  # Стандартное отклонение

# Создаем вектор случайных нормально распределенных чисел
data = np.random.normal(mu, sigma, n)

# Построение гистограммы с разным числом карманов
plt.figure(figsize=(10, 6))

# Оптимальный выбор числа карманов
bins_sqrt = int(np.sqrt(n))  # Правило квадратного корня
bins_sturges = int(np.log2(n) + 1)  # Правило Стерджесса

# Построение гистограмм
plt.subplot(1, 2, 1)
plt.hist(data, bins=bins_sqrt, edgecolor='black')
plt.title(f'Гистограмма: √n = {bins_sqrt} карманов')
plt.xlabel('Значения')
plt.ylabel('Частота')

plt.subplot(1, 2, 2)
plt.hist(data, bins=bins_sturges, edgecolor='black')
plt.title(f'Гистограмма: правило Стерджесса = {bins_sturges} карманов')
plt.xlabel('Значения')
plt.ylabel('Частота')

plt.tight_layout()
plt.show()
