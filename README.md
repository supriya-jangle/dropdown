import 'package:flutter/material.dart';
void main() => runApp(MyApp());
class MyApp extends StatelessWidget {
 @override
 Widget build(BuildContext context) {
 return MaterialApp(
 home: DropdownButtonDemo(),
 );
 }
}
class DropdownButtonDemo extends StatefulWidget {
 @override
 _DropdownButtonDemoState createState() => _DropdownButtonDemoState();
}
class _DropdownButtonDemoState extends State<DropdownButtonDemo> {
 String dropdownValue = 'One'; // Initial value of the dropdown
 @override
 Widget build(BuildContext context) {
 return Scaffold(
 appBar: AppBar(title: Text('DropdownButton Example')),
 body: Center(
 child: DropdownButton<String>(
 value: dropdownValue, // Current selected value
 onChanged: (String? newValue) {
 setState(() {
 dropdownValue = newValue!; // Update selected value
 });
 },
 items: <String>['One', 'Two', 'Three', 'Four']
 .map<DropdownMenuItem<String>>((String value) {
 return DropdownMenuItem<String>(
 value: value,
 child: Text(value),
 );
 }).toList(),
 ),
 ),
 );
 }
}


