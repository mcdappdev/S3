# S3 library for Vapor
Basic S3 access library for Vapor written in Swift


### Install

1) Add following package to your ```Package.swift```:
``` Swift
.Package(url: "https://github.com/manGoweb/S3.git", majorVersion: 0, minor: 1)
```

2) Run ```vapor clean```
3) Do ```vapor xcode```

### Usage

Import the module ```import S3```

#### Get data from S3

``` Swift
let s3: S3 = try S3(droplet: drop)
let fileData: Data = try s3.get(fileAtPath: "images/image.png", bucketName: "booststore")
```

#### Upload data to S3

``` Swift
let s3: S3 = try S3(droplet: drop)
let url = URL.init(fileURLWithPath: "/Users/pro/Dropbox/books/agile-android-software-development.pdf")
try s3.put(fileAtUrl: url, filePath: "books/agile-android-software-development.pdf", bucketName: "booststore", accessControl: .publicRead)
```

#### Delete data from S3

``` Swift
let s3: S3 = try S3(droplet: drop)
try s3.delete(fileAtPath: "images/image.png", bucketName: "booststore")
```

### Troubleshooting

##### I am getting a ```badResponse``` error and my credentials are correct
* Check if you don't need to set your region, it's one of the optional methods on all put methods
