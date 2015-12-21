---
layout: page
title: Login
order: -1
---

This application is meant to be used only by employees at Razer Cars.
So, the application should be secured (both on the front end and API) using authentication

## User Stories

* A user can login with username and password
  - OAuth2 using Ember Simple Auth and Microsoft Identity

## Design

Our designer has sent in a rough mock up of this page:

![Login Page]({{ site.baseurl }}public/login-form.png)

## Acceptance Tests

```js
// tests/acceptance/general/login-test.js
import { test } from 'qunit';
import moduleForAcceptance from 'razer-cars/tests/helpers/module-for-acceptance';

moduleForAcceptance('Acceptance | general/login');

test('guest user can visit /login', function(assert) {
  visit('/login');

  andThen(function() {
    assert.equal(currentURL(), '/login');
  });
});

test('guest user can see a blank login form', function(assert) {
  visit('/login');

  andThen(function() {
    let username = findWithAssert('[name=username]');
    let password = findWithAssert('[name=password]');

    assert.equal(username.val(), '');
    assert.equal(password.val(), '');
  });
});

test('User can login with valid credentials', function(assert) {
  visit('/login');
  fillIn('[name=username]', 'valid@example.com');
  fillIn('[name=password]', 'password1234');
  click('.login-submit-btn');

  andThen(function() {
    assert.equal(currentURL(), '/', 'User should be redirected after login');
  });
});

test('User cannot login with invalid credentials', function(assert) {
  visit('/login');
  fillIn('[name=username]', 'invalid@example.com');
  fillIn('[name=password]', 'password1234');
  click('.login-submit-btn');

  andThen(function() {
    assert.equal(currentURL(), '/login', 'User should be not redirected because they are wrong');
  });
});
```
