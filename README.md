# react-pin-field

A React component for entering PIN codes.

![gif](https://user-images.githubusercontent.com/10437171/70847884-f9d35f00-1e69-11ea-8152-1c70eda12137.gif)

*Live demo at https://react-pin-field.soywod.me.*

## Installation

```bash
yarn add react-pin-field
# or
npm install react-pin-field
```

## Usage

```typescript
import PinField from "react-pin-field"
```

## Props

```typescript
type PinFieldProps = {
  allowedChars?: string | RegExp
  className?: string
  length?: number
  onChange?: (code: string) => void
  onComplete?: (code: string) => void
  onReceiveKey: (key: string) => string
  style?: React.CSSProperties
} & React.InputHTMLAttributes<HTMLInputElement>

const defaultProps = {
  allowedChars: /^[a-zA-Z0-9]$/,
  className: "",
  length: 5,
  onChange: () => {},
  onComplete: () => {},
  onReceiveKey: (key: string) => key,
  style: {},
}
```

## Examples

Refer to the [live demo](https://react-pin-field.soywod.me) to see the result.

### Basic

```typescript
<PinField />
```

### With custom style

You can pass a custom `className`, a custom `style`, or override the CSS class
`.react-pin-field`.

```typescript
<PinField
  style={{
    width: 50,
    height: 50,
    borderRadius: "50%",
    border: "1px solid gray",
    outline: "none",
    textAlign: "center",
    margin: 10,
  }}
/>
```

### With custom length

```typescript
<PinField length={3} />
```

### With custom validation

```typescript
<PinField allowedChars="0123456789" />
<PinField allowedChars={/^[0-9]$/} />
```

### With custom events

- onChange: when a char change
- onComplete: when all the chars have been filled
- onReceiveKey: when receive a key (used to format it, for eg: set to upper case)

```typescript
<PinField
  onChange={handleChange}
  onComplete={handleComplete}
  onReceiveKey={key => key.toUpperCase()}
/>
```

### With custom InputHTMLAttributes

```typescript
<PinField type="password" autoFocus disabled={loading} />
```

## Development

```bash
git clone https://github.com/soywod/react-pin-field.git
cd react-pin-field
yarn install
```

To start the development server:

```bash
yarn start
```

To build the demo:

```bash
yarn build:demo
```

To build the lib:

```bash
yarn build:lib
```

## Changelog

See [CHANGELOG.md](https://github.com/soywod/react-pin-field/blob/master/CHANGELOG.md)

## License

[MIT](https://github.com/soywod/react-pin-field/blob/master/LICENSE) -
Copyright (c) 2019 Clément DOUIN
