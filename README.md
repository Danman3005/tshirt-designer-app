import React, { useState } from 'react';
import { View, Text, TextInput, Button, Image, TouchableOpacity } from 'react-native';
import { SafeAreaView } from 'react-native-safe-area-context';
import { StyleSheet } from 'react-native';

export default function App() {
  const [text, setText] = useState('');
  const [designText, setDesignText] = useState('');

  return (
    <SafeAreaView style={styles.container}>
      <Text style={styles.logo}>[Logo Platzhalter]</Text>

      <Text style={styles.title}>T-Shirt Designer</Text>

      <TextInput
        style={styles.input}
        placeholder="Text für das Shirt..."
        value={text}
        onChangeText={setText}
      />

      <Button title="Text hinzufügen" onPress={() => setDesignText(text)} />

      <View style={styles.shirtArea}>
        <Image source={require('./shirt.png')} style={styles.shirtImage} />
        <Text style={styles.designText}>{designText}</Text>
      </View>

      <TouchableOpacity style={styles.saveButton}>
        <Text style={styles.saveButtonText}>Design speichern</Text>
      </TouchableOpacity>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    backgroundColor: '#e6f2ff', // hellblau
    padding: 20,
  },
  logo: {
    fontSize: 18,
    marginBottom: 10,
    color: '#4b0082', // lila
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    color: '#003366', // dunkelblau
    marginBottom: 20,
  },
  input: {
    borderColor: '#90ee90', // hellgrün
    borderWidth: 1,
    padding: 10,
    width: '100%',
    marginBottom: 10,
  },
  shirtArea: {
    marginTop: 20,
    width: '100%',
    height: 300,
    alignItems: 'center',
    justifyContent: 'center',
    position: 'relative',
  },
  shirtImage: {
    width: 250,
    height: 250,
    resizeMode: 'contain',
  },
  designText: {
    position: 'absolute',
    fontSize: 20,
    color: '#4b0082', // lila
    fontWeight: 'bold',
  },
  saveButton: {
    marginTop: 20,
    backgroundColor: '#4b0082',
    padding: 10,
    borderRadius: 10,
  },
  saveButtonText: {
    color: '#fff',
    fontWeight: 'bold',
  },
});