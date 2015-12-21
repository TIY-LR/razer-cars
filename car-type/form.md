---
layout: page
title: Car Type Form
order: 2
---

At Razer Cars, we have a variety of different car makes and models that we stock.
Because of this, at any time, we need to be able to add new or modify existing makes and models to our ever growing list of offerings.

## User Stories

* A user can create a new Car Type
* A user edit an existing Car Type

## Design

Our designer has sent in a rough mock up of this page:

![Car Type Form]({{ site.baseurl }}public/cars-form.png)

## Acceptance Tests

```js
// tests/acceptance/car-type/list-test.js
import { test } from 'qunit';
import moduleForAcceptance from 'razer-cars/tests/helpers/module-for-acceptance';

moduleForAcceptance('Acceptance | car-type/form', {
  beforeEach() {
    login();
  },
});

test('visiting /cars shows all car-types', function(assert) {
  visit('/cars');

  andThen(function() {
    assert.equal(currentURL(), '/cars');
  });
});

test('User can see a list of car types', function(assert) {
  visit('/cars');

  andThen(function() {
    let items = findWithAssert('.car-type-list-item');
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
