# Input

### Intro

The user can enter content in the text box.

### Install

```javascript
// react
import { Input } from '@nutui/nutui-react';

```

### Basic Usage

:::demo
```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const [value, UpdateValue] = useState('')
  return (
    <>
      <Input name="text" label="Text" defaultValue={value} placeholder="Text" onChange={(val) => {
            UpdateValue(val)
          }}/>
    </>
  );
};
export default App;
```
:::

### Custom Type

:::demo
```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        text: '',
        password: '',
        number: '',
        digit: '',
        tel: ''
    })
  return (
    <>
       <Input
          name="text"
          label="Text" 
          placeholder="Text" 
          defaultValue={state.text}
        />
        <Input
          name="password"
          label="Password" 
          placeholder="Password"
          defaultValue={state.password}
          type="password"
        />
        <Input
          name="number"
          label="Number" 
          placeholder="Number"
          defaultValue={state.number}
          type="number"
        />
        <Input
          name="digit"
          label="Digit" 
          placeholder="Digit"
          defaultValue={state.digit}
          type="digit"
        />
        <Input
          name="tel"
          label="Tel" 
          placeholder="Tel"
          defaultValue={state.tel}
          type="tel"
        />
    </>
  )
}
export default App;
```
:::


### Readonly And Disabled

:::demo
```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        readonly:'',
        disabled: '',
    })
  return (
    <>
       <Input
          label="Text" 
          placeholder="Readonly" 
          defaultValue={state.readonly}
          readonly
        />
        <Input
          label="Text" 
          placeholder="Disabled"
          defaultValue={state.disabled}
          disabled
        />
    </>
  )
}
export default App;
```
:::

### Show Icon

The user can enter content in the text box. Configure the icons on both sides of the input box through `left-icon` and `right-icon`, and display the clear icon during the input process by setting `clearable`. Need to reference the `Icon` component

:::demo
```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        showIcon: '',
        clear: '',
    })
  return (
    <>
       <Input
          label="Text" 
          placeholder="Show Icon" 
          defaultValue={state.showIcon}
          leftIcon="dongdong"
          rightIcon="ask2"
        />
        <Input
          label="Text" 
          placeholder="Show Clear Icon"
          defaultValue={state.clear}
          clearable
          clearSize="14"
        />
    </>
  )
}
export default App;
```
:::

### Error Info

`:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        required: '',
        error1: '',
        error2: '',
    })
  return (
    <>
       <Input
          label="Text" 
          placeholder="Required" 
          defaultValue={state.required}
          required
        />
        <Input
          label="Text" 
          placeholder="Error"
          defaultValue={state.error1}
          error
        />
         <Input
          label="Text" 
          placeholder="Error Message"
          defaultValue={state.error2}
          errorMessage="Error Message"
        />
    </>
  )
}
export default App;
```
:::

### Insert Button

:::demo

```tsx
import  React, { useState } from "react";
import { Input, Button } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        buttonVal: '',
    })
  
  return (
    <>
       <Input
          label="Code"
          placeholder="Please enter code"
          defaultValue={state.buttonVal}
          clearable
          center
          slotButton={<Button size="small" type="primary">Send</Button>}
        />
    </>
  )
}
export default App;
```
:::

### Format Value

:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        format1: '',
        format2: '',
    })
    const formatter = (value: string) => value.replace(/\d/g, '')
  return (
    <>
       <Input
          label="Text"
          placeholder="Format On Change"
          defaultValue={state.format1}
          formatter={formatter}
        />
        <Input
          label="Text"
          placeholder="Format On Blur"
          defaultValue={state.format2}
          formatter={formatter}
          formatTrigger="onBlur"
        />
    </>
  )
}
export default App;
```
:::

### Show Word Limit

:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        textarea: '',
    })
  return (
    <>
       <Input
          label="Message"
          placeholder="Message"
          defaultValue={state.textarea}
          type="textarea"
          showWordLimit
          rows="2"
          maxlength="50"
        />
    </>
  )
}
export default App;
```
:::

### Input Align

:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        align1: '',
        align2: '',
    })
  return (
    <>
       <Input
          label="Text"
          placeholder="Label Align"
          defaultValue={state.align1}
          labelAlign="right"
        />
        <Input
          label="Text"
          placeholder="Input Align"
          defaultValue={state.align2}
          labelAlign="right"
        />
    </>
  )
}
export default App;
```
:::

### No Border

:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        noBorder1: '',
        noBorder2: '',
    })
  return (
    <>
       <Input
          label="No Border"
          defaultValue={state.noBorder1}
          placeholder="No Border"
          border={false}
        />
        <Input
          label="No Border"
          defaultValue={state.noBorder2}
          placeholder="No Border"
          border={false}
        />
    </>
  )
}
export default App;
```
:::

### Click Event

:::demo

```tsx
import  React, { useState } from "react";
import { Input } from '@nutui/nutui-react';

const App = () => {
    const  [state, setState] = useState({
        event:'',
    })
    const change = (value: string | number) => {
        console.log('change: ', value)
    }
    const focus = (value: string | number, event: Event) => {
        console.log('focus:', value, event)
    }
    const blur = (value: string | number, event: Event) => {
        console.log('blur:', value, event)
    }
    const clear = (value: string | number, event: Event) => {
        console.log('clear:', value, event)
    }
    const click = (value: string | number) => {
        console.log('click:', value)
    }
    const clickInput = (value: string | number) => {
        console.log('clickInput:', value)
    }
    const clickLeftIcon = (value: string | number) => {
        console.log('clickLeftIcon:', value)
    }
    const clickRightIcon = (value: string | number) => {
        console.log('clickRightIcon:', value)
    }
  return (
    <>
       <Input
          label="Click"
          placeholder="Click"
          defaultValue={state.event}
          leftIcon="dongdong"
          rightIcon="ask2"
          clearable
          onChange={change}
          onFocus={focus}
          onBlur={blur}
          onClear={clear}
          onClick={click}
          onClickInput={clickInput}
          onClickLeftIcon={clickLeftIcon}
          onClickRightIcon={clickRightIcon}
        />
    </>
  )
}
export default App;
```
:::
### Prop

