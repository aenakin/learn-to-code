This on was a bit silly... you could literally spawn `expert`and `character`on top of the gems if you just gave them the right coordinates

```swift
let expert = Expert()
let character = Character()
world.place(expert, atColumn: 1, row: 6)
world.place(character, atColumn: 1, row: 6)
```

But that was no fun, now was it... So I decided to try and recreate everything I knew until now.

```swift
let expert = Expert()
world.place(expert, atColumn: 1, row: 6)
extension Expert {
    func turnAround() {
        turnLeft()
        turnLeft()
    }
    func moveForward(numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            moveForward()
        }
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

expert.collectGem()
expert.turnLeft()
expert.moveForward(numberOfTimes: 1)
expert.turnLock(up: true, numberOfTimes: 1)
expert.turnRight()
expert.moveForward(numberOfTimes: 5)
expert.turnRight()
expert.moveForward()
expert.collectGem()
expert.turnAround()
expert.moveForward(numberOfTimes: 2)
expert.turnLock(up: true, numberOfTimes: 1)
expert.turnRight()
expert.moveForward(numberOfTimes: 7)
expert.collectGem()
```

I think I could have automated the movement more, but I was happy with this.
