Man, why is this so hard?

I wanted to include everything I have learned up until now into the code, no shortcuts! How else am I going to learn?

I started with making sure that I was moving correctly.

```swift
func moveCollectToggle() {
    if !isBlocked  {
        moveForward()
        if isOnGem {
            collectGem()
        } else if isOnClosedSwitch {
            toggleSwitch()
        }
    } else if isBlocked {
        turnLeft()
        turnLeft()
    }
}

purplePortal.isActive = false
while true {
    moveCollectToggle()
}
```

Okay great, we are moving. The portals is turning off... Now how do I turn them back on, so I can finish the puzzle on the other side of the portal?

*Hmmm*

Aha!

```swift
    } else if isBlocked {
        purplePortal.isActive = true
        turnLeft()
        turnLeft()
    }
```

Now when we are at the end of the row the portals will be activated again! Genius.

Wait... No, when I turn around it's turning off again... *sigh*

There's gotta be a way to tell the portal to behave some other way than `true` or `false`, I mean I have seen it! I have messed with gamefiles before and
I have seen it used. How do you do that in `.swift`?

Google helped.

```swift
purplePortal.isActive = !purplePortal.isActive
```

Okay great, so now whenever I am at the end of the line in the map, I can tell it that when `isBlocked`to activate the **Portals** too.

Let's also add those variables. And let's make use of them so we're not constantly looping!

```swift
var gemCount = 0
var switchCount = 0

func moveCollectToggle() {
    if !isBlocked  {
        moveForward()
        if isOnGem {
            collectGem()
        } else if isOnClosedSwitch {
            toggleSwitch()
        }
    } else if isBlocked {
        purplePortal.isActive = !purplePortal.isActive
        turnLeft()
        turnLeft()
    }
}

purplePortal.isActive = false
while !(gemCount == 7 && switchCount == 1) {
    moveCollectToggle()
}
```

Wait why am I looping all the time? This was supposed to work!

Wait a second... 

*sigh* *I forgot to add the counters*...

```swift
var gemCount = 0
var switchCount = 0

func moveCollectToggle() {
    if !isBlocked  {
        moveForward()
        if isOnGem {
            collectGem()
            gemCount += 1
        } else if isOnClosedSwitch {
            toggleSwitch()
            switchCount += 1
        }
    } else if isBlocked {
        purplePortal.isActive = !purplePortal.isActive
        turnLeft()
        turnLeft()
    }
}

purplePortal.isActive = false
while !(gemCount == 7 && switchCount == 1) {
    moveCollectToggle()
}
```

Added the counters, and like magic again, it worked!

This one... I need to drink more water, because my head is seriously hurting. I couldn't figure out for the life of me where to activate the portals on and off.

But Google saved the day this time.
