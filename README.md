# Extended-Project
import random

#variables
WIDTH = 1036
HEIGHT = 800
CENTER = WIDTH/2
MIDHEIGHT = HEIGHT/2
MIDWIDTH = WIDTH/2

MATHSTARTED = False
ENGLISHSTARTED = False

Science = Actor('sciencenorm')
Science.pos = (840,200)

'''Math'''
Math = Actor('mathsnorm')
Math.pos = (518,550)

Add = Actor('addnorm')
Add.pos = (250, 250)

def draw_add():
    Add.draw()

def on_mouse_down(pos):
    global MATHSTARTED
    if Math.collidepoint(pos):
        MATHSTARTED = True
    else:
        MATHSTARTED = False

'''English'''
English = Actor('englishnorm')
English.pos = (200,200)

Spelling = Actor('spellnorm')
Spelling.pos = (500, 250)

def draw_spelling():
    Spelling.draw()

def down_mouse_on(pos):
    global ENGLISHSTARTED
    if English.collidepoint(pos):
        ENGLISHSTARTED = True 
    else:
        ENGLISHSTARTED = False

'''INTRO SCREEN'''
def draw_intro():
    English.draw()
    Math.draw()
    Science.draw()

''' Game '''
def draw():
    screen.fill(( 0, 100, 200))

    for i in range(3):
        screen.blit(images.tree, (i * images.tree.get_width(),HEIGHT - images.tree.get_height()))

    for i in range(1):
        screen.blit(images.sun1, (-200,-170))

    for i in range(4):
        screen.blit(images.cloud1, (i * images.cloud1.get_width(),50))

    for i in range(17):
        screen.blit(images.ground, (i * images.ground.get_width(),HEIGHT - images.ground.get_height()))

    if MATHSTARTED == False:
        draw_intro()

    '''Math'''
    if MATHSTARTED == True:
        screen.clear

        screen.fill(( 0, 100, 200))

        for i in range(3):
            screen.blit(images.tree, (i * images.tree.get_width(),HEIGHT - images.tree.get_height()))

        for i in range(1):
            screen.blit(images.sun1, (-200,-170))

        for i in range(4):
            screen.blit(images.cloud1, (i * images.cloud1.get_width(),50))

        for i in range(17):
            screen.blit(images.ground, (i * images.ground.get_width(),HEIGHT - images.ground.get_height()))

        draw_add()
        
    '''English'''
    if ENGLISHSTARTED == True:
        screen.clear
        
        screen.fill((0, 100, 200))

        for i in range(3):
            screen.blit(images.tree, (i * images.tree.get_width(),HEIGHT - images.tree.get_height()))

        for i in range(1):
            screen.blit(images.sun1, (-200,-170))

        for i in range(4):
            screen.blit(images.cloud1, (i * images.cloud1.get_width(),50))

        for i in range(17):
            screen.blit(images.ground, (i * images.ground.get_width(),HEIGHT - images.ground.get_height()))
            
        draw_spelling()
