A sample command-line application with an entrypoint in `bin/`, library code
in `lib/`, and example unit test in `test/`.

```
void main(List<String> arguments) {
  try {
    Cat cat1 = Cat(-5);
    print(cat1.age);
  }on ageExecpt catch (e) {
    print(e.message);
  }
}

class ageExecpt implements Exception {
  String message = "Age Exception";
  ageExecpt({this.message='Age Exception'});
  @override
  String toString() => "Age Exception: ${message}";
}

class Cat {
  int age = 0;
  Cat(int age) {
    if (age < 0) {
      throw ageExecpt(message: 'Age cannot be negative');
      // print("Age cannot be negative");
    } else {
      this.age = age;
    }
  }
}

```
