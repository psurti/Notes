#### Tutorials
https://javascript.info/   


#### JSON number limitations
https://cdivilly.wordpress.com/2012/04/11/json-javascript-large-64-bit-integers/   
https://www.techempower.com/blog/2016/07/05/mangling-json-numbers/   
https://codeburst.io/throttling-and-debouncing-in-javascript-b01cad5c8edf#.ly8uqz8v4   
https://javascript.info/   

#### JS Object mutablility prevention
https://ourcodeworld.com/articles/read/167/how-to-prevent-modification-of-an-object-in-javascript-and-prevent-them-from-being-accesible-in-the-console   

##### JS Engines
https://www.freecodecamp.org/news/javascript-under-the-hood-v8/   
https://duktape.org/   

##### prebuilt v8
https://rubygems.org/gems/libv8     
```
# Find the appropriate gem version for your OS,
# visit: https://rubygems.org/gems/libv8/versions

# Download the gem
# MacOS Sierra is darwin-16, for v8 6.3.292.48.1 it looks like:
curl https://rubygems.org/downloads/libv8-6.3.292.48.1-x86_64-darwin-16.gem > libv8.gem

# Extract the gem (it's a tarball)
tar -xf libv8.gem

# Extract the `data.tar.gz` within
cd libv8-6.3.292.48.1-x86_64-darwin-16
tar -xzf data.tar.gz

# Symlink the compiled libraries and includes
ln -s $(pwd)/data/vendor/v8/include $GOPATH/src/github.com/augustoroman/v8/include
ln -s $(pwd)/data/vendor/v8/out/x64.release $GOPATH/src/github.com/augustoroman/v8/libv8

# Run the tests to make sure everything works
cd $GOPATH/src/github.com/augustoroman/v8
go test
```
