import random

def play_game():
    choices = {'к': 'камень', 'н': 'ножницы', 'б': 'бумага'}
    scores = {'player': 0, 'computer': 0, 'draws': 0}

    print("Добро пожаловать в игру 'Камень, ножницы, бумага'!")
    print("Выберите вариант: к (камень), н (ножницы), б (бумага)")
    print("Для выхода введите 'выход'")

    while True:

        player_input = input("\nВаш выбор (к/н/б) или 'выход': ")

        if player_input == 'выход':
            break

        if player_input not in choices:
            print("Неверный ввод! Используйте: к, н, б или 'выход'.")
            continue

        player_choice = choices[player_input]
        print(f"Вы выбрали: {player_choice}")

   
        computer_choice = random.choice(list(choices.values()))
        print(f"Компьютер выбрал: {computer_choice}")


        if player_choice == computer_choice:
            result = "Ничья!"
            scores['draws'] += 1
        elif (player_choice == 'камень' and computer_choice == 'ножницы') or \
             (player_choice == 'ножницы' and computer_choice == 'бумага') or \
             (player_choice == 'бумага' and computer_choice == 'камень'):
            result = "Вы выиграли!"
            scores['player'] += 1
        else:
            result = "Компьютер выиграл!"
            scores['computer'] += 1

        print(result)
        print(f"Счёт: Вы {scores['player']} — Компьютер {scores['computer']} — Ничьи {scores['draws']}")


    print("\nИтоговый счёт:")
    print(f"Вы: {scores['player']}")
    print(f"Компьютер: {scores['computer']}")
    print(f"Ничьи: {scores['draws']}")
    print("Спасибо за игру!")


play_game()
