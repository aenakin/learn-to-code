Oh boy... this looks like a mess.

```swift
extension Expert {
    func turnLock(up: Bool, numberOfTimes: Int) {
        if up == true {
            for i in 1 ... numberOfTimes {
                turnLockUp()
            }
        } else {
            for i in 1 ... numberOfTimes {
                turnLockDown()
            }
        }
        
    }
}

extension Character {
    func turnAround() {
        turnLeft()
        turnLeft()
    }
    func moveAndCollect(numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            if !isBlocked {
                moveForward()
            } else if !isBlockedRight {
                turnRight()
            } else if !isBlockedLeft{
                turnLeft()
            } else {
                turnAround()
            }
            if isOnGem {
                collectGem()
            }
        }
    }
    func moveForward(numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            moveForward()
        }
        
    }
    
    func moveForwardAndCollectTwice(numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            moveForward(numberOfTimes: 2)
            turnRight()
            moveForward(numberOfTimes: 2)
            collectGem()
            turnAround()
            moveForward(numberOfTimes: 2)
            turnRight()
        }
    }
}
//character moves
character.moveAndCollect(numberOfTimes: 18)
//expert brings up blue platform
expert.turnLeft()
expert.turnLock(up: true, numberOfTimes: 4)
//character moves
character.moveAndCollect(numberOfTimes: 2)
character.turnAround()
character.moveForward()
character.turnLeft()
// expert brings down blue platform
expert.turnLock(up: false, numberOfTimes: 3)
//character moves
character.moveAndCollect(numberOfTimes: 6)
//expert brings up orange platform
expert.turnLeft()
expert.turnLock(up: true, numberOfTimes: 1)
//expert brings up purple platform
expert.turnLeft()
expert.turnLock(up: true, numberOfTimes: 1)
//expert brings up green platform
expert.turnLeft()
expert.turnLock(up: true, numberOfTimes: 1)
//character clears bottom row
character.moveForwardAndCollectTwice(numberOfTimes: 2)
character.moveForward(numberOfTimes: 2)
character.collectGem()
character.turnAround()
character.moveForward()
//expert brings up green platform
expert.turnLock(up: true, numberOfTimes: 3)
//character takes last gem
character.turnLeft()
character.moveForward()
character.collectGem()
```

There's prooooobably a simpler way to achieve the same end result, but I haven't yet figured it out.