| Attribute         | Description                                   | Type           | Default  |
| ------------ | -------------------------------------- | -------------- | ------- |
| defaultValue | Input value                   | string         | -       |
| type         | Input type, support all native types and `textarea` `number` `digit` type    | string         | `text`  |
| name`v1.3.10`  | Used for form submission to obtain data | string         | -       |
| ref`v1.3.10`  | Used to obtain internal input instance ref | RefAttributes         | -       |
| placeholder  | Placeholder when the input box is empty         | string         | -       |
| label        | Left text                               | string         | -       |
| labelClass  | Left text extra class name                      | string | -  |
| labelWidth  | Label width, default unit is `px`            | string \| number | `80`    |
| labelAlign  | Label align,  eg `left`、`center`、`right`   | string | `left` |
| inputAlign  | Input align, eg `left`、`center`、`right` | string | `left` |
| colon        | Whether to display colon after label     | boolean        | `false` |
| required     | Whether to show required mark            | boolean        | `false` |
| border       | Whether to show inner borde         | boolean        | `true` |
| disabled     | Whether to disable field            | boolean        | `false` |
| readonly     | Whether to be readonly              | boolean        | `false` |
| autofocus    | Whether to auto focus, unsupported in iOS     | boolean        | `false` |
| maxlength   | Max length of value                  | string \| number  | -       |
| clearable    | Whether to be clearable              | boolean        | `false`  |
| clearIcon   | Clear Icon name, [name of icon](#/icon)           | string        | `mask-close`  |
| clearSize   | Clear Icon `font-size`               | string        | `14`  |
| leftIcon    | Left side Icon name, [name of icon](#/icon) | string        | - |
| rightIcon   | Right side Icon name, [name of icon](#/icon) | string        | - |
| leftIconSize    | Left side Icon `font-size`    | string        | `14`  |
| rightIconSize   | Right side Icon `font-size`   | string        | `14`  |
| showWordLimit | Whether to show word limit, need to set the `max-length` prop | boolean | `false`  |
| error         | Whether to mark the input content in red   | boolean | `false`  |
| errorMessage | Error message            | string \| number | - |
| errorMessageAlign | Error message align, eg `left`、`center`、`right`          | string | - |
| formatter      | Input value formatter    | `(val: string) => string` | - |
| formatTrigger | When to format value, eg `onChange`、`onBlur` | string | - |

### Events

| Event   | Description      | Arguments    |
|--------|----------------|-------------|
| onChange `v1.3.8` | Emitted when input value changed | `val, event`  |
| onFocus `v1.3.8`  | Emitted when input is focused     | `val, event` |
| onBlur `v1.3.8`   | Emitted when input is blurred     | `val, event`  |
| onClear `v1.3.8` | Emitted when the clear icon is clicked   | `val, event`  |
| onClick `v1.3.8`  | Emitted when component is clicked	      | `val, event`  |
| onClickInput `v1.3.8`      | Emitted when the input is clicked      | `val, event`  |
| onClickLeftIcon `v1.3.8`  | Emitted when the left icon is clicked      | `val, event`  |
| onClickRightIcon `v1.3.8` | Emitted when the right icon is clicked      | `val, event`  |

### Slots

| Name  | Description     | 
|-------|----------|
| slotButton | Insert button |
| slotInput `v3.1.22` | Custom input |

## Theming

### CSS Variables

The component provides the following CSS variables, which can be used to customize styles. Please refer to [ConfigProvider component](#/en-US/component/configprovider).

| Name | Default Value |
| --- | --- |
| --nutui-input-border-bottom | `#eaf0fb` |
| --nutui-input-disabled-color | `#c8c9cc` |
| --nutui-input-required-color | `$required-color` |
| --nutui-input-font-size | `$font-size-2` |
| --nutui-input-padding | `10px 25px` |
| --nutui-inputnumber-icon-color | `$title-color` |
| --nutui-inputnumber-icon-void-color | `$disable-color` |
| --nutui-inputnumber-icon-disabled-color | `$gray2` |
| --nutui-inputnumber-icon-size | `20px` |
| --nutui-inputnumber-input-font-size | `12px` |
| --nutui-inputnumber-input-font-color | `$gray1` |
| --nutui-inputnumber-input-background-color | `$gray4` |
| --nutui-inputnumber-input-border-radius | `4px` |
| --nutui-inputnumber-input-width | `40px` |
| --nutui-inputnumber-input-margin | `0 6px` |
| --nutui-inputnumber-input-border | `0` |
| --nutui-inputnumber-border | `0` |
| --nutui-inputnumber-border-radius | `0` |
| --nutui-inputnumber-height | `auto` |
| --nutui-inputnumber-line-height | `normal` |
| --nutui-inputnumber-border-box | `content-box` |
| --nutui-inputnumber-display | `flex` |
