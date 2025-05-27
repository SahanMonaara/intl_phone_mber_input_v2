
# International Phone Number Input v2

[![Pub Version](https://img.shields.io/pub/v/intl_phone_number_input_v2)](https://pub.dev/packages/intl_phone_number_input_v2)
[![License](https://img.shields.io/github/license/SahanMonaara/intl_phone_number_input_v2)](LICENSE)

`intl_phone_number_input_v2` is a Flutter package that provides a customizable international phone number input widget. This package allows developers to easily integrate phone number input fields into their Flutter applications, supporting validation and formatting for different countries.

## Features

- Supports international phone number input.
- Customizable input field.
- Auto-formatting and validation of phone numbers.
- Country code picker with flag icons.
- Lightweight and easy to integrate.

## Installation

Add `intl_phone_number_input_v2` to your `pubspec.yaml` file:

```yaml
dependencies:
  intl_phone_number_input_v2: ^0.0.8
```

Then, run `flutter pub get` to install the package.

## Usage

Here's a basic example of how to use the `intl_phone_number_input_v2` package:

```dart
import 'package:flutter/material.dart';
import 'package:intl_phone_number_input_v2/intl_phone_number_input_v2.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('International Phone Number Input'),
        ),
        body: MyHomePage(),
      ),
    );
  }
}

class MyHomePage extends StatefulWidget {
  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String phoneNumber;
  PhoneNumber number = PhoneNumber(isoCode: 'US');

  @override
  Widget build(BuildContext context) {
    return Padding(
      padding: const EdgeInsets.all(16.0),
      child: InternationalPhoneNumberInput(
        onInputChanged: (PhoneNumber number) {
          print(number.phoneNumber);
        },
        onInputValidated: (bool value) {
          print(value);
        },
        selectorConfig: SelectorConfig(
          selectorType: PhoneInputSelectorType.DROPDOWN,
        ),
        ignoreBlank: false,
        autoValidateMode: AutovalidateMode.disabled,
        initialValue: number,
        textFieldController: TextEditingController(),
        formatInput: true,
        keyboardType:
            TextInputType.numberWithOptions(signed: true, decimal: true),
        inputBorder: OutlineInputBorder(),
        onSaved: (PhoneNumber number) {
          phoneNumber = number.phoneNumber;
        },
      ),
    );
  }
}
```

## Documentation

For more detailed documentation and examples, please refer to the [package documentation on pub.dev](https://pub.dev/packages/intl_phone_number_input_v2).

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your changes. Make sure to follow the existing code style and include tests for any new features or bug fixes.

1. Fork the repository.
2. Create a new branch: `git checkout -b my-branch-name`.
3. Make your changes and commit them: `git commit -m 'Add new feature'`.
4. Push to the branch: `git push origin my-branch-name`.
5. Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [intl_phone_number_input](https://pub.dev/packages/intl_phone_number_input) for providing the base implementation.
