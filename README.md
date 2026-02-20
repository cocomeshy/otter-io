# io

Standard I/O operations for Otter. Provides console output using platform-specific stdout handles.

## API Reference

### `io.out(text:str, end:str = "\n") -> void`

Print text to standard output, followed by `end`.

- **Parameters:**
  - `text` — String to print
  - `end` — String appended after text (default: newline `"\n"`)
- **Platform:** Uses `WriteFile` to stdout handle (Windows), `write` syscall (Linux/macOS)

```otter
io.out("hello world");         // prints: hello world\n
io.out("no newline", "");      // prints: no newline
io.out($"value: {42}");       // prints: value: 42\n
```

---

### `io.write_stdout(text:str) -> void`

Write raw string to standard output without any suffix. Low-level alternative to `io.out`.

- **Parameters:**
  - `text` — String to write

```otter
io.write_stdout("raw ");
io.write_stdout("output");
// prints: raw output
```

---

### `io.io_init() -> void`

Initialize the I/O subsystem. Currently a no-op, reserved for future use.

## Dependencies

- `memory` — for `strlen`

## Install

```
otter pkg add io
otter pkg pull
```
