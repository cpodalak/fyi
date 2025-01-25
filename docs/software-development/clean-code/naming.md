---
slug: clean-code-naming
title: Naming
tags: [clean-code]
sidebar_position: 3
---

Naming a variable or module or function is the hardest job, especially when you realize how incredibly important it is :satisfied:

### TL;DR
> - Use descriptive names.
> - Use adjectives to clarify.
> - Be specific about actions.
> - Describe object in class names.
> - Avoid slang/abbreviations.
> - Use meaningful distinctions.
> - Choose pronounceable and searchable names.
> - Use consistent terminology.

### **How to name things correctly?**

#### **Variables & Constants**

| **Guideline**     | **Bad** | **Good**                                      |
|---------------------------------------------------------------------|----------------------------------|---------------------------------------------------------------------------------------|
| For value as object                                                    | `x`, `data`, `lst`, `cfg`       | `user`, `database_element`, `order_list`, `config_settings`                           |
| For value as number or string                                          | `n`, `s`, `ms`, `mt`            | `max_speed`, `min_temperature`, `name`, `age`                                         |
| For value as boolean                                                  | `status`, `perm`, `auth`        | `has_permission`, `is_authenticated`, `is_active_user`                                |
| Add adjectives to add details without introducing redundancy      | `count`, `order_count`          | `active_user_count`, `completed_order_count`                                          |

#### **Functions/Methods**  
| **Guideline**     | **Bad** | **Good**                                      |
|---------------------------------------------------------------------|----------------------------------|---------------------------------------------------------------------------------------|
| Functions that perform operations                                  | `do_send()`, `config_load()`    | `send_response()`, `load_configuration()`                                             |
| Functions that return boolean values                               | `check_user()`, `license_check()`| `is_user_valid()`, `has_valid_license()`                                              |
| Add adjectives to add details without introducing redundancy      | `fetch_users()`, `generate_report()` | `fetch_active_users()`, `generate_monthly_report()`                                |

#### **Classes**  
| **Guideline**     | **Bad** | **Good**                                      |
|---------------------------------------------------------------------|----------------------------------|---------------------------------------------------------------------------------------|
| Describe the object and provide details avoiding redundancy        | `ManagerClass`, `ProcessorClass`| `TransactionManager`, `PaymentProcessor`                                              |

#### **Generic**  
| **Guideline**     | **Bad** | **Good**                                      |
|---------------------------------------------------------------------|----------------------------------|---------------------------------------------------------------------------------------|
| Avoid slang and unclear abbreviations                              | `calcStats()`, `initDB()`       | `initialize_database()`, `calculate_statistics()`                                     |
| Make meaningful distinctions                                       | `date1`, `date2`                | `start_date`, `end_date`                                                              |
| Use pronounceable names                                            | `ttlAmt`                        | `total_amount`                                                                        |
| Use searchable names                                               | `maxRet`                        | `maximum_retries`                                                                     |
| Avoid mental mappings                                              | `i`, `j`, `k`                   | `index`, `count`                                                                      |
| Don’t be overly clear                                              | `calculate_the_discount_amount()`| `calculate_discount()`                                                                |
| Pick one word per concept                                          | `get_data()`, `retrieve_data()` | `fetch_data()`                                                                        |
