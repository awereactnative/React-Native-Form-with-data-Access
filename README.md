# React-Native-Form-with-data-Access

# Introduction

  Forms are an interactive part of our website or product UI. Feedback, surveys, data collection, etc., are critical aspects of your product that require extensive use of forms. If you don’t get your forms right, you might be unknowingly providing your users with a bad experience, which can lead to a drastic reduction in the use of your product.
  
# Demo 
![Form](https://user-images.githubusercontent.com/86215353/181409999-6b7b3fe2-42fd-4e92-b384-6be4ef13e3ca.gif)



# Installation

```
npm i react-native-mask-text
```
```
npm i react-native-paper
```

# Example
```js

import * as React from 'react';
import { Text, View, StyleSheet, TextInput, Button } from 'react-native';
import Constants from 'expo-constants';

import { Card } from 'react-native-paper';
import { MaskedTextInput } from 'react-native-mask-text';

export default function App() {
  const [form, setForm] = React.useState({
    name: '',
    email: '',
    Expected_Salary: '',
    DOB: '',
  });

  const handleForm = (key, value) => {
    setForm((currentForm) => ({
      ...currentForm,
      [key]: value,
    }));
  };

  const submitForm = () => {
    console.log('submit this form =>', JSON.stringify(form, false, 2));
  };

  return (
    <View style={styles.container}>
      <Text style={styles.paragraph}>Simple Form With Console Log Output</Text>
      <Card style={styles.card}>
        <Text style={styles.label}>Full Name</Text>
        <TextInput
          style={styles.input}
          id="nome"
          name="name"
          placeholder="Ex.: Just A Varibale"
          onChangeText={(value) => handleForm('name', value)}
        />

        <Text style={styles.label}>Email</Text>
        <TextInput
          style={styles.input}
          name="email"
          placeholder="Ex.: variable@domain.com"
          onChangeText={(value) => handleForm('email', value)}
        />

        <Text style={styles.label}>Expected Salary</Text>
        <MaskedTextInput
          type="currency"
          options={{
            prefix: '$',
            decimalSeparator: '.',
            groupSeparator: ',',
            precision: 2,
          }}
          onChangeText={(value) => handleForm('Expected_Salary', value)}
          keyboardType="numeric"
          style={styles.input}
        />

        <Text style={styles.label}>Date of Birth</Text>
        <MaskedTextInput
          mask="99/99/9999"
          placeholder="MM/DD/YYYY"
          onChangeText={(value) => handleForm('DOB', value)}
          keyboardType="numeric"
          style={styles.input}
        />
        <View style={styles.buttonContainer}>
          <Button title="submit" onPress={submitForm} />
        </View>
      </Card>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    paddingTop: Constants.statusBarHeight,
    backgroundColor: '#ecf0f1',
    padding: 8,
  },
  paragraph: {
    margin: 24,
    fontSize: 18,
    fontWeight: 'bold',
    textAlign: 'center',
  },
  card: {
    padding: 20,
    marginHorizontal: 20,
    justifyContent: 'center',
  },
  label: {
    fontSize: 12,
    marginTop: 5,
  },
  input: {
    height: 40,
    marginHorizontal: 0,
    marginVertical: 5,
    paddingHorizontal: 5,
    borderWidth: 1,
    borderRadius: 10,
  },
  buttonContainer: {
    marginTop: 10,
  },
});

```

# Tutorial

Coming Soon...d 
