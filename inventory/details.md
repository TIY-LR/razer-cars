---
layout: page
title: Inventory Details
order: 4
---

At Razer Cars, we need to keep track of what cars are on the lot ready to be rented, or which ones have probably been stolen at this point.
We want to be able to manage this for a car fleet from a single screen.
This screen will allow us to see what the status of our current fleet and rentals are, rent out cars (if any are available), and return cars back to the lot.

## User Stories

* A user can see the total supply for the current fleet
* A user can see the cars available for rent in the current fleet (total supply - active rentals)
* A user can see the rental dates for current active rents
* A user can click on "Quick Rent" to check out a car from the fleet
  - "Available for Rent" should decrease by one
  - New item is added to "Current Rentals"
* A user cannot click on "Quick Rent" if there are no available cars in the current fleet
* A user can click on "Return" to return a car from active rental back into the fleet lot
  - "Available for Rent" should increase by one
  - Item is no longer listed in "Current Rentals"

## Design

Our designer has sent in a rough mock up of this page:

![Car Type Form]({{ site.baseurl }}public/inventory-detail.png)

## Acceptance Tests

### Soon

{% comment %}
```js
// tests/acceptance/car-type/list-test.js
import { test } from 'qunit';
import moduleForAcceptance from 'razer-cars/tests/helpers/module-for-acceptance';

moduleForAcceptance('Acceptance | car-type/form', {
  beforeEach() {
    login();
  },
});

test('visiting /cars/new shows the car-type form', function(assert) {
  visit('/cars/new');

  andThen(function() {
    assert.equal(currentURL(), '/cars/new');
  });
});

test('User can car type form', function(assert) {
  visit('/cars/new');

  andThen(function() {
    let items = findWithAssert('.form-input__');
    let firstItem = items.first();

    assert.equal(items.length, 5, 'There should be five car types in the list');

    assert.equal(firstItem.find('.car-type-list-item__year').text(), '2015');
    assert.equal(firstItem.find('.car-type-list-item__name').text(), 'Ford Explorer');
  });
});

test('User can navigate to new car type form', function(assert) {
  visit('/cars');
  click('.new-btn');

  andThen(function() {
    assert.equal(currentURL(), '/cars/new');
  });
});

test('User can navigate to new car type form', function(assert) {
  visit('/cars');
  click('.car-type-list-item__edit:first');

  andThen(function() {
    assert.equal(currentURL(), '/cars/1/edit');
  });
});
```
{% endcomment %}
