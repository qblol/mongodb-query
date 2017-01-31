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
db.student.find()
```

output:

```

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

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```

## 1 . Membuat database academic.
input:
```
use academic
```
output:
```
switched to db academic
```
