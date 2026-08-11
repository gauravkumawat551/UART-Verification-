
# UART Verification using SystemVerilog

## 📌 Project Overview

This project focuses on the functional verification of a UART (Universal Asynchronous Receiver/Transmitter) design using SystemVerilog.

The main objective of the project is to verify UART transmit and receive functionality under different operating conditions and ensure that the design behaves according to the expected protocol.

The verification environment generates different UART transactions, drives them to the DUT, monitors the DUT outputs, and compares the actual results with the expected behavior.

---

## 🎯 Objectives

- Verify UART transmitter functionality.
- Verify UART receiver functionality.
- Verify correct serial data transmission and reception.
- Check different data patterns and frame configurations.
- Verify start bit, data bits, parity, and stop bit behavior.
- Detect protocol and functional errors.
- Improve verification coverage through constrained and directed test scenarios.

---

## 🏗️ UART Protocol

UART is an asynchronous serial communication protocol.

A typical UART frame consists of:

```text
Idle | Start | Data Bits | Parity | Stop
     |       |           |        |
     |       |           |        +---- Stop Bit
     |       |           +------------- Optional Parity
     |       +------------------------- Data Bits
     +--------------------------------- Start Bit
````

The communication does not require a separate clock signal between the transmitter and receiver. Both sides operate using a predefined baud rate.

---

## 🔍 Verification Architecture

The verification environment consists of the following major components:

```text
                    +----------------------+
                    |    Test / Stimulus   |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |      Generator       |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |      Driver          |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |        UART DUT      |
                    +----------+-----------+
                               |
                 +-------------+-------------+
                 |                           |
                 v                           v
          +-------------+             +-------------+
          |   Monitor   |             |   Monitor   |
          +------+------+             +------+------+
                 |                           |
                 +-------------+-------------+
                               |
                               v
                    +----------------------+
                    |    Scoreboard        |
                    +----------------------+
                               |
                               v
                    +----------------------+
                    | Verification Result  |
                    +----------------------+
```

---

## 🧪 Test Scenarios

The following scenarios are verified:

* Basic UART transmission.
* Basic UART reception.
* Multiple data values.
* Different data patterns.
* All-zero data.
* All-one data.
* Alternating bit patterns.
* Back-to-back UART transactions.
* Reset behavior.
* Start and stop bit verification.
* Frame-level data integrity.
* Error detection scenarios.

---

## 🛠️ Tools & Technologies

| Category        | Technology                       |
| --------------- | -------------------------------- |
| HDL             | SystemVerilog                    |
| Verification    | SystemVerilog Testbench          |
| Simulation      | Cadence Xcelium / EDA Playground |
| Waveform        | SimVision / GTKWave              |
| Version Control | Git & GitHub                     |

---

## 📂 Project Structure

```text
UART-Verification/
│
├── rtl/
│   └── uart.s
│
├── tb/
│   ├── uart_tb.s
│   ├── uart_transaction.s
│   ├── uart_generator.s
│   ├── uart_driver.s
│   ├── uart_monitor.s
│   └── uart_scoreboard.s
│
├── test/
│   └── uart_test.s
│
├── sim/
│   └── simulation_files
│
├── waveform/
│   └── waveform_files
│
└── README.md
```

> Note: Modify the file/folder names according to the actual files present in this repository.

---

## 🔄 Verification Flow

1. The test generates UART transactions.
2. The generator creates different input data patterns.
3. The driver converts transactions into UART signal activity.
4. The DUT performs UART transmission/reception.
5. The monitor observes DUT signals.
6. The scoreboard compares expected and actual results.
7. Any mismatch is reported as a verification failure.
8. Waveforms are analyzed to debug protocol-level issues.

---

## 📊 Functional Checks

The verification environment checks:

* Correct start bit generation.
* Correct number of data bits.
* Correct bit ordering.
* Correct stop bit generation.
* Correct received data.
* Correct baud-rate timing.
* Reset functionality.
* Data integrity between TX and RX.
* Correct behavior during consecutive transactions.

---

## 📈 Coverage

Functional coverage is used to ensure that important UART scenarios are exercised.

Example coverage points include:

* Different data values.
* Different data patterns.
* Start bit.
* Stop bit.
* Reset conditions.
* TX/RX transactions.
* Back-to-back transfers.
* Error conditions.

---

## 🐞 Debugging & Waveform Analysis

Simulation waveforms are analyzed to verify the timing and sequence of UART signals.

Important signals observed during debugging include:

```text
clk
rst
tx
rx
tx_data
rx_data
tx_valid
rx_valid
tx_busy
rx_done
```

Waveform analysis helps identify issues related to:

* Bit timing
* Baud-rate generation
* Frame formatting
* Data sampling
* Reset behavior

---

## ✅ Expected Result

The UART design should correctly transmit and receive the generated test data without data corruption.

The scoreboard should report matching expected and actual values for all valid transactions.

Example:

```text
----------------------------------------
UART VERIFICATION SUMMARY
----------------------------------------
Transactions      : 100
Passed            : 100
Failed            : 0
----------------------------------------
TEST PASSED
----------------------------------------
```

---

## 🚀 Key Learning Outcomes

Through this project, I gained practical experience in:

* SystemVerilog-based verification.
* Testbench architecture.
* Transaction-based verification.
* UART protocol verification.
* Driver and monitor development.
* Scoreboard-based checking.
* Functional coverage.
* Simulation and waveform debugging.
* Identifying and debugging RTL/protocol-level issues.
* Git and GitHub-based project management.

---

## 👨‍💻 Author

**Gaurav Kumawat**

M.Sc. Tech. – Electronics
NIT Warangal

### Areas of Interest

* RTL Design
* Design Verification
* FPGA Design
* SystemVerilog
* Digital Design
* VLSI

---

## ⭐ Future Improvements

* Add complete UVM-based verification environment.
* Add assertion-based verification using SystemVerilog Assertions (SVA).
* Improve functional and code coverage.
* Add constrained-random stimulus.
* Add automated regression testing.
* Verify additional UART configurations and error conditions.

```
https://edaplayground.com/x/fasj

