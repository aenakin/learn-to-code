I think this code could be streamlined way more... but here is my thought process.

```Swift
func solveRow() {
    turnLeft()
    moveForward()
    moveForward()
    collectGem()
    turnLeft()
    turnLeft()
    moveForward()
    moveForward()
    turnLeft()
}
for i in 1 ... 4 {
    moveForward()
    if !isOnGem {
        solveRow()
    }else {
        collectGem()
    }
}
```
