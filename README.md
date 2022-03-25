### Pacman in Python with PyGame
Sarah's Notes
Movement for Enemies:

## initializing enemies:
# Create the player paddle object
VirusName=Ghost(w, b_h, "sprite.png")
monsta_list.add(VirusName)
all_sprites_list.add(VirusName)

    #default locations for Pacman and monstas
    w = 303-16 #Width
    p_h = (7*60)+19 #Pacman height
    m_h = (4*60)+19 #Monster height
    b_h = (3*60)+19 #Binky height
    i_w = 303-16-32 #Inky width
    c_w = 303+(32-16) #Clyde width

## enemy movement
# ALL GAME LOGIC SHOULD GO BELOW THIS COMMENT
returned = VirusName.changespeed(Pinky_directions,False,p_turn,p_steps,pl)
p_turn = returned[0]
p_steps = returned[1]
VirusName.changespeed(Pinky_directions,False,p_turn,p_steps,pl)
VirusName.update(wall_list,False)

    # Change the speed of the player
    def changespeed(self,x,y):
        self.change_x+=x
        self.change_y+=y

    p_turn = 0
    p_steps = 0

    pl = len(Pinky_directions)-1
    bl = len(Blinky_directions)-1
    il = len(Inky_directions)-1
    cl = len(Clyde_directions)-1

    directions array [horizontal, vertical, amt of loops to linger on this coordinate for]

## if steps less than the third value of directions, linger and increase step. once step equals it, and turn is 0 just increment turn which will change coordinates to the next ones. otherwise, make turn into 0 and 
def changespeed(self,list,ghost,turn,steps,l):
      try:
        z=list[turn][2]
        if steps < z:
          self.change_x=list[turn][0]
          self.change_y=list[turn][1]
          steps+=1
        else:
          if turn < l:
            turn+=1
          elif ghost == "clyde":
            turn = 2
          else:
            turn = 0
          self.change_x=list[turn][0]
          self.change_y=list[turn][1]
          steps = 0
        return [turn,steps]
      except IndexError:
         return [0,0]

This is a very minimal implementation of the Pacman game, having only one level and without ghosts strategy, not even with random movements (yes, the routes are programmed). However, we may improve this game in the future and everyone else interested can feel free to fork and contribute to this project.

Download installer from here: https://github.com/hbokmann/Pacman/blob/master/pacman.exe

![Pacman Game Window](https://raw.github.com/hbokmann/Pacman/master/images/pacman.jpg)


# Future development

* Fix Pacman's movement
* Ghosts moving algorithm and artificial intelligence
* Better design
* Better algorithm for the walls
* Additional levels?


Tested with [PyGame 1.9](http://pygame.org/ftp/pygame-1.9.2a0.win32-py3.2.msi ) and [Python 3.2 32bit](http://www.python.org/ftp/python/3.2.3/python-3.2.3.msi)


### Additional resources
* [Pac-Man Dossier - strategy of the ghosts movement](http://home.comcast.net/~jpittman2/pacman/pacmandossier.html)
* [HTML5 Pacman](http://arandomurl.com/2010/07/25/html5-pacman.html)
* [PyGame tutorials](http://programarcadegames.com/index.php?lang=en)
* [How To Write a Pacman Game in JavaScript](http://www.masswerk.at/JavaPac/pacman-howto.html)
* [Original Pacman game](http://originalpacman.com/)
