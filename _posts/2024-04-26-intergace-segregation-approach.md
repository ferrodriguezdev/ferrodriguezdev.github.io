---
layout: post
title: Interface segregation approach
date: '2024-04-26T00:00:00.000-05:00'
author: Fernando Rodriguez
tags:
---


I guess this is an unpopular opinion, but there are two things I consider before creating an interface.

I don't create an interface if I only have one implementation in the domain layer initially. I always extract it when I
have a second one. It doesn't take much time and effort, and I avoid ending up with a long list of interfaces
implemented only once.

I don't necessarily have a method per interface. Instead, I prefer to delegate the responsibility in the implementation
when the time comes, by doing something like:

```java
public interface UserRepository {
  List<User> findAll();

  void save(final User user);
}
```

```java
public interface DBUserService implements UserRepository {
  @Override
  public List<User> findAll() {
  }

  @Override
  public void save(final User user) {
    throw new UnsupportedOperationException();
  }
}
```

All this, as long as the responsibility remains in the user repository. Otherwise, it would make sense to create a new
repository with its own actions.
