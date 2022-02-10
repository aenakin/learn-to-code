Cool we can place more stuff in the world now.

We were supposed to only place blocks, but I wanted to try if you could place gems too (spoiler alert: you can).

```swift
let block = Block()
let gem = Gem()

world.place(block, atColumn: 3, row: 3)
world.place(gem, atColumn: 3, row: 3)

func moveAndCollect() {
        if !isBlocked {
            jump()
            if isOnGem {
                collectGem()
            } else if isOnClosedSwitch {
                toggleSwitch()
            }
        } else if !isBlockedLeft {
            turnLeft()
        } else {
            turnRight()
        }
    }

while !isOnOpenSwitch {
    moveAndCollect()
}
```

Pretty simple setup, but it was fun to come up with the entire code by memory. I tend to practice typing the entire thing, intead of using shortcuts,
just to remember what is it that I'm doing.
