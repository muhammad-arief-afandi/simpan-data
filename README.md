# 
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Informasi(),
  ));
}

class Informasi extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Informasi Mahasiswa'),
      ),
      floatingActionButton: FloatingActionButton.extended(
          icon: Icon(Icons.add),
          label: Text('Input Data'),
          onPressed: () {
          // Navigasi ke rute kedua (Input Data).
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => InputData()),
            );
          }),
      body: ListView(
        children: ListTile.divideTiles(
          context: context,
          tiles: [
            ListTile(
              leading: Icon(Icons.people),
              title: Text("Muhammad arief afandi"),
              subtitle: Text("Laki-laki"),
              trailing: Text("Komputer"),
            ),
            ListTile(
              leading: Icon(Icons.people),
              title: Text("Mulia Dewi"),
              subtitle: Text("Perempuan"),
              trailing: Text("Ekonomi"),
            ),
          ],
        ).toList(),
      ),
    );
  }
}

class InputData extends StatelessWidget {
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Input Data Mahasiswa"),
      ),
      body: Container(
        padding: EdgeInsets.all(20.0),
        child: Column(
          children: [
            TextField(
              decoration: InputDecoration(labelText: "Input Nama Mahasiswa"),
            ),
            RadioListTile(
              title: Text('Laki-laki'),
              value: null,
              groupValue: null,
              onChanged: null,
            ),
            RadioListTile(
              title: Text('Perempuan'),
              value: null,
              groupValue: null,
              onChanged: null,
            ),
            DropdownButton(
              isExpanded: true,
              hint: Text('pilih jurusan'),
              items: null,
              onChanged: null,
            ),
            RaisedButton(
              child: Text("Simpan"),
              onPressed: () {},
            ),
          ],
        ),
      ),
    );
  }
}
