from random import *

suit = ["черви", "пики", "буби", "трефы"]
cards = ["", "", "двойка", "тройка", "четверка", "пятерка", "шестерка",
"семерка", "восьмерка", "девятка", "десятка", "валет", "дама", "король", "туз"]

master_cards = cards.copy()

def card_deck(suit, cards):
    new_card_deck = []
    for c in suit:
        for q in cards[2:]:
            temp = []
            temp.append(q)
            temp.append(c)
            new_card_deck.append(temp)
    return new_card_deck 

            
new_card_deck = card_deck(suit, cards)


class Player:
    def __init__(self, name, hand, score):
        self.name = name
        self.hand = hand
        self.score = score
        
        
    def pickcard(self):
        n = 0
        if len(new_card_deck) > 26:
            while n < 26:
                temp = new_card_deck.pop(randint(0, len(new_card_deck) - n))
                self.hand.append(temp)
                n += 1
        else:
            self.hand.extend(new_card_deck)
        return self.hand
    
            
    def display_info(self):
        print(self.name, self.hand)


        

player1 = Player("Sergey", [], 0)
player2 = Player("Ivan", [], 0)

player1.pickcard()
player2.pickcard()


n = 0

while n < 26:
    print(f'Игрок {player1.name} кладет {" ".join(player1.hand[n])}\n'
    f'Игрок {player2.name} кладет {" ".join(player2.hand[n])}')
    if master_cards.index(player1.hand[n][0]) < master_cards.index(player2.hand[n][0]):
        player2.score += 1
        print(f'Раунд {n + 1} выйграл {player2.name}\n')
    elif master_cards.index(player1.hand[n][0]) > master_cards.index(player2.hand[n][0]):
        player1.score += 1
        print(f'Раунд {n + 1} выйграл {player1.name}\n')
    else:
        print(f"Раунд {n + 1} Ничья\n")
    n += 1

print(player1.score, player2.score, sep='\n')
if player1.score != player2.score:
    print(f"Победил {player1.name}" if player1.score > player2.score else f"Победил {player2.name}")
else:
    print("Ничья, Победила дружба!")
