## to download multiple files simultaniously with parallel

#### 
`parallel` is available in linux that allows N parallel programs to run. 

-j8 is used, where N in -jN which N numbers of cores will be utilized for download operation.

```
cat url-list | parallel -j8 wget {}

Alternatively,
cat url-list | parallel -j8 wget ' ' {}
```

`cat` is reading the file with URLs to download. `file.txt` could look like:

```
https://XXX/all/Packages/a/abrt-2.10.9-20.el8.x86_64.rpm
https://XXX/all/Packages/a/abrt-addon-vmcore-2.10.9-20.el8.x86_64.rpm
....
```

The output is then piped to parallel that is responsible for spinning multiple wgets (-jN decide how many). The {} is piped input line.