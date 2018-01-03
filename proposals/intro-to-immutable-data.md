# 99 Immutable Drinks On the Wall

Inspired by this [tweet](https://twitter.com/kyleshevlin/status/937196906345676800).

## Abstract

Alongside the renaissance of functional programming, immutable data structures are experiencing a revival, so it's important to understand what they are and the pros and cons of using them. One of the challenges to learning this paradigm is how counterintuitive it is. Humans experience the world as mutable. Things change by mutations, both large and small. So let's learn what immutable data is by reimagining common experiences done immutably, like having dinner and drinks with friends.

## Details

Immutable data means that we cannot perform any direct changes on that data. So how do we change it to reflect updates? We make a copy, merge our update, and return a whole new data structure to our app. How can we turn this into a metaphor so we can quickly recognize the difference in our code?

Imagine having a glass of water. Each time a take a drink, we might say that I mutate the quantity of water. Something like:

```javascript
let water = 100
let gulp = 10

water -= gulp

console.log(water) // 90
```

Another way to think of this is that gulp is an 'action' that reduces our water by a certain amount and returns the new amount:

```javascript
let initialState = {
  water: 100
}

const update = (state, action) => {
  switch (action.type) {
    case 'GULP':
      return { ...state, water: state.water - 10 }

    default:
      return state
  }
}

const newState = update(initialState, 'GULP')

console.log(newState.water) // 90
```

While it might might seem a lot of extra work to do it this way (and you're not wrong about that), there are a lot of benefits of always returning a new glass, I mean, state object. Namely, our state becomes a pure function which is both easy to memoize and to test, making our apps more performant and robust.
