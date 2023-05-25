# Pygame Touchscreen Slideshow Project

A simple slideshow project using Pygame and a touchscreen on a Raspberry Pi.

## Step 1: Create a Directory for Images

Open a terminal and create a directory for your images.

```bash
mkdir ~/artworks
```

Download images into this directory that you want to do the slideshow with.  

##Step 2: Pygame Script

Create a new python file:
```bash
nano slideshow.py
```

Paste the following: 
```python3
import pygame
import os
import glob

# Initialize Pygame
pygame.init()

# Set the size of the Pygame window to match the size of your display
screen = pygame.display.set_mode((800, 480))  # Adjust this to match your display's resolution

# List of images
images = glob.glob("/home/pi/artworks/*.jpg")  # Adjust this to match the path to your images and file type
images.sort()

# Image index
index = 0

# Load the first image
img = pygame.image.load(images[index])

running = True

while running:
    # Clear the screen
    screen.fill((0, 0, 0))
    
    # Draw the image
    screen.blit(pygame.transform.scale(img, (800, 480)), (0, 0))  # Adjust the dimensions to match your display's resolution
    
    # Swap buffers
    pygame.display.flip()

    # Event handling
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False
        elif event.type == pygame.MOUSEBUTTONDOWN:
            index += 1
            if index >= len(images):
                index = 0
            img = pygame.image.load(images[index])

pygame.quit()
```

Press Ctrl+X, then Y, and finally Enter to save and exit the file.

###Step 3: Run the slideshow

```bash
python3 slideshow.py
```

