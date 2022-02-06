Fors the last chapter of the first part on the 2nd course, I wanted to write a function from scratch, instead of copy pasting from previous exercises.
Just to refresh my memory, and to learn I suppose.

The only thing we were given this exercise was our **constant** `totalGems`, which is a randomly generated number from 1 to 12 based on the amount of 
**Gems** on the level.

```swift
let totalGems = randomNumberOfGems
```

Okay! Cool. Let's write something.

First I had to make sure that the `func` was working correctly, and I wasn't getting stuck anywhere.

```Swift
func walkAndCollect() {
    if !isBlocked {
        moveForward()
        }
    } else if isBlocked && !isBlockedRight {
        turnRight()
    } else {
        turnLeft()
    }
}

while true {
    walkAndCollect()
)
```
https://user-images.githubusercontent.com/99089521/152674771-c39251b6-4c4c-4cff-80ad-4230ca99f05a.mp4

Great we're not getting stuck!

So let's collect some gems now.

let totalGems = randomNumberOfGems
var gemCounter = 0

```swift
func walkAndCollectGems() {
    if !isBlocked {
        moveForward()
        while isOnGem {
            collectGem()
        }
    } else if isBlocked && !isBlockedRight {
        turnRight()
    } else {
        turnLeft()
    }
}

while true {
    walkAndCollect()
)
```

Okay! It works, we're collecting gems.

Now the only thing left to do is to add our **variable** `collectGems`, and give a rule to only collect as many gems as there is randomly generated.

```swift
let totalGems = randomNumberOfGems
var gemCounter = 0

func walkAndCollect() {
    if !isBlocked {
        moveForward()
        while isOnGem {
            collectGem()
            gemCounter += 1
        }
        
    }else if isBlocked && !isBlockedRight {
        turnRight()
    }else {
        turnLeft()
    }
}

while gemCounter < totalGems {
    walkAndCollect()
}
```

That should do it! 

