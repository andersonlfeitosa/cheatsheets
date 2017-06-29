## SVN 


This is a little cheatsheet about [SVN](https://subversion.apache.org).

### Checkout (over http)
```
svn co http://192.168.33.11/svn/repo/trunk/code
```

### Commit
```
svn commit -m "my first commit"
```

### Create tag
```
svn copy -r revision_number --pin-externals http://192.168.33.11/svn/repo/trunk/code http://192.168.33.11/svn/repo/tags/v1.0.0 -m message_tag
```

### Create branch
```
svn copy --pin-externals http://192.168.33.11/svn/repo/tags/v1.0.0 http://192.168.33.11/svn/repo/branches/v1.0.1 -m message_tag
```

### List externals files
```
svn propget svn:externals -R my_working_copy
```

### Create external file
```
svn propset svn:externals "http://192.168.33.11/svn/repo/trunk/code/common common" my_working_copy/common
```

### Delete external file
```
svn propdel svn:externals my_working_copy/dir
```

