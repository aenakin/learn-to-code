WIP

```swift
let block = Block()

func placeBlock() {
    for j in 1 ... 2 {
        for i in 1 ... 3 {
            if j == 1 || i != 2 {
                world.place(block, atColumn: i*2, row: 2)
            }
        }
    }
}

func turnAround() {
    turnLeft()
    turnLeft()
}

func moveForward(times: Int) {
    for i in 1 ... times {
        moveForward()
    }
}

func solveRow() {
    moveForward(times: 2)
    toggleSwitch()
    turnRight()
    moveForward(times: 4)
    collectGem()
    turnAround()
    moveForward(times: 4)
    turnRight()
}


placeBlock()
for i in 1 ... 3 {
    solveRow()
}

```
