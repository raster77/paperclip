# Build a deb package after a make

### 1 - Create a directory \<package>_\<version>-1_\<arch>

`
mkdir mypackage_1.0-1_amd64
`

### 2 - Run this command to install in the previous directory :

`
make DESTDIR=mypackage_1.0-1_amd64 install
`

### 3 - Create a directory **DEBIAN**

`mkdir mypackage_1.0-1_amd64/DEBIAN`

### 4 - Create a file **control** in DEBIAN directory

`touch mypackage_1.0-1_amd64/DEBIAN/control`

### 6 - Edit *control* and add those lines

* Package: \<package name>
* Version: \<version>
* Description: \<descrition>
* Architecture: \<arch>
* Maintainer: \<maintainer name>
* Section: \<In wich section>
* Priority: \<A priority>

### 7 - Build the package

`dpkg-deb --build --root-owner-group \<directory created at step 1>`
