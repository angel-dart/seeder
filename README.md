# angel_seeder

[![version 1.0.1](https://img.shields.io/badge/pub-1.0.1-brightgreen.svg)](https://pub.dartlang.org/packages/angel_seeder)
[![build status](https://travis-ci.org/angel-dart/seeder.svg?branch=master)](https://travis-ci.org/angel-dart/seeder)

Straightforward data seeder for Angel services.
This is an almost exact port of [feathers-seeder](https://github.com/thosakwe/feathers-seeder),
so its documentation should almost exactly match up here.
Fortunately for us, I was also the one who made `feathers-seeder`, so if you ever need assistance,
come to me. 

# Example
```dart
var app = new Angel()..use('/todos', new TodoService());

await app.configure(seed(
    'todos',
    new SeederConfiguration<Todo>(delete: false, count: 10, template: {
        'text': (Faker faker) => 'Clean your room, ${faker.person.name()}!',
        'completed': false
    })));
```