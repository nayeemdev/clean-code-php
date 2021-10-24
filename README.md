# পিএইচপি তে ক্লিন কোড

## সুচিপত্র

  1. [ভূমিকা](#ভূমিকা)
  2. [ভেরিয়েবল](#ভেরিয়েবল)
     * [অর্থপূর্ণ এবং উচ্চারণযোগ্য ভেরিয়েবল নাম ব্যবহার করুন](#অর্থপূর্ণ-এবং-উচ্চারণযোগ্য-ভেরিয়েবল-নাম-ব্যবহার-করুন)
     * [একই ধরনের ভেরিয়েবলের জন্য একই শব্দভাণ্ডার ব্যবহার করুন](#একই-ধরনের-ভেরিয়েবলের-জন্য-একই-শব্দভাণ্ডার-ব্যবহার-করুন)
     * [অনুসন্ধানযোগ্য নাম ব্যবহার করুন (পর্ব ১)](#অনুসন্ধানযোগ্য-নাম-ব্যবহার-করুন-পর্ব-১)
     * [অনুসন্ধানযোগ্য নাম ব্যবহার করুন (পর্ব ২)](#অনুসন্ধানযোগ্য-নাম-ব্যবহার-করুন-পর্ব-২)
     * [ব্যাখ্যামূলক ভেরিয়েবল ব্যবহার করুন](#ব্যাখ্যামূলক-ভেরিয়েবল-ব্যবহার-করুন)
     * [নেস্টেড স্ট্রাকচার এড়িয়ে চলুন (পর্ব ১)](#নেস্টেড-স্ট্রাকচার-এড়িয়ে-চলুন-পর্ব-১)
     * [নেস্টেড স্ট্রাকচার এড়িয়ে চলুন (পর্ব ২)](#নেস্টেড-স্ট্রাকচার-এড়িয়ে-চলুন-পর্ব-২)
     * [মেন্টাল ম্যাপিং এড়িয়ে চলুন](#মেন্টাল-ম্যাপিং-এড়িয়ে-চলুন)
     * [অপ্রয়োজনীয় প্রসঙ্গ যোগ করবেন না](#অপ্রয়োজনীয়-প্রসঙ্গ-যোগ-করবেন-না)
  3. [তুলনা](#তুলনা)
     * [একই ধরনের ভেরিয়েবল এর তুলনা করুন](#একই-ধরনের-ভেরিয়েবল-এর-তুলনা-করুন)
     * [Null coalescing operator](#null-coalescing-operator)
  4. [ফাংশন](#ফাংশন)
     * [সংক্ষিপ্ত বা শর্তাধীন সংযোগের পরিবর্তে ডিফল্ট আর্গুমেন্ট ব্যবহার করুন](#সংক্ষিপ্ত-বা-শর্তাধীন-সংযোগের-পরিবর্তে-ডিফল্ট-আর্গুমেন্ট-ব্যবহার-করুন)
     * [ফাংশন আর্গুমেন্ট (2 টা আর্গুমেন্ট বা কম)](#ফাংশন-আর্গুমেন্ট-2-টা-আর্গুমেন্ট-বা-কম)
     * [ফাংশন কি কাজ করে সেই হিসেবে নামকরণ করতে হবে](#ফাংশন-কি-কাজ-করে-সেই-হিসেবে-নামকরণ-করতে-হবে)
     * [ফাংশন-শুধুমাত্র-Abstraction-এর-একটি-স্তর-হওয়া-উচিত](#ফাংশন-শুধুমাত্র-abstraction-এর-একটি-স্তর-হওয়া-উচিত)
     * [ফাংশন প্যারামিটার হিসাবে flag ব্যবহার করবেন না](#ফাংশন-প্যারামিটার-হিসাবে-flag-ব্যবহার-করবেন-না)
     * [পার্শ্বপ্রতিক্রিয়া এড়িয়ে চলুন](#পার্শ্বপ্রতিক্রিয়া-এড়িয়ে-চলুন)
     * [Global functions লেখা থেকে বিরত থাকুন](#global-functions-লেখা-থেকে-বিরত-থাকুন)
     * [Singleton pattern ব্যাবহার করবেন না](#singleton-pattern-ব্যাবহার-করবেন-না)
     * [Encapsulate conditionals](#encapsulate-conditionals)
     * [নেগেটিভ কন্ডিশনিং এড়িয়ে চলুন](#নেগেটিভ-কন্ডিশনিং-এড়িয়ে-চলুন)
     * [কন্ডিশনিং এড়িয়ে চলুন](#কন্ডিশনিং-এড়িয়ে-চলুন)
     * [ফাংশন এর মধ্যে টাইপ চেক থেকে বিরত থাকুন (পর্ব ১)](#ফাংশন-এর-মধ্যে-টাইপ-চেক-থেকে-বিরত-থাকুন-পর্ব-১)
     * [ফাংশন এর মধ্যে টাইপ চেক থেকে বিরত থাকুন (পর্ব ২)](#ফাংশন-এর-মধ্যে-টাইপ-চেক-থেকে-বিরত-থাকুন-পর্ব-২)
     * [ডেড কোড মুছে ফেলুন](#ডেড-কোড-মুছে-ফেলুন)
  5. [অবজেক্টস এবং ডেটা স্ট্রাকচার](#অবজেক্টস-এবং-ডেটা-স্ট্রাকচার)
     * [অবজেক্ট এনক্যাপসুলেশন ব্যবহার করুন](#অবজেক্ট-এনক্যাপসুলেশন-ব্যবহার-করুন)
     * [অবজেক্ট তৈরিতে private protected মেম্বার ব্যাবহার করুন](#অবজেক্ট-তৈরিতে-private-protected-মেম্বার-ব্যাবহার-করুন)
  6. [ক্লাস](#ক্লাস)
     * [Inheritanceএর থেকে Composition কে গুরুত্ব দিন](#Inheritance-এর-থেকে-Composition-কে-গুরুত্ব-দিন)
     * [ফ্লুয়েন্ট ইন্টারফেস এড়িয়ে চলুন](#ফ্লুয়েন্ট-ইন্টারফেস-এড়িয়ে-চলুন)
     * [Prefer final classes](#prefer-final-classes)
  7. [SOLID](#solid)
     * [Single Responsibility Principle (SRP)](#single-responsibility-principle-srp)
     * [Open/Closed Principle (OCP)](#openclosed-principle-ocp)
     * [Liskov Substitution Principle (LSP)](#liskov-substitution-principle-lsp)
     * [Interface Segregation Principle (ISP)](#interface-segregation-principle-isp)
     * [Dependency Inversion Principle (DIP)](#dependency-inversion-principle-dip)
  8. [পুনরাবৃত্তি করবেন না (DRY)](#পুনরাবৃত্তি-করবেন-না-dry)
  9. [অনুবাদ](#অনুবাদ)

## ভূমিকা

Software engineering principles, from Robert C. Martin's book
[*Clean Code*](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882),
adapted for PHP. এটি একটি স্টাইল গাইড নয়। এটি পিএইচপিতে পাঠযোগ্য, পুন: ব্যবহারযোগ্য এবং রিফ্যাক্টরেবল সফটওয়্যার তৈরির জন্য একটি নির্দেশিকা।

Not every principle herein has to be strictly followed, and even fewer will be universally
agreed upon. These are guidelines and nothing more, but they are ones codified over many
years of collective experience by the authors of *Clean Code*.

Inspired from [clean-code-javascript](https://github.com/ryanmcdermott/clean-code-javascript).

Although many developers still use PHP 5, most of the examples in this article only work with PHP 7.1+.

## ভেরিয়েবল

### অর্থপূর্ণ এবং উচ্চারণযোগ্য ভেরিয়েবল নাম ব্যবহার করুন

**খারাপ:**

```php
$ymdstr = $moment->format('y-m-d');
```

**ভাল:**

```php
$currentDate = $moment->format('y-m-d');
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### একই ধরনের ভেরিয়েবলের জন্য একই শব্দভাণ্ডার ব্যবহার করুন

**খারাপ:**

```php
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();
```

**ভাল:**

```php
getUser();
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### অনুসন্ধানযোগ্য নাম ব্যবহার করুন (পর্ব ১)

সাধারণত আমরা কোড লেখার থেকে বেশি পড়ে থাকি। তাই এটা গুরুত্বপূর্ণ যে আমরা যে কোড লিখব সেটা যেন রিডেবল এবং সার্চেবল হয় অর্থাৎ পড়তে এবং খুঁজে পেতে যেন সহজ হয়। আমাদের প্রোগ্রাম বোঝার জন্য অর্থবহ হওয়া ভেরিয়েবলের নাম না দিলে যারা কোড পড়বে তাঁদের বুঝতে অসুবিধা হবে। সেজন্য ভেরিয়েবল এর নাম রিডেবল এবং সার্চেবল হওয়া জরুরি।

**খারাপ:**

```php
// What the heck is 448 for?
$result = $serializer->serialize($data, 448);
```

**ভাল:**

```php
$json = $serializer->serialize($data, JSON_UNESCAPED_SLASHES | JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
```

### অনুসন্ধানযোগ্য নাম ব্যবহার করুন (পর্ব ২)

**খারাপ:**

```php
class User
{
    // What the heck is 7 for?
    public $access = 7;
}

// What the heck is 4 for?
if ($user->access & 4) {
    // ...
}

// What's going on here?
$user->access ^= 2;
```

**ভাল:**

```php
class User
{
    public const ACCESS_READ = 1;

    public const ACCESS_CREATE = 2;

    public const ACCESS_UPDATE = 4;

    public const ACCESS_DELETE = 8;

    // User as default can read, create and update something
    public $access = self::ACCESS_READ | self::ACCESS_CREATE | self::ACCESS_UPDATE;
}

if ($user->access & User::ACCESS_UPDATE) {
    // do edit ...
}

// Deny access rights to create something
$user->access ^= User::ACCESS_CREATE;
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ব্যাখ্যামূলক ভেরিয়েবল ব্যবহার করুন

**খারাপ:**

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches[1], $matches[2]);
```

**খারাপ নয়:**

এটি আরও ভাল, তবে আমরা এখনও রেজেক্সের উপর নির্ভরশীল হয়ে আছি।

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

[, $city, $zipCode] = $matches;
saveCityZipCode($city, $zipCode);
```

**ভাল:**

Naming subpatterns ব্যাবহার করে রেজেক্স এর উপর নির্ভরতা কমিয়ে আনতে পারি।

```php
$address = 'One Infinite Loop, Cupertino 95014';
$cityZipCodeRegex = '/^[^,]+,\s*(?<city>.+?)\s*(?<zipCode>\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches['city'], $matches['zipCode']);
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### নেস্টেড স্ট্রাকচার এড়িয়ে চলুন (পর্ব ১)

অনেক বেশি if-else statements আপনার কোড পড়া বা অনুসরণ করাকে কঠিন করে তুলতে পারে কাড়ন এটা বুঝতে অনেক ঝামেলা হবে। এক্ষেত্রে বিশদভাবে লেখাই ভাল(Explicit is better than implicit.)।

**খারাপ:**

```php
function isShopOpen($day): bool
{
    if ($day) {
        if (is_string($day)) {
            $day = strtolower($day);
            if ($day === 'friday') {
                return true;
            } elseif ($day === 'saturday') {
                return true;
            } elseif ($day === 'sunday') {
                return true;
            }
            return false;
        }
        return false;
    }
    return false;
}
```

**ভাল:**

```php
function isShopOpen(string $day): bool
{
    if (empty($day)) {
        return false;
    }

    $openingDays = ['friday', 'saturday', 'sunday'];

    return in_array(strtolower($day), $openingDays, true);
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### নেস্টেড স্ট্রাকচার এড়িয়ে চলুন (পর্ব ২)

**খারাপ:**

```php
function fibonacci(int $n)
{
    if ($n < 50) {
        if ($n !== 0) {
            if ($n !== 1) {
                return fibonacci($n - 1) + fibonacci($n - 2);
            }
            return 1;
        }
        return 0;
    }
    return 'Not supported';
}
```

**ভাল:**

```php
function fibonacci(int $n): int
{
    if ($n === 0 || $n === 1) {
        return $n;
    }

    if ($n >= 50) {
        throw new Exception('Not supported');
    }

    return fibonacci($n - 1) + fibonacci($n - 2);
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### মেন্টাল ম্যাপিং এড়িয়ে চলুন

ভেরিয়েবল নাম এমনভাবে লিখুন যাতে যে কোড পড়ছে তার যেন অনুবাদ করে দেখতে না হয়। এমন নাম হওয়া উচিত যেন যেকেউ দেখে বুঝে নিতে পারে।
বিশদভাবে লেখাই ভাল(Explicit is better than implicit.)।

**খারাপ:**

```php
$l = ['Austin', 'New York', 'San Francisco'];

for ($i = 0; $i < count($l); $i++) {
    $li = $l[$i];
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `$li` for again?
    dispatch($li);
}
```

**ভাল:**

```php
$locations = ['Austin', 'New York', 'San Francisco'];

foreach ($locations as $location) {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    dispatch($location);
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### অপ্রয়োজনীয় প্রসঙ্গ যোগ করবেন না

যদি আপনার class/object এর নাম দিয়ে কিছু বুঝা যায় তাহলে ওই একই নাম এই class/object এর ভেরিয়েবল এ ব্যবহার করার দরকার নেই।

**খারাপ:**

```php
class Car
{
    public $carMake;

    public $carModel;

    public $carColor;

    //...
}
```

**ভাল:**

```php
class Car
{
    public $make;

    public $model;

    public $color;

    //...
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## তুলনা

### [একই ধরনের ভেরিয়েবল এর তুলনা করুন](http://php.net/manual/en/language.operators.comparison.php)

**ভাল না:**

এখানে এই সিম্পল কম্প্যেয়ার string কে integer এ রূপান্তর করে ফেলেছে।

```php
$a = '42';
$b = 42;

if ($a != $b) {
    // The expression will always pass
}
```

এখানে `$a != $b`, `FALSE` রিটার্ন করে কিন্তু এটা `TRUE` হবে!
এখানে string `42` integer `42` এর থেকে আলাদা ধরনের/type।

**ভাল:**

এই identical comparison type এবং value তুলনা/কম্পেয়ার করে.

```php
$a = '42';
$b = 42;

if ($a !== $b) {
    // The expression is verified
}
```

এখানে `$a !== $b`, `TRUE` রিটার্ন করে।

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Null coalescing operator

Null coalescing হল নতুন অপেরেটর [PHP 7 এ যুক্ত হয়েছে](https://www.php.net/manual/en/migration70.new-features.php). The null coalescing operator `??` has been added as syntactic sugar for the common case of needing to use a ternary in conjunction with `isset()`. এটি এর প্রথম operand রিটার্ন করে যদি প্রথম operand টি exists করে এবং এটি NULL না হয়, অন্যথায় এটি দ্বিতীয় operand রিটার্ন করে।

**খারাপ:**

```php
if (isset($_GET['name'])) {
    $name = $_GET['name'];
} elseif (isset($_POST['name'])) {
    $name = $_POST['name'];
} else {
    $name = 'nobody';
}
```

**ভাল:**
```php
$name = $_GET['name'] ?? $_POST['name'] ?? 'nobody';
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## ফাংশন

### সংক্ষিপ্ত বা শর্তাধীন সংযোগের পরিবর্তে ডিফল্ট আর্গুমেন্ট ব্যবহার করুন

**ভাল না:**

এটা ভাল নয় কারণ  `$breweryName` , `NULL` হতে পারে।

```php
function createMicrobrewery($breweryName = 'Hipster Brew Co.'): void
{
    // ...
}
```

**খারাপ নয়:**

এই উদাহরণ টা বুঝতে আগের উদাহরণ থেকে সুবিধা হবে, কিন্তু এটি ভেরিয়েবলের মানকে আরও ভালভাবে নিয়ন্ত্রণ করে।

```php
function createMicrobrewery($name = null): void
{
    $breweryName = $name ?: 'Hipster Brew Co.';
    // ...
}
```

**ভাল:**

আপনি [type hinting](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration) ব্যাবহার করে এটা নিশিত করতে পারেন যে `$breweryName` কখন ও `NULL` হবে না।

```php
function createMicrobrewery(string $breweryName = 'Hipster Brew Co.'): void
{
    // ...
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন আর্গুমেন্ট (2 টা আর্গুমেন্ট বা কম)

ফাংশন এর প্যারামিটার কম করা গুরুত্বপূর্ণ কারণ এটা ফাংশন টেস্টিং সহজ করে তোলে। ৩ তার বেশি প্যারামিটার টেস্টিং কে অনেক বেশি কঠিন করে ফেলে কারণ তখন আপনার প্রতিটা আর্গুমেন্ট এর জনন অনেকগুলো করে টেস্ট কেস চিন্তা করতে হবে এবং সেগুলো হ্যান্ডেল করতে হবে।

জিরো/০ টা আর্গুমেন্ট হল আদর্শ কেস। ১ টা বা ২ টা আর্গুমেন্ট ও থিক আছে কিন্তু ২ এর অধীক হলে অবশ্যয় এভয়েড করতে হবে। সাধারণত, আপনার ফাংশন এ ২ তার বেশি আর্গুমেন্ট থাকা মানে আপনার ফাংশন টা অনেক বেশি কাজ করতেছে যেটা উচিত নয়।

**খারাপ:**

```php
class Questionnaire
{
    public function __construct(
        string $firstname,
        string $lastname,
        string $patronymic,
        string $region,
        string $district,
        string $city,
        string $phone,
        string $email
    ) {
        // ...
    }
}
```

**ভাল:**

```php
class Name
{
    private $firstname;

    private $lastname;

    private $patronymic;

    public function __construct(string $firstname, string $lastname, string $patronymic)
    {
        $this->firstname = $firstname;
        $this->lastname = $lastname;
        $this->patronymic = $patronymic;
    }

    // getters ...
}

class City
{
    private $region;

    private $district;

    private $city;

    public function __construct(string $region, string $district, string $city)
    {
        $this->region = $region;
        $this->district = $district;
        $this->city = $city;
    }

    // getters ...
}

class Contact
{
    private $phone;

    private $email;

    public function __construct(string $phone, string $email)
    {
        $this->phone = $phone;
        $this->email = $email;
    }

    // getters ...
}

class Questionnaire
{
    public function __construct(Name $name, City $city, Contact $contact)
    {
        // ...
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন কি কাজ করে সেই হিসেবে নামকরণ করতে হবে

**খারাপ:**

```php
class Email
{
    //...

    public function handle(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
// What is this? A handle for the message? Are we writing to a file now?
$message->handle();
```

**ভাল:**

```php
class Email
{
    //...

    public function send(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
// Clear and obvious
$message->send();
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন শুধুমাত্র Abstraction এর একটি স্তর হওয়া উচিত

যখন আপনার এক লেভেল এর বেশি abstraction থাকে তার মানে হল আপনার ফাংশন টা অনেক বেশি কাজ করতেছে। ফাংশন ভাগ করে লিখলে সেটা পুনরায় ব্যাবহার এবং টেস্ট করতে খুবই সুবিধা হয়।

**খারাপ:**

```php
function parseBetterPHPAlternative(string $code): void
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            // ...
        }
    }

    $ast = [];
    foreach ($tokens as $token) {
        // lex...
    }

    foreach ($ast as $node) {
        // parse...
    }
}
```

**এটাও খারাপ:**

আমরা কিছু ফাংশন এর কাজ সম্পন্ন করেছি কিন্তু `parseBetterPHPAlternative()` ফাংশন এখনো অনেক জটিল/কমপ্লেক্স এবং টেস্ট করার মত অবস্থাই নেই।

```php
function tokenize(string $code): array
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            $tokens[] = /* ... */;
        }
    }

    return $tokens;
}

function lexer(array $tokens): array
{
    $ast = [];
    foreach ($tokens as $token) {
        $ast[] = /* ... */;
    }

    return $ast;
}

function parseBetterPHPAlternative(string $code): void
{
    $tokens = tokenize($code);
    $ast = lexer($tokens);
    foreach ($ast as $node) {
        // parse...
    }
}
```

**ভাল:**

সব থেকে ভাল সমাধান হল - `parseBetterPHPAlternative()` থেকে dependency গুল আলাদা করে ফেলা।

```php
class Tokenizer
{
    public function tokenize(string $code): array
    {
        $regexes = [
            // ...
        ];

        $statements = explode(' ', $code);
        $tokens = [];
        foreach ($regexes as $regex) {
            foreach ($statements as $statement) {
                $tokens[] = /* ... */;
            }
        }

        return $tokens;
    }
}

class Lexer
{
    public function lexify(array $tokens): array
    {
        $ast = [];
        foreach ($tokens as $token) {
            $ast[] = /* ... */;
        }

        return $ast;
    }
}

class BetterPHPAlternative
{
    private $tokenizer;
    private $lexer;

    public function __construct(Tokenizer $tokenizer, Lexer $lexer)
    {
        $this->tokenizer = $tokenizer;
        $this->lexer = $lexer;
    }

    public function parse(string $code): void
    {
        $tokens = $this->tokenizer->tokenize($code);
        $ast = $this->lexer->lexify($tokens);
        foreach ($ast as $node) {
            // parse...
        }
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন প্যারামিটার হিসাবে flag ব্যবহার করবেন না

Flags আপনার ইউজার কে বুঝায় যে এই ফাংশন টা একের অধিক কাজ করতেছে, কিন্তু একটা ফাংশন একটার বেশি কাজ করা উচিত নয়। ফাংশন এর কাজ গুল আলাদা করা উচিত যদি boolean ভ্যালু এর উপর বেস করে আলাদা কাজ করে।
**খারাপ:**

```php
function createFile(string $name, bool $temp = false): void
{
    if ($temp) {
        touch('./temp/' . $name);
    } else {
        touch($name);
    }
}
```

**ভাল:**

```php
function createFile(string $name): void
{
    touch($name);
}

function createTempFile(string $name): void
{
    touch('./temp/' . $name);
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### পার্শ্বপ্রতিক্রিয়া এড়িয়ে চলুন

A function produces a side effect if it does anything other than take a value in and
return another value or values. A side effect could be writing to a file, modifying
some global variable, or accidentally wiring all your money to a stranger.

Now, you do need to have side effects in a program on occasion. Like the previous
example, you might need to write to a file. What you want to do is to centralize where
you are doing this. Don't have several functions and classes that write to a particular
file. Have one service that does it. One and only one.

The main point is to avoid common pitfalls like sharing state between objects without
any structure, using mutable data types that can be written to by anything, and not
centralizing where your side effects occur. If you can do this, you will be happier
than the vast majority of other programmers.

**খারাপ:**

```php
// Global variable referenced by following function.
// If we had another function that used this name, now it'd be an array and it could break it.
$name = 'Ryan McDermott';

function splitIntoFirstAndLastName(): void
{
    global $name;

    $name = explode(' ', $name);
}

splitIntoFirstAndLastName();

var_dump($name);
// ['Ryan', 'McDermott'];
```

**ভাল:**

```php
function splitIntoFirstAndLastName(string $name): array
{
    return explode(' ', $name);
}

$name = 'Ryan McDermott';
$newName = splitIntoFirstAndLastName($name);

var_dump($name);
// 'Ryan McDermott';

var_dump($newName);
// ['Ryan', 'McDermott'];
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Global functions লেখা থেকে বিরত থাকুন

Polluting globals is a bad practice in many languages because you could clash with another
library and the user of your API would be none-the-wiser until they get an exception in
production. Let's think about an example: what if you wanted to have configuration array?
You could write global function like `config()`, but it could clash with another library
that tried to do the same thing.

**খারাপ:**

```php
function config(): array
{
    return [
        'foo' => 'bar',
    ];
}
```

**ভাল:**

```php
class Configuration
{
    private $configuration = [];

    public function __construct(array $configuration)
    {
        $this->configuration = $configuration;
    }

    public function get(string $key): ?string
    {
        // null coalescing operator
        return $this->configuration[$key] ?? null;
    }
}
```

Load configuration and create instance of `Configuration` class

```php
$configuration = new Configuration([
    'foo' => 'bar',
]);
```

And now you must use instance of `Configuration` in your application.

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Singleton pattern ব্যাবহার করবেন না

Singleton is an [anti-pattern](https://en.wikipedia.org/wiki/Singleton_pattern). Paraphrased from Brian Button:
 1. They are generally used as a **global instance**, why is that so bad? Because **you hide the dependencies** of your application in your code, instead of exposing them through the interfaces. Making something global to avoid passing it around is a [code smell](https://en.wikipedia.org/wiki/Code_smell).
 2. They violate the [single responsibility principle](#single-responsibility-principle-srp): by virtue of the fact that **they control their own creation and lifecycle**.
 3. They inherently cause code to be tightly [coupled](https://en.wikipedia.org/wiki/Coupling_%28computer_programming%29). This makes faking them out under **test rather difficult** in many cases.
 4. They carry state around for the lifetime of the application. Another hit to testing since **you can end up with a situation where tests need to be ordered** which is a big no for unit tests. Why? Because each unit test should be independent from the other.

There is also very good thoughts by [Misko Hevery](http://misko.hevery.com/about/) about the [root of problem](http://misko.hevery.com/2008/08/25/root-cause-of-singletons/).

**খারাপ:**

```php
class DBConnection
{
    private static $instance;

    private function __construct(string $dsn)
    {
        // ...
    }

    public static function getInstance(): self
    {
        if (self::$instance === null) {
            self::$instance = new self();
        }

        return self::$instance;
    }

    // ...
}

$singleton = DBConnection::getInstance();
```

**ভাল:**

```php
class DBConnection
{
    public function __construct(string $dsn)
    {
        // ...
    }

    // ...
}
```

Create instance of `DBConnection` class and configure it with [DSN](http://php.net/manual/en/pdo.construct.php#refsect1-pdo.construct-parameters).

```php
$connection = new DBConnection($dsn);
```

And now you must use instance of `DBConnection` in your application.

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Encapsulate conditionals

**খারাপ:**

```php
if ($article->state === 'published') {
    // ...
}
```

**ভাল:**

```php
if ($article->isPublished()) {
    // ...
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### নেগেটিভ কন্ডিশনিং এড়িয়ে চলুন

**খারাপ:**

```php
function isDOMNodeNotPresent(DOMNode $node): bool
{
    // ...
}

if (! isDOMNodeNotPresent($node)) {
    // ...
}
```

**ভাল:**

```php
function isDOMNodePresent(DOMNode $node): bool
{
    // ...
}

if (isDOMNodePresent($node)) {
    // ...
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### কন্ডিশনিং এড়িয়ে চলুন

This seems like an impossible task. Upon first hearing this, most people say,
"how am I supposed to do anything without an `if` statement?" The answer is that
you can use polymorphism to achieve the same task in many cases. The second
question is usually, "well that's great but why would I want to do that?" The
answer is a previous clean code concept we learned: a function should only do
one thing. When you have classes and functions that have `if` statements, you
are telling your user that your function does more than one thing. Remember,
just do one thing.

**খারাপ:**

```php
class Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        switch ($this->type) {
            case '777':
                return $this->getMaxAltitude() - $this->getPassengerCount();
            case 'Air Force One':
                return $this->getMaxAltitude();
            case 'Cessna':
                return $this->getMaxAltitude() - $this->getFuelExpenditure();
        }
    }
}
```

**ভাল:**

```php
interface Airplane
{
    // ...

    public function getCruisingAltitude(): int;
}

class Boeing777 implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getPassengerCount();
    }
}

class AirForceOne implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude();
    }
}

class Cessna implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getFuelExpenditure();
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন এর মধ্যে টাইপ চেক থেকে বিরত থাকুন (পর্ব ১)

PHP is untyped, which means your functions can take any type of argument.
Sometimes you are bitten by this freedom and it becomes tempting to do
type-checking in your functions. There are many ways to avoid having to do this.
The first thing to consider is consistent APIs.

**খারাপ:**

```php
function travelToTexas($vehicle): void
{
    if ($vehicle instanceof Bicycle) {
        $vehicle->pedalTo(new Location('texas'));
    } elseif ($vehicle instanceof Car) {
        $vehicle->driveTo(new Location('texas'));
    }
}
```

**ভাল:**

```php
function travelToTexas(Vehicle $vehicle): void
{
    $vehicle->travelTo(new Location('texas'));
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফাংশন এর মধ্যে টাইপ চেক থেকে বিরত থাকুন (পর্ব ২)

If you are working with basic primitive values like strings, integers, and arrays,
and you use PHP 7+ and you can't use polymorphism but you still feel the need to
type-check, you should consider
[type declaration](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration)
or strict mode. It provides you with static typing on top of standard PHP syntax.
The problem with manually type-checking is that doing it will require so much
extra verbiage that the faux "type-safety" you get doesn't make up for the lost
readability. Keep your PHP clean, write good tests, and have good code reviews.
Otherwise, do all of that but with PHP strict type declaration or strict mode.

**খারাপ:**

```php
function combine($val1, $val2): int
{
    if (! is_numeric($val1) || ! is_numeric($val2)) {
        throw new Exception('Must be of type Number');
    }

    return $val1 + $val2;
}
```

**ভাল:**

```php
function combine(int $val1, int $val2): int
{
    return $val1 + $val2;
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ডেড কোড মুছে ফেলুন

Dead code is just as bad as duplicate code. There's no reason to keep it in
your codebase. If it's not being called, get rid of it! It will still be safe
in your version history if you still need it.

**খারাপ:**

```php
function oldRequestModule(string $url): void
{
    // ...
}

function newRequestModule(string $url): void
{
    // ...
}

$request = newRequestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**ভাল:**

```php
function requestModule(string $url): void
{
    // ...
}

$request = requestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**


## অবজেক্টস এবং ডেটা স্ট্রাকচার

### অবজেক্ট এনক্যাপসুলেশন ব্যবহার করুন

In PHP you can set `public`, `protected` and `private` keywords for methods.
Using it, you can control properties modification on an object.

* When you want to do more beyond getting an object property, you don't have
to look up and change every accessor in your codebase.
* Makes adding validation simple when doing a `set`.
* Encapsulates the internal representation.
* Easy to add logging and error handling when getting and setting.
* Inheriting this class, you can override default functionality.
* You can lazy load your object's properties, let's say getting it from a
server.

Additionally, this is part of [Open/Closed](#openclosed-principle-ocp) principle.

**খারাপ:**

```php
class BankAccount
{
    public $balance = 1000;
}

$bankAccount = new BankAccount();

// Buy shoes...
$bankAccount->balance -= 100;
```

**ভাল:**

```php
class BankAccount
{
    private $balance;

    public function __construct(int $balance = 1000)
    {
      $this->balance = $balance;
    }

    public function withdraw(int $amount): void
    {
        if ($amount > $this->balance) {
            throw new \Exception('Amount greater than available balance.');
        }

        $this->balance -= $amount;
    }

    public function deposit(int $amount): void
    {
        $this->balance += $amount;
    }

    public function getBalance(): int
    {
        return $this->balance;
    }
}

$bankAccount = new BankAccount();

// Buy shoes...
$bankAccount->withdraw($shoesPrice);

// Get balance
$balance = $bankAccount->getBalance();
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### অবজেক্ট তৈরিতে private protected মেম্বার ব্যাবহার করুন

* `public` methods and properties are most dangerous for changes, because some outside code may easily rely on them and you can't control what code relies on them. **Modifications in class are dangerous for all users of class.**
* `protected` modifier are as dangerous as public, because they are available in scope of any child class. This effectively means that difference between public and protected is only in access mechanism, but encapsulation guarantee remains the same. **Modifications in class are dangerous for all descendant classes.**
* `private` modifier guarantees that code is **dangerous to modify only in boundaries of single class** (you are safe for modifications and you won't have [Jenga effect](http://www.urbandictionary.com/define.php?term=Jengaphobia&defid=2494196)).

Therefore, use `private` by default and `public/protected` when you need to provide access for external classes.

For more information you can read the [blog post](http://fabien.potencier.org/pragmatism-over-theory-protected-vs-private.html) on this topic written by [Fabien Potencier](https://github.com/fabpot).

**খারাপ:**

```php
class Employee
{
    public $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}

$employee = new Employee('John Doe');
// Employee name: John Doe
echo 'Employee name: ' . $employee->name;
```

**ভাল:**

```php
class Employee
{
    private $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

$employee = new Employee('John Doe');
// Employee name: John Doe
echo 'Employee name: ' . $employee->getName();
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## ক্লাস

### Inheritanceএর থেকে Composition কে গুরুত্ব দিন

As stated famously in [*Design Patterns*](https://en.wikipedia.org/wiki/Design_Patterns) by the Gang of Four,
you should prefer composition over inheritance where you can. There are lots of
good reasons to use inheritance and lots of good reasons to use composition.
The main point for this maxim is that if your mind instinctively goes for
inheritance, try to think if composition could model your problem better. In some
cases it can.

You might be wondering then, "when should I use inheritance?" It
depends on your problem at hand, but this is a decent list of when inheritance
makes more sense than composition:

1. Your inheritance represents an "is-a" relationship and not a "has-a"
relationship (Human->Animal vs. User->UserDetails).
2. You can reuse code from the base classes (Humans can move like all animals).
3. You want to make global changes to derived classes by changing a base class.
(Change the caloric expenditure of all animals when they move).

**খারাপ:**

```php
class Employee
{
    private $name;

    private $email;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    // ...
}

// Bad because Employees "have" tax data.
// EmployeeTaxData is not a type of Employee

class EmployeeTaxData extends Employee
{
    private $ssn;

    private $salary;

    public function __construct(string $name, string $email, string $ssn, string $salary)
    {
        parent::__construct($name, $email);

        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}
```

**ভাল:**

```php
class EmployeeTaxData
{
    private $ssn;

    private $salary;

    public function __construct(string $ssn, string $salary)
    {
        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}

class Employee
{
    private $name;

    private $email;

    private $taxData;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    public function setTaxData(EmployeeTaxData $taxData): void
    {
        $this->taxData = $taxData;
    }

    // ...
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### ফ্লুয়েন্ট ইন্টারফেস এড়িয়ে চলুন

A [Fluent interface](https://en.wikipedia.org/wiki/Fluent_interface) is an object
oriented API that aims to improve the readability of the source code by using
[Method chaining](https://en.wikipedia.org/wiki/Method_chaining).

While there can be some contexts, frequently builder objects, where this
pattern reduces the verbosity of the code (for example the [PHPUnit Mock Builder](https://phpunit.de/manual/current/en/test-doubles.html)
or the [Doctrine Query Builder](http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/query-builder.html)),
more often it comes at some costs:

1. Breaks [Encapsulation](https://en.wikipedia.org/wiki/Encapsulation_%28object-oriented_programming%29).
2. Breaks [Decorators](https://en.wikipedia.org/wiki/Decorator_pattern).
3. Is harder to [mock](https://en.wikipedia.org/wiki/Mock_object) in a test suite.
4. Makes diffs of commits harder to read.

For more information you can read the full [blog post](https://ocramius.github.io/blog/fluent-interfaces-are-evil/)
on this topic written by [Marco Pivetta](https://github.com/Ocramius).

**খারাপ:**

```php
class Car
{
    private $make = 'Honda';

    private $model = 'Accord';

    private $color = 'white';

    public function setMake(string $make): self
    {
        $this->make = $make;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setModel(string $model): self
    {
        $this->model = $model;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setColor(string $color): self
    {
        $this->color = $color;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = (new Car())
    ->setColor('pink')
    ->setMake('Ford')
    ->setModel('F-150')
    ->dump();
```

**ভাল:**

```php
class Car
{
    private $make = 'Honda';

    private $model = 'Accord';

    private $color = 'white';

    public function setMake(string $make): void
    {
        $this->make = $make;
    }

    public function setModel(string $model): void
    {
        $this->model = $model;
    }

    public function setColor(string $color): void
    {
        $this->color = $color;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = new Car();
$car->setColor('pink');
$car->setMake('Ford');
$car->setModel('F-150');
$car->dump();
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Prefer final classes

The `final` keyword should be used whenever possible:

1. It prevents an uncontrolled inheritance chain.
2. It encourages [composition](#prefer-composition-over-inheritance).
3. It encourages the [Single Responsibility Pattern](#single-responsibility-principle-srp).
4. It encourages developers to use your public methods instead of extending the class to get access to protected ones.
5. It allows you to change your code without breaking applications that use your class.

The only condition is that your class should implement an interface and no other public methods are defined.

For more informations you can read [the blog post](https://ocramius.github.io/blog/when-to-declare-classes-final/) on this topic written by [Marco Pivetta (Ocramius)](https://ocramius.github.io/).

**খারাপ:**

```php
final class Car
{
    private $color;

    public function __construct($color)
    {
        $this->color = $color;
    }

    /**
     * @return string The color of the vehicle
     */
    public function getColor()
    {
        return $this->color;
    }
}
```

**ভাল:**

```php
interface Vehicle
{
    /**
     * @return string The color of the vehicle
     */
    public function getColor();
}

final class Car implements Vehicle
{
    private $color;

    public function __construct($color)
    {
        $this->color = $color;
    }

    public function getColor()
    {
        return $this->color;
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## SOLID

**SOLID** is the mnemonic acronym introduced by Michael Feathers for the first five principles named by Robert Martin, which meant five basic principles of object-oriented programming and design.

 * [S: Single Responsibility Principle (SRP)](#single-responsibility-principle-srp)
 * [O: Open/Closed Principle (OCP)](#openclosed-principle-ocp)
 * [L: Liskov Substitution Principle (LSP)](#liskov-substitution-principle-lsp)
 * [I: Interface Segregation Principle (ISP)](#interface-segregation-principle-isp)
 * [D: Dependency Inversion Principle (DIP)](#dependency-inversion-principle-dip)

### Single Responsibility Principle (SRP)

As stated in Clean Code, "There should never be more than one reason for a class
to change". It's tempting to jam-pack a class with a lot of functionality, like
when you can only take one suitcase on your flight. The issue with this is
that your class won't be conceptually cohesive and it will give it many reasons
to change. Minimizing the amount of times you need to change a class is important.
It's important because if too much functionality is in one class and you modify a piece of it,
it can be difficult to understand how that will affect other dependent modules in
your codebase.

**খারাপ:**

```php
class UserSettings
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }

    public function changeSettings(array $settings): void
    {
        if ($this->verifyCredentials()) {
            // ...
        }
    }

    private function verifyCredentials(): bool
    {
        // ...
    }
}
```

**ভাল:**

```php
class UserAuth
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }

    public function verifyCredentials(): bool
    {
        // ...
    }
}

class UserSettings
{
    private $user;

    private $auth;

    public function __construct(User $user)
    {
        $this->user = $user;
        $this->auth = new UserAuth($user);
    }

    public function changeSettings(array $settings): void
    {
        if ($this->auth->verifyCredentials()) {
            // ...
        }
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Open/Closed Principle (OCP)

As stated by Bertrand Meyer, "software entities (classes, modules, functions,
etc.) should be open for extension, but closed for modification." What does that
mean though? This principle basically states that you should allow users to
add new functionalities without changing existing code.

**খারাপ:**

```php
abstract class Adapter
{
    protected $name;

    public function getName(): string
    {
        return $this->name;
    }
}

class AjaxAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'ajaxAdapter';
    }
}

class NodeAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'nodeAdapter';
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        $adapterName = $this->adapter->getName();

        if ($adapterName === 'ajaxAdapter') {
            return $this->makeAjaxCall($url);
        } elseif ($adapterName === 'httpNodeAdapter') {
            return $this->makeHttpCall($url);
        }
    }

    private function makeAjaxCall(string $url): Promise
    {
        // request and return promise
    }

    private function makeHttpCall(string $url): Promise
    {
        // request and return promise
    }
}
```

**ভাল:**

```php
interface Adapter
{
    public function request(string $url): Promise;
}

class AjaxAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class NodeAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        return $this->adapter->request($url);
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Liskov Substitution Principle (LSP)

This is a scary term for a very simple concept. It's formally defined as "If S
is a subtype of T, then objects of type T may be replaced with objects of type S
(i.e., objects of type S may substitute objects of type T) without altering any
of the desirable properties of that program (correctness, task performed,
etc.)." That's an even scarier definition.

The best explanation for this is if you have a parent class and a child class,
then the base class and child class can be used interchangeably without getting
incorrect results. This might still be confusing, so let's take a look at the
classic Square-Rectangle example. Mathematically, a square is a rectangle, but
if you model it using the "is-a" relationship via inheritance, you quickly
get into trouble.

**খারাপ:**

```php
class Rectangle
{
    protected $width = 0;

    protected $height = 0;

    public function setWidth(int $width): void
    {
        $this->width = $width;
    }

    public function setHeight(int $height): void
    {
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square extends Rectangle
{
    public function setWidth(int $width): void
    {
        $this->width = $this->height = $width;
    }

    public function setHeight(int $height): void
    {
        $this->width = $this->height = $height;
    }
}

function printArea(Rectangle $rectangle): void
{
    $rectangle->setWidth(4);
    $rectangle->setHeight(5);

    // BAD: Will return 25 for Square. Should be 20.
    echo sprintf('%s has area %d.', get_class($rectangle), $rectangle->getArea()) . PHP_EOL;
}

$rectangles = [new Rectangle(), new Square()];

foreach ($rectangles as $rectangle) {
    printArea($rectangle);
}
```

**ভাল:**

The best way is separate the quadrangles and allocation of a more general subtype for both shapes.

Despite the apparent similarity of the square and the rectangle, they are different.
A square has much in common with a rhombus, and a rectangle with a parallelogram, but they are not subtypes.
A square, a rectangle, a rhombus and a parallelogram are separate shapes with their own properties, albeit similar.

```php
interface Shape
{
    public function getArea(): int;
}

class Rectangle implements Shape
{
    private $width = 0;
    private $height = 0;

    public function __construct(int $width, int $height)
    {
        $this->width = $width;
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square implements Shape
{
    private $length = 0;

    public function __construct(int $length)
    {
        $this->length = $length;
    }

    public function getArea(): int
    {
        return $this->length ** 2;
    }
}

function printArea(Shape $shape): void
{
    echo sprintf('%s has area %d.', get_class($shape), $shape->getArea()).PHP_EOL;
}

$shapes = [new Rectangle(4, 5), new Square(5)];

foreach ($shapes as $shape) {
    printArea($shape);
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Interface Segregation Principle (ISP)

ISP states that "Clients should not be forced to depend upon interfaces that
they do not use."

A good example to look at that demonstrates this principle is for
classes that require large settings objects. Not requiring clients to set up
huge amounts of options is beneficial, because most of the time they won't need
all of the settings. Making them optional helps prevent having a "fat interface".

**খারাপ:**

```php
interface Employee
{
    public function work(): void;

    public function eat(): void;
}

class HumanEmployee implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        // ...... eating in lunch break
    }
}

class RobotEmployee implements Employee
{
    public function work(): void
    {
        //.... working much more
    }

    public function eat(): void
    {
        //.... robot can't eat, but it must implement this method
    }
}
```

**ভাল:**

Not every worker is an employee, but every employee is a worker.

```php
interface Workable
{
    public function work(): void;
}

interface Feedable
{
    public function eat(): void;
}

interface Employee extends Feedable, Workable
{
}

class HumanEmployee implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        //.... eating in lunch break
    }
}

// robot can only work
class RobotEmployee implements Workable
{
    public function work(): void
    {
        // ....working
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

### Dependency Inversion Principle (DIP)

This principle states two essential things:
1. High-level modules should not depend on low-level modules. Both should
depend on abstractions.
2. Abstractions should not depend upon details. Details should depend on
abstractions.

This can be hard to understand at first, but if you've worked with PHP frameworks (like Symfony), you've seen an implementation of this principle in the form of Dependency
Injection (DI). While they are not identical concepts, DIP keeps high-level
modules from knowing the details of its low-level modules and setting them up.
It can accomplish this through DI. A huge benefit of this is that it reduces
the coupling between modules. Coupling is a very bad development pattern because
it makes your code hard to refactor.

**খারাপ:**

```php
class Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot extends Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**ভাল:**

```php
interface Employee
{
    public function work(): void;
}

class Human implements Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot implements Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## পুনরাবৃত্তি করবেন না (DRY)

Try to observe the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.

ডুপ্লিকেট কোড এড়ানোর জন্য সব সময় ই চেষ্টা করা উচিত। ডুপ্লিকেট কোড খারাপ কারণ হল যে আপনার যদি কোন কিছু পরিবর্তন করতে হয় তাহলে যত জায়গায় ডুপ্লিকেট কোড লিখেছেন সব জাইগায় ই পরিবর্তন করতে হবে।

মনে করেন আপনি একটা রেস্টুরেন্ট চালাচ্ছেন এবং আপনার সব ইনভেন্টরি এর হিসাব রাখতে হয়: টমাটো, পেয়াজ, রসুন, মরিচ ইত্যাদি। এখন যদি এই ইনভেন্টরি এর জন্য আলাদা আলাদা লিস্ট করেন তাহলে প্রতি বার ই আপনার সবগুলো লিস্ট আপডেট করতে হবে যদি কোন লিস্ট আপডেট করতে ভুলে যান তাহলে আপনার হিসাব ও ভুল হয়ে যাবে। কিন্তু যদি শুধু একটা লিস্ট থাকত তাহলে কত সহজেই কাজ হয়ে যেত শুদু মাত্র একটা জায়গায় তেই পরিবর্তন এর মাধ্যমে।

যদি এমন হয় যে আপনার ডুপ্লিকেট কোড করার কারণ হল আপনার কাছে ২ টা আলাদা জিনিষ আছে কিন্তু সেখানে কিছু জিনিস একই রকম যেটা আপনাকে ফোর্স করতেছে আলাদা ভাবে কোড করার জন্য। তাহলে আপনি ওই আলদা জিনিসগুলো আলাদা ভাবে abstraction করে জিনিসটা হান্ডেল করতে পারেন আর এর জন্য ওই আলাদা জিনিষ গুলো একটা function/module/class এ নিয়ে কাজ করতে পারেন তাহলে এই function/module/class আপনি অন্য কোথায় লাগলে সেখানে ব্যাবহার করতে পারবেন।

abstraction করা আসলে একটুখানি কঠিন এর জন্য আপনার উচিত হবে SOLID principles এর [Classes](#classes) section তা ফলো করা। কারণ খারাপ abstraction ডুপ্লিকেট কোড এর থেকেও বেশি খারাপ, তাই আপনাকে এই বিষয়ে অবশ্যই সাবধান হতে হবে।

**খারাপ:**

```php
function showDeveloperList(array $developers): void
{
    foreach ($developers as $developer) {
        $expectedSalary = $developer->calculateExpectedSalary();
        $experience = $developer->getExperience();
        $githubLink = $developer->getGithubLink();
        $data = [$expectedSalary, $experience, $githubLink];

        render($data);
    }
}

function showManagerList(array $managers): void
{
    foreach ($managers as $manager) {
        $expectedSalary = $manager->calculateExpectedSalary();
        $experience = $manager->getExperience();
        $githubLink = $manager->getGithubLink();
        $data = [$expectedSalary, $experience, $githubLink];

        render($data);
    }
}
```

**ভাল:**

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        $expectedSalary = $employee->calculateExpectedSalary();
        $experience = $employee->getExperience();
        $githubLink = $employee->getGithubLink();
        $data = [$expectedSalary, $experience, $githubLink];

        render($data);
    }
}
```

**Very good:**

কোড এর কম্প্যাক্ট ভার্সন ব্যাবহার করা সবসময় ভাল।

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        render([$employee->calculateExpectedSalary(), $employee->getExperience(), $employee->getGithubLink()]);
    }
}
```

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**

## অনুবাদ

এটা অন্যান্য ভাষাতেও খুঁজে পাবেন এখানেঃ 

* :bangladesh: **বাংলা:**
   * [nayeemdev/clean-code-php](https://github.com/nayeemdev/clean-code-php)
* :cn: **Chinese:**
   * [php-cpm/clean-code-php](https://github.com/php-cpm/clean-code-php)
* :ru: **Russian:**
   * [peter-gribanov/clean-code-php](https://github.com/peter-gribanov/clean-code-php)
* :es: **Spanish:**
   * [fikoborquez/clean-code-php](https://github.com/fikoborquez/clean-code-php)
* :brazil: **Portuguese:**
   * [fabioars/clean-code-php](https://github.com/fabioars/clean-code-php)
   * [jeanjar/clean-code-php](https://github.com/jeanjar/clean-code-php/tree/pt-br)
* :thailand: **Thai:**
   * [panuwizzle/clean-code-php](https://github.com/panuwizzle/clean-code-php)
* :fr: **French:**
   * [errorname/clean-code-php](https://github.com/errorname/clean-code-php)
* :vietnam: **Vietnamese**
   * [viethuongdev/clean-code-php](https://github.com/viethuongdev/clean-code-php)
* :kr: **Korean:**
   * [yujineeee/clean-code-php](https://github.com/yujineeee/clean-code-php)
* :tr: **Turkish:**
   * [anilozmen/clean-code-php](https://github.com/anilozmen/clean-code-php)
* :iran: **Persian:**
     * [amirshnll/clean-code-php](https://github.com/amirshnll/clean-code-php)

**[⬆ সূচিপত্রে ফিরে যান](#সুচিপত্র)**
