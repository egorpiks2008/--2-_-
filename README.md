from pygame import *
from random import randint
player_speed=5
window=display.set_mode((700,500))
display.set_caption('pin-pong')
background=transform.scale(image.load('101800_O.jpg'),(700,500))
finish=False
game=True


class GameSprite(sprite.Sprite):
    def __init__(self, player_image, player_x, player_y,size_x,size_y, player_speed,):
        super().__init__()
        self.image = transform.scale(image.load(player_image), (size_x,size_y))
        self.speed = player_speed

        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
    def reset(self):
        window.blit(self.image, (self.rect.x, self.rect.y))

finish=False
game=True
while game:
    
    for e in event.get():
        if e.type ==QUIT:
            game=False
    if finish !=True:
        window.blit(background,(0,0))

    display.update()
