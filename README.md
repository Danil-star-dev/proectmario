# proectmario

import pygame

W = 1600
H = 1000 
WHITE = (255, 255, 255)
GREEN = (0, 255, 25)
isJump = False
jumpCount = 10
 
pygame.init()
sc = pygame.display.set_mode((W, H))
 
# координаты и радиус круга
x = 100
y = 700


while 1:
    sc.fill(WHITE)
    pygame.draw.rect(sc, GREEN, (x, y, 40, 60))
 
    pygame.display.update()
 
    for i in pygame.event.get():
        if i.type == pygame.QUIT:
            exit()
        elif i.type == pygame.KEYDOWN:

            if i.key == pygame.K_a and x > 60:
                x -= 30

            if i.key == pygame.K_d and x < 1540:
                x += 30
            
            while jumpCount != 0:
            
            if i.key == pygame.K_SPACE and y > 60:
                isJump = True
            
                if jumpCount >= -10:
                    if jumpCount < 0:
                        y += (jumpCount**2) / 2
                    else:
                        y -= (jumpCount**2) / 2
                    jumpCount -= 1
                    pygame.display.update
                else:
                        isJump = False
                        jumpCount = 10
        pygame.display.update
