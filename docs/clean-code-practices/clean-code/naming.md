---
slug: clean-code-naming
title: Naming
tags: [clean-code]
sidebar_position: 3
---

Naming is a crucial aspect of writing clean code. It helps make your code more readable and understandable without requiring readers to dive into the details. Let's explore some guidelines.

### **Why do names matter?**

- Names allow readers to understand your code without going through it in detail.

### **Name Casing**

- **snake_case:** use for variables, functions and methods.
- **camelCase:** use for variables, functions and methods.
- **PascalCase:** use for classes.
- **kebab-case:** use for custom HTML or XML elements.


### **How to name things correctly?**

| **Category**    | **Guideline**     | **Bad** | **Good**                                      |
|---------------------------|---------------------------------------------------------------------|----------------------------------|---------------------------------------------------------------------------------------|
| **Variables & Constants** | Value as object                                                    | `x`, `data`, `lst`, `cfg`       | `user`, `database_element`, `order_list`, `config_settings`                           |
|                           | Value as number or string                                          | `n`, `s`, `ms`, `mt`            | `max_speed`, `min_temperature`, `name`, `age`                                         |
|                           | Value as boolean                                                  | `status`, `perm`, `auth`        | `has_permission`, `is_authenticated`, `is_active_user`                                |
|                           | Add adjectives to add details without introducing redundancy      | `count`, `order_count`          | `active_user_count`, `completed_order_count`                                          |
| **Functions/Methods**     | Functions that perform operations                                  | `do_send()`, `config_load()`    | `send_response()`, `load_configuration()`                                             |
|                           | Functions that return boolean values                               | `check_user()`, `license_check()`| `is_user_valid()`, `has_valid_license()`                                              |
|                           | Add adjectives to add details without introducing redundancy      | `fetch_users()`, `generate_report()` | `fetch_active_users()`, `generate_monthly_report()`                                |
| **Classes**               | Describe the object and provide details avoiding redundancy        | `ManagerClass`, `ProcessorClass`| `TransactionManager`, `PaymentProcessor`                                              |
| **Generic Naming Guidelines** |                                                               |                                  |                                                                                       |
|                           | Avoid slang and unclear abbreviations                              | `calcStats()`, `initDB()`       | `initialize_database()`, `calculate_statistics()`                                     |
|                           | Make meaningful distinctions                                       | `date1`, `date2`                | `start_date`, `end_date`                                                              |
|                           | Use pronounceable names                                            | `ttlAmt`                        | `total_amount`                                                                        |
|                           | Use searchable names                                               | `maxRet`                        | `maximum_retries`                                                                     |
|                           | Avoid mental mappings                                              | `i`, `j`, `k`                   | `index`, `count`                                                                      |
|                           | Don’t be overly clear                                              | `calculate_the_discount_amount()`| `calculate_discount()`                                                                |
|                           | Pick one word per concept                                          | `get_data()`, `retrieve_data()` | `fetch_data()`                                                                        |
