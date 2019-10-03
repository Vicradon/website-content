---
title: How to sort an array by date value in JavaScript
date: 2019-07-14T07:00:00+02:00
description: "Find out how to sort an array of items by date value in JavaScript"
tags: js
---

Say you have an array of objects like this, which contains a set of [date objects](/javascript-dates/):

```js
const activities = [
  { title: 'Hiking', date: new Date('2019-06-28') },
  { title: 'Shopping', date: new Date('2019-06-10') },
  { title: 'Trekking', date: new Date('2019-06-22') }
]
```

You want to sort those activities by the `date` property.

You can use the `sort()` method of [`Array`](/javascript-array/), which takes a callback function, which takes as parameters 2 objects contained in the array (which we call `a` and `b`):

```js
const sortedActivities = activities.sort((a, b) => b.date - a.date)
```

When we return a positive value, the function communicates to `sort()` that the object `b` takes precedence in sorting over the object `a`. Returning a negative value will do the opposite.

The `sort()` method returns a new sorted array, but it also sorts the original array in place. Thus, both the `sortedActivities` and `activities` arrays are now sorted. One option to protect the original array from being modified is to use the `slice()` method to create a copy of the array prior to sorting, as follows:

```js
const sortedActivities = activities.slice().sort((a, b) => b.date - a.date)
```