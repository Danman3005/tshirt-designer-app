import React, { useState } from 'react';
import { View, Text, TextInput, Button, StyleSheet } from 'react-native';

export default function App() {
  const [text, setText] = useState('');
  const [designText, setDesignText] = useState('');

  return (
    <View style={styles.container}>
      <Text style={styles.title}>T-Shirt Designer</Text>

      <TextInput
        style={styles.input}
        placeholder="Text für das Shirt..."
        value={text}
        onChangeText={setText}
      />

      <Button title="Text anzeigen" onPress={() => setDesignText(text)} />

      <View style={styles.shirtPreview}>
        <Text style={styles.shirtText}>{designText}</Text>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#e6f2ff',
    alignItems: 'center',
    justifyContent: 'center',
    padding: 20,
  },
  title: {
    fontSize: 28,
    color: '#4b0082',
    marginBottom: 20,
  },
  input: {
    borderWidth: 1,
    borderColor: '#90ee90',
    padding: 10,
    width: '100%',
    marginBottom: 20,
    borderRadius: 8,
  },
  shirtPreview: {
    marginTop: 40,
    width: 200,
    height: 200,
    backgroundColor: '#ffffff',
    borderWidth: 2,
    borderColor: '#003366',
    alignItems: 'center',
    justifyContent: 'center',
  },
  shirtText: {
    fontSize: 20,
    color: '#003366',
    fontWeight: 'bold',
  },
});