Nothing to add.

```swift
let expert = Expert()
world.place(expert, facing: .south, atColumn: 1, row: 8)
extension Expert {
    func turnAround() {
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
    func moveForwardAndCollect(numberOfTimes: Int) {
        for i in 1 ... numberOfTimes {
            if isOnGem {
                collectGem()
            }
            if !isBlocked {
                moveForward()
            } 
        }
    }
}

expert.moveForwardAndCollect(numberOfTimes: 4)
expert.turnLock(up: false, numberOfTimes:1)
expert.turnLeft()
expert.moveForwardAndCollect(numberOfTimes: 4)
expert.turnLock(up: true, numberOfTimes:1)
expert.turnRight()
expert.moveForwardAndCollect(numberOfTimes: 5)
