# hexlet-project
import random

def is_even(num):
    """Функция проверки четности числа"""
    if num % 2 == 0:
        return True
    else:
        return False

def play_game():
    """Основная функция игры"""
    num_correct = 0
    num_incorrect = 0

    while num_correct < 3:
        num = random.randint(1, 100)
        answer = input("Является ли число {} четным? (Да/Нет) ".format(num)).lower()

        if answer == "да" and is_even(num):
            print("Правильно!")
            num_correct += 1
        elif answer == "нет" and not is_even(num):
            print("Правильно!")
            num_correct += 1
        else:
            print("Неправильно! Попробуй еще раз.")
            num_incorrect += 1

        if num_incorrect == 3:
            print("Вы допустили слишком много ошибок. Игра окончена.")
            return

    print("Вы ответили правильно на все вопросы. Игра окончена.")

play_game()
