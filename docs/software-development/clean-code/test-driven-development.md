---
slug: test-driven-development
title: Test Driven Development
tags: [clean-code]
sidebar_position: 7
---

# Test Driven Development (TDD)

### The 3 laws of TDD
>First Law - *"Don't write any production code until you have a test that proves it's needed and currently fails."*
>

>Second Law - *"Don't over-engineer your unit tests. Write only the code necessary to demonstrate the failure. If the test doesn't even compile, it's considered a failure"*
>

>Third Law - *"Don't write more production code than is sufficient to pass the currently failing test."* 
>

### The essence of TDD can be summarized in the following steps:

1. **Write a Test:** Write a test for the smallest possible functionality you want to add.
2. **Run the Test:** Run the test to ensure it fails (since the functionality hasn’t been implemented yet).
3. **Write Code:** Write the minimum amount of code needed to pass the test.
4. **Run the Test Again:** Ensure the test passes.
5. **Refactor:** Clean up the code while ensuring the test still passes.
6. **Repeat:** Move on to the next piece of functionality.

This cycle is often referred to as the **Red-Green-Refactor** loop:

1. **Red:** Write a test and watch it fail.
2. **Green:** Write just enough code to make the test pass.
3. **Refactor:** Improve the code without changing its behavior.

## Common Pitfalls in TDD

- **Skipping the Refactoring Step:** Neglecting to refactor can lead to messy, unmaintainable code.
- **Writing Large Tests:** Focus on small, incremental tests. Each test should cover a specific functionality.
- **Overtesting:** Avoid testing trivial code, such as simple getters and setters.
- **Ignoring Test Failures:** Always address test failures immediately to maintain trust in the test suite.
- **Neglecting Design Principles:** While focusing on passing tests, don’t compromise on design best practices.



In my experience, TDD is a powerful approach when you need to ensure your code is reliable and easy to maintain, especially for complex requirements. However, it's not always the best fit for quick experiments.

Following TDD too rigidly can sometimes slow you down and make things more complicated than they need to be. Developer need to flex the steps a bit to speed up development while still enjoying benefits of Test-Driven Development(TDD).