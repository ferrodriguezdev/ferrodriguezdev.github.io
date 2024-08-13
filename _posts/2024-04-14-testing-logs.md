---
layout: post
title: Testing logs
date: '2024-04-14T00:00:00.000-05:00'
author: Fernando Rodriguez
tags:
---


In my experience, we often overlook the importance of logs, and this is a mistake.

There are a few things to consider, and one of them is testing logs, just as you would test the output of your services.

In Spring Boot, for instance, you can easily achieve this by using the "CapturedOutput" object, as demonstrated in the
following example:

```java
    @Test
        public void deposit_shouldLogDepositMessage(final CapturedOutput output) {
        
            final Double depositAmount = 50.00;

            accountService.deposit(userId, initialBalance, depositAmount);

            final String logOutput = output.getOut();

            Assertions.assertAll(
                    () -> Assertions.assertTrue(logOutput.contains("INFO")),
                    () -> Assertions.assertTrue(logOutput.contains(userId)),
                    () -> Assertions.assertTrue(logOutput.contains(String.valueOf(depositAmount))),
                    () -> Assertions.assertTrue(logOutput.contains(LocalDate.now().toString()))
            );
}
```
