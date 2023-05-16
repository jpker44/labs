Лабораторна робота №6

Ось її код

def calculate_estimate(a, m, b):
    E = (a + 4 * m + b) / 6
    SD = (b - a) / 6
    return E, SD

def calculate_project_interval(tasks):
    total_E = 0
    total_SE = 0

    for task in tasks:
        a, m, b = task
        E, SD = calculate_estimate(a, m, b)
        total_E += E
        total_SE += SD

    project_E = total_E
    project_SE = total_SE

    project_CI_min = project_E - 2 * project_SE
    project_CI_max = project_E + 2 * project_SE

    return project_CI_min, project_CI_max
    
  num_tasks = int(input("Введіть кількість завдань: "))
 tasks = []

 for i in range(num_tasks):
    a = float(input("Введіть оцінку a для завдання {}: ".format(i+1)))
    m = float(input("Введіть оцінку m для завдання {}: ".format(i+1)))
    b = float(input("Введіть оцінку b для завдання {}: ".format(i+1)))
    tasks.append((a, m, b))

 project_CI_min, project_CI_max = calculate_project_interval(tasks)

 print("Project's 95% confidence interval: {} ... {} points".format(project_CI_min, project_CI_max))
 
 
 А це її скріншот у виконанні
 
 <img width="952" alt="Знімок екрана 2023-05-16 163948" src="https://github.com/jpker44/labs/assets/127845127/57a87f22-cae3-421c-80f5-a8a17a0f5491">

 
 Ця програма спочатку отримує від користувача кількість завдань та їх оцінки (a, m, b). Потім вона обчислює оцінку (E) та стандартне відхилення (SD) для кожного завдання, використовуючи формули. Після цього вона обчислює оцінку та стандартне відхилення для всього проекту, а також 95% довірчий інтервал (CI) на основі цих значень. Нарешті, вона надрукує значення мінімального та максимального CI для проекту.
 
 
