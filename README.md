import random

def play_game():
    choices = ['камень', 'ножницы', 'бумага']
    
    print("Добро пожаловать в игру 'Камень, ножницы, бумага'!")
    print("Выберите один из вариантов: камень, ножницы, бумага")
    
    while True:
        player_choice = input("Ваш выбор: ")
        
        if player_choice not in choices:
            print("Неверный ввод! Пожалуйста, выберите: камень, ножницы или бумага.")
            continue
        
        computer_choice = random.choice(choices)
        print(f"Компьютер выбрал: {computer_choice}")
        
        if player_choice == computer_choice:
            result = "Ничья!"
        elif player_choice == 'камень' and computer_choice == 'ножницы' or player_choice == 'ножницы' and computer_choice == 'бумага' or player_choice == 'бумага' and computer_choice == 'камень':
            result = "Вы выиграли!"
        else:
            result = "Компьютер выиграл!"
        
        print(result)
        
        play_again = input("Хотите сыграть ещё раз? (да/нет): ")
        if play_again != 'да':
            print("Спасибо за игру!")
            break


play_game()
