## installation


```sh
$ npm i react-native-chips-ui
```
or
```sh
$ yarn add react-native-chips-ui
```

## Examples

### Chip Component Example

```
variant types -> solid (default) , outlined , disabled
label -> "string"
```


```typescript
import React from "react";
import { StyleSheet } from "react-native";
import { Chip } from "react-native-chips-ui";

function App() {
  // Function to handle press events on chips
  const onChipItemPress = () => {
    console.log("pressed");
  };

  return (
    <>
      {/* Chip component for user input */}
      <Chip
        label="What's On Your Mind? "
        style={styles.chip}
        onPress={onChipItemPress}
      />

      {/* Disabled Chip component for deletion */}
      <Chip
        variant="disabled"
        label="Delete"
        style={styles.chip}
        onPress={onChipItemPress}
      />
    </>
  );
}

const styles = StyleSheet.create({
  chip: {
    alignSelf: "flex-start",
  },
});

export default App;

```

### Chips component example

```
itemVariant -> solid(default) , outline, disabled
```

```typescript
import React, { useState } from "react";
import { StyleSheet } from "react-native";
import { Chips } from "react-native-chips-ui";

function App() {
  // State to manage the list of available items for the Chips component
  const [items, setItems] = useState([
    { label: "Football", value: "1" },
    { label: "Cricket", value: "2" },
    { label: "Tennis", value: "3" },
    { label: "Table Tennis", value: "4" },
    { label: "Basketball", value: "5" },
    { label: "Swimming", value: "6" },
  ]);

  // State to manage the selected values in the Chips component
  const [selectedValues, setSelectedValues] = useState(["1", "2"]);

  return (
    <>
      {/* Chips component for displaying and selecting items */}
      <Chips
        type="filter"
        itemVariant="outlined"
        items={items}
        setItems={setItems}
        selectedValues={selectedValues}
        setSelectedValues={setSelectedValues}
      />
    </>
  );
}

const styles = StyleSheet.create({
  // Additional styles can be defined here if needed
});

export default App;

```