# Translate php to golang
## Push in list
* php:
```php
$fruits = ['banana', 'orange'];
$fruits[] = ['apple'];

print_r($fruits);
```
* Golang
```golang
fruits := []string{"banana", "orange"}
fruits = append(fruits, "apple")

fmt.Println(fruits)
```
## Pop from list
* php
```php
$fruits = ['banana', 'orange', 'apple'];
array_pop($fruits);

print_r($fruits);
```
* Golang
```golang
fruits := []string{"banana", "orange", "apple"}
fruit, fruits := fruits[len(fruits)-1], fruits[:len(fruits)-1]

fmt.Println(fruits)
```
## List loop
* php
```php
$fruits = ['banana', 'orange', 'apple'];
foreach ($fruits as $index => $fruit) {
    echo $index.' '.$fruit.PHP_EOL;
}
```
* Golang
```golang
var fruits = []string{"banana", "apple"}
for index, fruit := range fruits {
    fmt.Println(index,fruit)
}
```
## Dictionaries
* php
```php
$person = [
    'name' => 'Hossein',
    'last_name' => 'Zeinali',
];
$person['gender'] = 'male';
foreach ($person as $key => $value) {
    echo $key.':'.$value.PHP_EOL;
}
```
* Golang
```golang
person := map[string]string{"name": "Hossein","last_name": "Zeinali"}
person["gender"] = "male"
for key, value := range person {
	println(key, ":", value)
}
```
## exits in list
* php
```php
$fruits = ['banana', 'orange', 'apple'];
$doesExist = in_array('orange', $fruits);
echo $doesExist.PHP_EOL;
```
* Golang
```golang
var fruits = []string{"banana", "orange", "apple"}
var doesExist = false
for _, fruit := range fruits {
    if fruit == "orange" {
        doesExist = true
        break
    }
}
println(doesExist)
```
## exists in dictionary
* php
```php
$person = [
    'name' => 'Hossein',
    'last_name' => 'Zeinali',
    'gender' => 'male',
];
$doesExist = isset($person['name']);
echo $doesExist.PHP_EOL;
```
* Golang
```golang
var person = map[string]string{"name": "Hossein","last_name": "Zeinali"}
_, ok := person["name"]
var doesExist = false
if ok {
	doesExist = true
}
println(doesExist)
```

## Class
* php
```php
class Person {
    public $name;
    public $lastName;
    
    public function __construct($name, $lastName) {
        $this->name = $name;
        $this->lastName = $lastName;
    }
    
    public function getFullName() {
        return $this->name.' '.$this->lastName;
    }
}
$person = new Person('Hossein', 'Zeinali');
echo $person->getFullName().PHP_EOL;
```
* Golang
```golang
type Person struct {
	name string
	lastName string
}

func (person *Person)getFullName() string  {
	return person.name+" "+person.lastName
}

func main() {
	var person = Person{
		name: "hossein",
		lastName: "Zeinali",
	}
	println(person.getFullName())
}
```