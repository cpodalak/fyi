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

1. **Variables & Constants**
    - by type of value
        - *object values:* describe the value.
            - don’t: x, data, lst, cfg
            - do: user, database_element, order_list, config_settings
        - *number or string values:* describe the value.
            - don't: n, s, ms, mt
            - do: max_speed, min_temperature,name, age
        - *boolean values:* Answer a true/false question.
            - don't: status, perm, auth
            - do: has_permission, is_authenticated, is_active_user
    - add adjectives to add details without introducing redundancy
        - don’t: count, order_count
        - do: active_user_count, completed_order_count

2. **Functions/Methods**
    - by functionality
        - *operation functions:* describe the operation
            - don’t: do_send(), config_load()
            - do: send_response(), load_configuration()
        - *boolean functions:* answer a true/false question
            - don’t: check_user(), license_check()
            - do: is_user_valid(), has_valid_license()
    - add adjectives to add details without introducing redundancy
            - don’t: fetch_users(), generate_report()
            - do: fetch_active_users(), generate_montly_report()
- **Classes**
    - describe the object and provide details avoiding redundancy
        - don’t: ManagerClass, ProcessorClass
            - do: TransactionManager, PaymentProcessor

### Generic Naming Guidelines

- avoid slang and unclear abbreviations
    - don’t: calcStats(), initDB()
    - do:  initialize_database(), calculate_statistics()
- make meaningful distinctions
    - don’t: date1, date2
    - do: start_date, end_date
- use pronounceable names
    - don’t: ttlAmt
    - do: total_amount
- use searchable names
    - don’t: maxRet
    - do: maximum_retries
- avoid mental mappings
    - don’t: i, j, k
    - do: index, count
- don’t be overly clear
    - don’t: calculate_the_discount_amount()
    - do: calculate_discount()
- pick one word per concept
    - don’t: get_data(), retrieve_data()
    - do: fetch_data()