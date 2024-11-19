import pygame

pygame.init()
screen = pygame.display.set_mode((800, 600))
pygame.display.set_caption('Side-Scrolling Game')
clock = pygame.time.Clock()
running = True

player = [100, 450, 0, 0]
isOnGround = False

def move_player():
    global isOnGround
    if keys[pygame.K_LEFT]:
        player[2] =- 5
    elif keys[pygame.K_RIGHT]:
        player[2] = 5
    else:
        player[2] = 0
        
    if isOnGround == False:
        player[3] += 1
        
    player[0]+=player[2]
    player[1]+=player[3]
    
    if player[1] > 450:
        isOnGround = True
        player[1] = 450
    
def draw_clouds():
    for x in range(100, 800, 300):
        pygame.draw.circle(screen, ( 255, 255, 255), (x, 100), 40)
        pygame.draw.circle(screen, ( 255, 255, 255), (x-50, 125), 40)
        pygame.draw.circle(screen, ( 255, 255, 255), (x+50, 125), 40)
        pygame.draw.rect(screen, (255, 255, 255), (x-50, 100, 100, 65))

def draw_trees():
    for x in range(100, 800, 300):
        pygame.draw.rect(screen, (150, 75, 0), (x+50, 200, 25, 300))
        pygame.draw.circle(screen, (100, 255, 0), (x+65, 200), 40)
        pygame.draw.circle(screen, (100, 255, 0), (x+15, 225), 40)
        pygame.draw.circle(screen, (100, 255, 0), (x+115, 225), 40)        
        
while running: #Main game loop--------------------------------------------------
    #input section--------------------------------------------------------------
    clock.tick(60)
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
           
        keys = pygame.key.get_pressed()
        #physics section----------------------------------------------------
    move_player()
        #render section-----------------------------------------------------
    screen.fill((135, 206, 235)) #sky blue background
        
    pygame.draw.rect(screen, (255, 0, 255), (player[0], player[1], 50, 50))
        
    draw_clouds() #function call
        
    draw_trees()
        
    pygame.draw.rect(screen, (150, 255, 50), (0, 500, 800, 100)) #green grass
        
    pygame.display.flip()
    
pygame.quit()
