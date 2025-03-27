# Node Selection Utility

## Project Overview

This lightweight JavaScript library provides a robust utility for dynamically selecting nodes from a remote server via HTTP requests. The primary purpose is to facilitate distributed computing and load balancing scenarios by retrieving and randomly selecting available nodes.

### Key Features
- Asynchronous node retrieval
- Random node selection
- Easy integration with axios for HTTP requests
- Error-tolerant design
- Minimal external dependencies

## Installation

Install the library using npm:

```bash
npm install node-selection-utility
```

### Prerequisites
- Node.js (v14.0.0 or higher)
- axios library

## API Reference

### `getNode(url: string, taskId: string): Promise<string>`

Retrieves a list of nodes from a specified URL and returns a randomly selected node's URL.

#### Parameters
- `url` (string): Base URL of the node service
- `taskId` (string): Unique identifier for the task/request

#### Returns
- `Promise<string>`: URL of a randomly selected node, or an empty array if no nodes are found

#### Example Usage
```javascript
import getNode from 'node-selection-utility';

async function distributeTask() {
  try {
    const selectedNodeUrl = await getNode('https://node-service.com', 'task-123');
    console.log('Selected Node:', selectedNodeUrl);
  } catch (error) {
    console.error('Node selection failed');
  }
}
```

## Repository Structure

- `getNode.js`: Core implementation of node selection logic
- `README.md`: Project documentation

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Open a Pull Request

### Running Tests
Currently, no test suite is implemented. Contributions adding comprehensive testing are encouraged.

## License

[MIT License](LICENSE) - Feel free to use, modify, and distribute this library.