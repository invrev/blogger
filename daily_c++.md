#### C++ resources

http://www.parashift.com/c++-faq-lite/ctors.html
http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml#Smart_Pointers
http://google-styleguide.googlecode.com/svn/trunk/

#### 
    * difference between pass by value and pass by reference
    * Motivation to use the pass by reference some one wants 
to use the string of 500MB in the program and system have only 600MB of space.

### use vector

* copy an array to a vector
 `vector<int> input_vec (arr,arr + sizeof(arr)/sizeof(arr[0]));`

### use stack 
    `(push,top,pop)`

### use queue 
    *`(push (inserted at back),front (last element),pop)`

### use algorithm

* in-place increasing sort
`sort (input_vec.begin(),input_vec.end())`

### use string (NOTE : unlike JAVA,strings are immutable)

* get the substring
substr(pos,length)

* sort the string
    in-place sorting
    eg. string single_str
    `sort(single_str.begin(),single_str.end());`

* map in c++

* declaration
    `map<string,string> str_map;`
    
* most used interfaces 
    find : to check wheather element is exist or not
    
    `if (str_map.find(element_key) == str_map.end() ) {
        //element_key not found    
    } else {
        str_map[element_key] = "found"; add the element
    }`

* Use of iterator

* appending one vector to other
    
    `first_vec.insert(first_vec.end(), second_vec.begin(), second_vec.end());`
    
#### Get the symbol table for the debugging
    `g++ -g <file_name.cpp>`
    



