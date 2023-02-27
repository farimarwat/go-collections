#Go-Collections
Go functions to manipulate slices lists

### Available Functionality
1. Filter
2. Find
3. Map

More will come soon

### Setup:
Enter in terminal:


     go get -u github.com/farimarwat/go-collections

### Next Import



    import (
    	"fmt"
    
    	"github.com/farimarwat/go-collections"
    )

Asume that we have a Person struct type



    type Person struct {
    	Name string
    	Age  int
    }

Now asume that we have a list of Person type:



    list := make([]Person, 5)
    	list[0] = Person{Name: "Haris", Age: 18}
    	list[1] = Person{Name: "Aslam", Age: 30}
    	list[2] = Person{Name: "Rashid", Age: 21}
    	list[3] = Person{Name: "Zaid", Age: 12}
    	list[4] = Person{Name: "Zahid", Age: 13}

### Filter

    	p, err := gocollections.Filter(list, func(p Person) bool {
    		return p.Age > 15
    	})
		//below to check filtered list
    	if err != nil {
    		fmt.Println(err)
    	} else {
    		fmt.Println(p)
    	}

### Find



    p, err := gocollections.Find(list, func(p Person) bool {
    		return p.Name == "Zaid"
    	})
		  //below to check if element found
    	if err != nil {
    		fmt.Println(err)
    	} else {
    		fmt.Println(p)
    	}

### Map



    result := gocollections.Map(list,func(p Person) Person {
    		person := p
    		person.Age = 37
    		return person
    	})
    	fmt.Println(result)


