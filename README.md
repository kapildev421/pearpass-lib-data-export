# pearpass-lib-data-export

A utility for exporting PearPass vaults to various formats.

## Features

- Export vault data to CSV format.
- Export vault data to JSON format.

## Security Notice

1. To ensure the security and integrity of your projects, please note that official PearPass packages are distributed exclusively through our GitHub organization.
2. Any packages with similar names found on the npm registry or other third-party package managers are not affiliated with PearPass and should be strictly avoided. We recommend installing directly from this repository to ensure you are using the verified, open-source version.

## Installation

Install the package using npm:

```bash
npm install git+https://github.com/tetherto/pearpass-lib-data-export.git
```

## Testing

To run the tests, use the following command:

```bash
npm test
```

## Usage Examples

Here's how you can use the library to export data:

### Export to JSON

```javascript
import { parseDataToJson } from '@tetherto/pearpass-lib-data-export';

const vaultData = [
  {
    name: 'My Vault',
    records: [
      {
        type: 'login',
        data: {
          title: 'Sample Login',
          username: 'user',
          password: 'password123'
        }
      }
    ]
  }
];

const files = parseDataToJson(vaultData);
files.forEach(file => {
  console.log(`File: ${file.filename}`);
  // You can now save file.data to a file
});
```

### Export to CSV

```javascript
import { parseDataToCsvText } from '@tetherto/pearpass-lib-data-export';

const vaultData = [
  {
    name: 'My Vault',
    records: [
      {
        type: 'login',
        data: {
          title: 'Sample Login',
          username: 'user',
          password: 'password123'
        }
      }
    ]
  }
];

const files = parseDataToCsvText(vaultData);
files.forEach(file => {
  console.log(`File: ${file.filename}`);
  // You can now save file.data to a file
});
```

## Related Projects

*   [@tetherto/pearpass-lib-data-import](https://github.com/tetherto/pearpass-lib-data-import)

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](./LICENSE) file for details.
