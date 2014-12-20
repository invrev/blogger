#### C++ resources

http://www.parashift.com/c++-faq-lite/ctors.html
http://google-styleguide.googlecode.com/svn/trunk/cppguide.xml#Smart_Pointers
http://google-styleguide.googlecode.com/svn/trunk/

#### 
    * difference between pass by value and pass by reference
    * Motivation to use the pass by reference some one wants to use the string of 500MB in the program and system have only 600MB of space.

### use vector

* copy an array to a vector
 `vector<int> input_vec (arr,arr + sizeof(arr)/sizeof(arr[0]));`

* create 2-d vector
`declare 2-d vector and init 2-d

    vector< vector <int> > t_d_vec (m,vector <int> (n));
`

`declare 2-d vector and init 1-d vector

    vector< vector <int> > t_d_vec (m);
    for (int i=0;i<m;i--) {
        t_d_vec [i].resize(n) ;
    }
`

### use stack 
    `(push,top,pop)`

### use queue 
    *`(push (inserted at back),front (last element),pop)`

### use algorithm

* in-place increasing sort
`sort (input_vec.begin(),input_vec.end())`

### use string (NOTE : unlike JAVA,strings are immutable)

* convert number to string
`use sstream
#include <sstream> 
ostringstream convert;   
convert << Number; 
string result = convert.str();`

* get the substring

`
eg. string input_str;
input_str.substr(pos,length)
`

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

* increasing the size of vector by n .
    `vecObj.resize(n)`

    
#### Get the symbol table for the debugging
    `g++ -g <file_name.cpp>`

#### Difference in logical operator (&&) and BitWise operator (&)

#### pointer arena
       
    in c++,Reference is an alias of a object.
    in c,reference is an memory location or 
    Though eventually in both cases it is an memory location.
    
    Difference between reference and pointer 
    Terminologies 
    1. Pointee : 
         A value
    2. Reference :
         A memory address 
         Use & operator to create the reference.
    3. Pointer  :
         a memory location that stores the address/reference of another variable/memory location.
    4. Dreferencing :
         operation that retrives the pointee from the given pointer
    5. Shallow and Deep copy
    
    6. Bad pointer
        uninitialized pointer/pointer with a garbage value.

    
    1. Rule of three (not from c++)
         1. Pointer must be allocated  
             eg. int *a = 0 or struct node *head = (struct node *) malloc (sizeof(struct node))
         2. Pointee must be allocated
            eg. int b = 10;
         3. A pointer must be assigned to point to pointee
            eg . a = &b;

    

##### Reference vs. pointers: 

`int& a = b;
int* a = &b;`
*  References are like pointers, except:
*  Must always be initialized where declared
*  Cannot be reassigned
*  Use . instead of -> to access fields and methods
*  Never need to use * to dereference, compiler will “do the right thing”
*  Cannot take address of reference variable, you get the address of the referenced object

#### constructor in the struct 
    Always values in the bracket are for assignement 
    `eg. TreeNode(int x) : val(x), left(NULL), right(NULL) {} `



### pointer sharing and cleaning
string * a = new string; // this allocates space to store a string, and a is pointing to it
string * b = a; // b to the same address as a does
delete b; // free up the space that both a and b were pointing to
delete a; // this will be an error, because the space that a was pointing to is already free
