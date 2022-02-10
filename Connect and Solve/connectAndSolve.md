I couldn't figure out for the life of me why were my blocks despawning and spawning again, rather than getting stacked.

```swift
let block = Block()

func blockTheGap() {
    for i in 1 ... 2 {
        world.place(block, atColumn: 2, row: 2)
    }
}

func moveForward(times: Int) {
    for i in 1 ... times {
        moveForward()
    }
}

func turnAround() {
    turnLeft()
    turnLeft()
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

blockTheGap()
for i in 1 ... 3 {
    solveRow()
}
```

Until I tried to stick the variable, inside of the repeating code... and for some reason that worked.

```swift
func blockTheGap() {
    for i in 1 ... 2 {
        let block = Block()
        world.place(block, atColumn: 2, row: 2)
    }
    
    let block = Block()
    world.place(block, atColumn: 4, row: 2)
    
    for i in 1 ... 2 {
        let block = Block()
        world.place(block, atColumn: 6, row: 2)
    }
}

func moveForward(times: Int) {
    for i in 1 ... times {
        moveForward()
    }
}

func turnAround() {
    turnLeft()
    turnLeft()
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

blockTheGap()
for i in 1 ... 3 {
    solveRow()
}
```
I still don't understand why... or sort of do. Before I was moving the same block from one place to another, and then I was creating new blocks each time.
But I'm not 100% sure why.
