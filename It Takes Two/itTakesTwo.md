See, I am not sure if it matters how do you get to the end result, as long as you get there. I mean, I do know that you want to make your code as concise
and legible as you can, right? That way it's easier to follow for yourself and others, and easier to debug for example. Or easier to build up on it, or it
saves battery life, or memory, or... yeah.

But how do you know if you are following this principle? Like what determines it? The amount of lines? The amount of actions to perform?

I'm sure that there's simpler ways to get to the end result in this task, than this:

```swift
//variables to define gem and switch count
var gemCount = 0
var switchCount = 0

//defines expert behaviour
extension Expert {
    func moveAndTurn() {
        turnLeft()
        for i in 1 ... 3 {
            moveForward()
        }
        turnRight()
        for i in 1 ... 2 {
            moveForward()
        }
        turnLeft()
        for i in 1 ... 2 {
            turnLockDown()
        }
        turnRight()
        for i in 1 ... 2 {
            moveForward()
        }
        turnRight()
        for i in 1 ... 6 {
            moveForward()
        }
        turnRight()
        for i in 1 ... 2 {
            moveForward()
        }
        turnLeft()
        turnLockUp()
    }
}
//defines character behaviour
extension Character {
    func moveAndCollect() {
        if !isBlocked {
            moveForward()
            if isOnGem {
                collectGem()
                gemCount += 1
            } else if isOnClosedSwitch {
                toggleSwitch()
                switchCount += 1
            }
        } 
    }
}
//code
expert.moveAndTurn()
while !character.isOnOpenSwitch {
    character.moveAndCollect()
}
```

But is this bad? Or wrong? In the end it does what it needs to do.
