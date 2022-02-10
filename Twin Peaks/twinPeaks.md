Actually really happy with this!

For those who have played this, they know that there's a platform you can bring up to a certain level, for your `character` to be able to loop around the two peaks,
thus the level name ***Twin Peaks***.

So once the platforms were in position, it was about making your character loop around, until the correct amount **Gems** were collected.

```swift
import Foundation

let totalGems = randomNumberOfGems
var gemCount = 0

let expert = Expert()
let character = Character()

extension Expert {
    @objc override func turnAround() {
        turnLeft()
        turnLeft()
    }
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
    @objc func turnAround() {
        turnLeft()
        turnLeft()
    }
    func jump (numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            jump()
            if isOnGem {
                collectGem()
                gemCount += 1
            }
        }
    }
    func moveForwardAndCollect() {
        jump(numberOfTimes: 6)
        turnRight()
        jump(numberOfTimes: 2)
        turnRight()
    }
}

//place expert and character
world.place(expert, facing: .north, atColumn: 0, row: 4)
world.place(character, facing: .south, atColumn: 4, row: 6)

//expert levels platforms
expert.turnLock(up: true, numberOfTimes: 2)

//character clears map
while gemCount < totalGems {
    character.moveForwardAndCollect()
}
```

Quite pleased with this result, honestly. The only thing I wish I could hone out still is the unecessary couple of steps that your `character` takes after
all the gems are collected, because it's finishing the `function`.
