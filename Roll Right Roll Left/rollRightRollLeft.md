This is probably the level that I struggled the most with, as is to be expected from the final chapter.

I went through various itinerations of the code, wondering why wasn't it working as I was expecting it to.


```Swift
func navAround() {
    if !isBlocked {
        if isOnGem {
            collectGem()
        }else if isOnClosedSwitch {
            toggleSwitch()
        }
    moveForward()
} else if isBlockedLeft && isBlocked {
    turnRight()
} else {
    turnLeft()
}
}
while !isOnOpenSwitch {
    navAround()
}
```

Until it dawned on me that I needed a parameter that would check if I was on a gem `isOnGem` or a switch `isOnClosedSwitch` before I moved forward `moveForward`.

Therefore:

```Swift
func navAround() {
    if !isBlocked {
        while isOnGem || isOnClosedSwitch {
            if isOnGem {
                collectGem()
            }else if isOnClosedSwitch {
                toggleSwitch()
            }
        }
        moveForward()
    } else if isBlockedLeft && isBlocked {
        turnRight()
    } else {
        turnLeft()
    }
}
while !isOnOpenSwitch {
    navAround()
}
```

I know it's silly, but I was so stocked for having figured this out. It seriously took me so long to try and understand why it wasn't working,
that I had to take a break and go for a walk, and come back to it. 

After some trial and error, voilá! Like magic.

Time to tackle part 2 of the game.
