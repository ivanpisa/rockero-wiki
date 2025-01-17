# General

- [Introduction](#introduction)
- [Naming Conventions](#naming-conventions)
  - [Class naming](#class-naming)
  - [Code naming](#code-naming)
  - [Database naming](#database-naming)
- [Structure](#structure)
  - [Class structure](#class-structure)
- [Commenting](#commenting)
  - [Attributes](#attributes)
  - [Methods](#methods)
  - [Code](#code)

---

<a name="introduction"></a>

## Introduction

When writing code, it is important to keep in mind some general principles and standards that can help improve its quality and readability.

<a name="naming-conventions"></a>

## Naming Conventions

<a name="class-naming"></a>

### Class naming

| Class        | Naming                                                     | Example                                                                              |
| ------------ | ---------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| Action       | action name with "Action" suffix                           | `CreateUserAction`, `DeleteProductAction`, `UpdateCategoryAction`                    |
| Command      | command name with "Command" suffix                         | `GenerateReportCommand`, `ImportDataCommand`, `ExportDataCommand`                    |
| Controller   | singular with "Controller" suffix                          | `UserController`, `ProductController`, `CategoryController`                          |
| Data         | singular with "Data" suffix                                | `UserData`, `ProductData`, `CategoryData`                                            |
| Event        | event name with "Event" suffix                             | `UserCreatedEvent`, `OrderCreatedEvent`, `OrderShippedEvent`                         |
| Exception    | singular with "Exception" suffix                           | `ValidationException`, `NotFoundException`, `DuplicateEntryException`                |
| Interface    | adjective/noun without suffix                              | `Loggable`, `Configurable`, `Exportable`                                             |
| Job          | job name with "Job" suffix                                 | `SendEmailJob`, `ProcessPaymentJob`, `GenerateReportJob`                             |
| Mail         | mail name without suffix                                   | `InvoicePaid`, `OrderShipped`, `PasswordReset`                                       |
| Middleware   | middleware name without suffix                             | `Authentication`, `RateLimit`, `Cors`                                                |
| Model        | singular without suffix                                    | `User`, `Product`, `Category`                                                        |
| Notification | notification name without suffix                           | `InvoicePaid`, `OrderShipped`, `PasswordReset`                                       |
| Observer     | singular model name with "Observer" suffix                 | `UserObserver`, `ProductObserver`, `CategoryObserver`                                |
| Policy       | singular model name with "Policy" suffix                   | `UserPolicy`, `ProductPolicy`, `CategoryPolicy`                                      |
| Provider     | provider name with "Provider" suffix                       | `PaymentProvider`, `StorageProvider`, `EmailProvider`                                |
| Request      | method name with singular model name with "Request" suffix | `StoreUserRequest`, `UpdateProductRequest`, `DestroyCategoryRequest`                 |
| Rule         | rule name without suffix                                   | `ValidPhoneNumber`, `ValidBankAccount`, `Uppercase`                                  |
| Scope        | scope name with "Scope" suffix                             | `ActiveScope`, `NewScope`, `TrendingScope`                                           |
| Support      | support name without suffix                                | `OpeningHours`, `Cart`, `Table`                                                      |
| Trait        | adjective/prefix "with" without suffix                     | `Sortable`, `Searchable`, `Filterable`, `WithForm`, `WithSorting`, `WithFileUploads` |

<a name="code-naming"></a>

### Code naming

| Entity         | Naming                           | Example                                             |
| -------------- | -------------------------------- | --------------------------------------------------- |
| Method         | camelCase                        | `store`, `massDestroy`, `run`                       |
| Model Property | snake_case                       | `is_active`, `created_at`                           |
| Class Property | camelCase                        | `$isActive`, `$createdAt`                           |
| Variable       | camelCase                        | `$isActive`, `$createdAt`                           |
| Route          | lowercase - plural               | `users`, `products`, `categories`                   |
| Route name     | snake_case - with 'dot' notation | `users.show`, `products.index`, `categories.create` |

<a name="database-naming"></a>

### Database naming

| Entity       | Naming                                              | Example                                |
| ------------ | --------------------------------------------------- | -------------------------------------- |
| Table        | snake_case - plural                                 | `users`, `products`, `categories`      |
| Pivot table  | snake_case - singular model names alphabetically    | `category_product`, `order_user`       |
| Table column | snake_case - without table prefix                   | `title`, `price`, `description`        |
| Primary key  | id                                                  | `id`                                   |
| Foreign key  | snake_case - singular model name with "\_id" suffix | `user_id`, `product_id`, `category_id` |

<a name="structure"></a>

## Structure

<a name="class-structure"></a>

### Class structure

When organizing code in the class, it is best to follow this order:

- **Traits**
- **Constants**
- **Static properties**
- **Properties**
- **Static methods**
- **Methods**
- **Abstract methods**

It is also important to order each category by level in the following way:

- **public**
- **protected**
- **private**

```php
use Trait;

const FOO = 1;

public static int $a;

public int $b;
protected int $c;
private int $d;

public static function methodA() {}

public function methodB() {}
protected function methodC() {}
private function methodD() {}

abstract public function methodE() {}
```

<a name="commenting"></a>

## Commenting

Well-written comments elevate the readability and understanding of code, serving as valuable documentation for future developers who may need to understand it or modify it.

However, don't forget that readeable and understandable code is important in general - comments serve as additional support and they boost quality to the next level.

<a name="attributes"></a>

### Attributes

When declaring native attributes in Laravel, such as `$fillable`, you can omit comments and type hints since these properties will not be never accessed directly.

```php
protected $fillable = [];
```

Custom attributes should be accompanied by a type hint and also supplemented with comments when the name is not sufficiently self-explanatory.

```php
public int $clickCount = 0;

/**
 * Count represents the number of clicks.
 */
public int $count = 0;
```

<a name="methods"></a>

### Methods

You should provide descriptive comments to every method in the codebase.

```php
/**
 * Display a listing of the resource.
 */
public function index()
{
  //
}
```

<a name="code"></a>

### Code

You should provide descriptive comments to every part of the code that looks unclear, such as many statements.
