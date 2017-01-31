# mongodb-query

## 1 . Membuat database academic.

input:

```
use academic
```

output:

```
switched to db academic
```

## 2 . Menampilkan semua collection dan data dalam database.

input:

```
show collections
```

output:

```
departments
students
system.indexes
```

## 3 . Membuat atau mengaktifkan database.

input:

```
use academic
```

output:

```
switched to db academic
```

## 4 . Membuat collection department.

input:

```
db.createCollection("department")
```

output:

```
{ "ok" : 1 }
```

## 5 . Membuat collection student.

input:

```
db.createCollection("student")
```

output:

```
{ "ok" : 1 }
```

## 6 . Melihat struktur collection student.

input:

```
var student = db.students.findOne();
for (var key in student) { print (key) ; }
```

output:

```
_id
NIM
name
address
department
```

## 7 . Menginputkan 5 data ke dalam collection department.

input:

```
db.departments.insert([{code:"FTTM",name:"Fakultas Teknik Pertambangan dan Perminyakan",major:[{name:"Teknik Perminyakan"},{name:"Teknik Pertambangan"},{name:"Teknik Metalurgi"}]},{code:"FITB",name:"Fakultas Ilmu dan Teknologi Kebumian",major:[{name:"Teknik Geologi"},{name:"Teknik Geodesi dan Geomatika"},{name:"Oseanografi"}]},{code:"FMIPA",name:"Fakultas Matematika dan Ilmu Pengetahuan Alam",major:[{name:"Matematika"},{name:"Fisika"},{name:"Astronomi"}]},{code:"SAPPK",name:"Sekolah Arsitektur dan Perencanaan Kota",major:[{name:"Arsitektur"},{name:"Teknik Planologi"}]},{code:"SF",name:"Sekolah Farmasi",major:[{name:"Farmasi Klinik"},{name:"Farmasi Kmunitas"}]}])
```

output:

```
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 5,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
```

## 8 . Menginputkan 3 data ke dalam collection student beserta reference ke department.

input:

```
db.students.insert([{NIM:"15109063",name:"Muhammad Iqbal",address:"Margahayu Raya Bandung",department:{$ref:"departments",$id:ObjectId("58901b4e69a01ac6a294a3aa")}},{NIM:"16109063",name:"Raditya Arya",address:"Gatsu Surabaya",department:{$ref:"departments",$id:ObjectId("58901b4e69a01ac6a294a3a8")}},{NIM:"17109021",name:"Timothy Ombun",address:"Soekarno Hatta Batam",department:{$ref:"departments",$id:ObjectId("58901b4e69a01ac6a294a3ab")}}])
```

output:

```
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 3,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
```

## 9 . Melihat isi collection student.

input:

```
db.students.find()
```

output:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "NIM" : "15109063", "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung", "department" : DBRef("departments",
 ObjectId("58901b4e69a01ac6a294a3aa")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3ae"), "NIM" : "16109063", "name" : "Raditya Arya", "address" : "Gatsu Surabaya", "department" : DBRef("departments", ObjectId(
"58901b4e69a01ac6a294a3a8")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3af"), "NIM" : "17109021", "name" : "Timothy Ombun", "address" : "Soekarno Hatta Batam", "department" : DBRef("departments", Ob
jectId("58901b4e69a01ac6a294a3ab")) }
```

## 10 . Menampilkan key name dan address dalam collection student.

input:

```
db.students.find({},{name:1, address:1})
```

output:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung" }
{ "_id" : ObjectId("58901e6769a01ac6a294a3ae"), "name" : "Raditya Arya", "address" : "Gatsu Surabaya" }
{ "_id" : ObjectId("58901e6769a01ac6a294a3af"), "name" : "Timothy Ombun", "address" : "Soekarno Hatta Batam" }
```

## 11 . Menampilkan key NIM, name, dan address dari data student yang memunyai NIM tertentu.

input:

```
db.students.find({NIM:"15109063"},{NIM:1, name:1, address:1})
```

output:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "NIM" : "15109063", "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung" }
```

## 12 . Menampilkan semua data student secara urut berdasarkan name dengan sort() secara ascending maupun ascending.

input:

```
db.students.find().sort({name:1}) // ascending
db.students.find().sort({name:-1}) // descending
```

output ascending:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "NIM" : "15109063", "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung", "department" : DBRef("departments",
 ObjectId("58901b4e69a01ac6a294a3aa")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3ae"), "NIM" : "16109063", "name" : "Raditya Arya", "address" : "Gatsu Surabaya", "department" : DBRef("departments", ObjectId(
"58901b4e69a01ac6a294a3a8")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3af"), "NIM" : "17109021", "name" : "Timothy Ombun", "address" : "Soekarno Hatta Batam", "department" : DBRef("departments", Ob
jectId("58901b4e69a01ac6a294a3ab")) }
```

output descending:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3af"), "NIM" : "17109021", "name" : "Timothy Ombun", "address" : "Soekarno Hatta Batam", "department" : DBRef("departments", Ob
jectId("58901b4e69a01ac6a294a3ab")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3ae"), "NIM" : "16109063", "name" : "Raditya Arya", "address" : "Gatsu Surabaya", "department" : DBRef("departments", ObjectId(
"58901b4e69a01ac6a294a3a8")) }
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "NIM" : "15109063", "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung", "department" : DBRef("departments",
 ObjectId("58901b4e69a01ac6a294a3aa")) }
```

## 13 . Menampilkan semua data department secara urut berdasarkan name secara ascending maupun descending.

input:

```
db.departments.find().sort({name:1}) // ascending
db.departments.find().sort({name:-1}) // descending
```

output ascending:

```
{ "_id" : ObjectId("58901b4e69a01ac6a294a3a9"), "code" : "FITB", "name" : "Fakultas Ilmu dan Teknologi Kebumian", "major" : [ { "name" : "Teknik Geologi" }, { "name" :
"Teknik Geodesi dan Geomatika" }, { "name" : "Oseanografi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3aa"), "code" : "FMIPA", "name" : "Fakultas Matematika dan Ilmu Pengetahuan Alam", "major" : [ { "name" : "Matematika" }, { "na
me" : "Fisika" }, { "name" : "Astronomi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3a8"), "code" : "FTTM", "name" : "Fakultas Teknik Pertambangan dan Perminyakan", "major" : [ { "name" : "Teknik Perminyakan" },
 { "name" : "Teknik Pertambangan" }, { "name" : "Teknik Metalurgi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3ab"), "code" : "SAPPK", "name" : "Sekolah Arsitektur dan Perencanaan Kota", "major" : [ { "name" : "Arsitektur" }, { "name" :
"Teknik Planologi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3ac"), "code" : "SF", "name" : "Sekolah Farmasi", "major" : [ { "name" : "Farmasi Klinik" }, { "name" : "Farmasi Kmunitas" } ]
}
```

output descending:

```
{ "_id" : ObjectId("58901b4e69a01ac6a294a3ac"), "code" : "SF", "name" : "Sekolah Farmasi", "major" : [ { "name" : "Farmasi Klinik" }, { "name" : "Farmasi Kmunitas" } ]
}
{ "_id" : ObjectId("58901b4e69a01ac6a294a3ab"), "code" : "SAPPK", "name" : "Sekolah Arsitektur dan Perencanaan Kota", "major" : [ { "name" : "Arsitektur" }, { "name" :
"Teknik Planologi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3a8"), "code" : "FTTM", "name" : "Fakultas Teknik Pertambangan dan Perminyakan", "major" : [ { "name" : "Teknik Perminyakan" },
 { "name" : "Teknik Pertambangan" }, { "name" : "Teknik Metalurgi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3aa"), "code" : "FMIPA", "name" : "Fakultas Matematika dan Ilmu Pengetahuan Alam", "major" : [ { "name" : "Matematika" }, { "na
me" : "Fisika" }, { "name" : "Astronomi" } ] }
{ "_id" : ObjectId("58901b4e69a01ac6a294a3a9"), "code" : "FITB", "name" : "Fakultas Ilmu dan Teknologi Kebumian", "major" : [ { "name" : "Teknik Geologi" }, { "name" :
"Teknik Geodesi dan Geomatika" }, { "name" : "Oseanografi" } ] }
```


## 14 . Mencari data student dengan name.

input:

```
db.students.find({name:"Muhammad Iqbal"})
```

output:

```
{ "_id" : ObjectId("58901e6769a01ac6a294a3ad"), "NIM" : "15109063", "name" : "Muhammad Iqbal", "address" : "Margahayu Raya Bandung", "department" : DBRef("departments",
 ObjectId("58901b4e69a01ac6a294a3aa")) }
```
