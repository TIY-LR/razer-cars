---
layout: page
title: Inventory List
order: 3
---

At Razer Cars, we need to keep track of all of the different fleets of cars out for rent.
On this Inventory List screen we'll be able to quickly see what cars are available.

## User Stories

* A user can see all existing Fleets
  - A user can see the car type information (Year, Make, Model)
  - A user can see the currently available rentals
* A user can click on an "View Rentals" link and be redirected to the Inventory Detail for a fleet

## Design

Our designer has sent in a rough mock up of this page:

![Car Type Form]({{ site.baseurl }}public/inventory-list.png)

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
