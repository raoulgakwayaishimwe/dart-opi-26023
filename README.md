# README.md

## Student Information

-   **Name:** Gakwaya Ishimwe Raoul
-   **Registration Number:** 26023

## My Numbers

-   D = 1
-   L = 1
-   Starting balance = 1000 + (1 × 10) = **1010 RWF**
-   Bus fare = 200 + 1 = **201 RWF**
-   Student discount = 10 + 1 = **11%**

## Output of main.dart

``` text
Error: name too short
Owner: Gakwaya Ishimwe Raoul | Balance: 1230 RWF
Owner: Gakwaya Ishimwe Raoul | Balance: 1230 RWF
Error: top-up must be 500 to 50000 RWF
Topped up 2000 RWF
Paid 223 RWF
Paid 223 RWF
Owner: Gakwaya Ishimwe Raoul | Balance: 2784 RWF
Student discount: 28 RWF
Paid 195 RWF
Owner: Gakwaya Ishimwe Raoul | Balance: 1035 RWF
Student card: 13% off
```

## Part 4 --- Bug Hunt

**File: bug_hunt.dart**

``` dart
class Phone {
  String _brand = '';
  int _battery = 0;

  Phone(String brand, int battery) {
    _brand = brand;
    _battery = battery;
  }

  int get battery {
    return _battery;
  }

  set battery(int value) {
    if (value >= 0 && value <= 100) {
      _battery = value;
    }
  }

  void restart() {
    print('Restarting phone');
  }
}

class SmartPhone extends Phone {
  String _system = '';

  SmartPhone(String brand, int battery, String system)
      : super(brand, battery) {
    _system = system;
  }

  @override
  void restart() {
    print('Restarting $_system');
  }
}

void main() {
  Phone p = Phone('Tecno', 50);
  p.battery = 100;
  print(p.battery);
}
```

## Part 5 --- Prediction Code

**File: prediction.dart**

``` dart
class Bag {
  int _items = 0;

  int get items {
    return _items;
  }

  set items(int value) {
    if (value >= 0) {
      _items = value;
    }
  }

  void add() {
    _items = _items + 1;
  }
}

class BigBag extends Bag {
  @override
  void add() {
    super.add();
    super.add();
  }
}

void main() {
  Bag a = Bag();
  a.add();
  a.items = -5;
  print(a.items);

  BigBag b = BigBag();
  b.add();
  b.add();
  b.items = b.items + 1;
  print(b.items);
}
```
