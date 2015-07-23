These guidelines build on top of [Github Objective-C Code Guidelines](https://github.com/github/objective-c-style-guide), the following guidelines are all **Mandantory**, you can follow Github's guideline if it is not contray to iCHEF guidelines.
 
## Code Naming

 * All iCHEF POS class uses `iC`
 
 ```objc
 	iCSocketContainer *socket = [iCSocketContainer createSocket];
 ```
 
 * **No Abbreviations** for noun, verb, or adjective in class, method, or variable names.
 * Only Dictionary variables use the following abbreviation. Mutable or immutable collections are the same.
 
```objc
	NSDictionary *testDict;
	NSMutableDictionary *testDict;
	NSArray *testArray;
	NSMutableArray *testArray;
	NSSet *testSet;
	NSMutableSet *testSet;
```
* All boolean Variables start with **is** prefix.
```objc
	BOOL isEdited;
```
* All String variables ends with **String** suffix.
```objc
	NSString *testString;
```

* All String variables can be converted to JSON ends with **JSONString** suffix.
```objc
	NSString *testJSONString = @"{"test":"test"}";
	[testJSONString toJSON];
```

## Documentation and Organization

 * All method declarations should be documented.
 * All public method should use [VVDocumenter](https://github.com/onevcat/VVDocumenter-Xcode) to declare design intention, return type, and parameters in the header file.
 * All method declareations should have not null or nullable.
 ```objc
	- (nullable returnType *)itemWithName:(nonnull NSString *)parameter; 

 ```
 * All non-null property should be specified. Otherwise, nullable is the default.
 
  ```objc
	@property (copy, nonnull) NSArray *allItems;
  ```
  
 * Use `#pragma mark - ` to categorize methods into functional groupings and protocol implementations, following this general structure:

```objc
#pragma mark - Lifecycle

	+ (instancetype)objectWithThing:(id)thing {}
	- (instancetype)init {}
	- (void)viewDidLoad {}
	- (void)dealloc{}

#pragma mark - Other methods

	- (void)drawRect:(CGRect) {}
```
 * If a method call is too long, press **Enter** in the header of method segment, just let Xcode to align vertically with **:**
 * All publlic methods or properties should be placed in .h files, all private methods or properties shoud be in .m files.

## Import Policy
 * Only import what you need in header file , reduce the duty of pch file.

## Object Literals

* All NSNumber, NSDictionary, and NSArray must use Object Literals.

```objc
	NSNumber *orderCount = @(1 + 2);
```

```objc
 	NSDictionary *testDict = @{obj1, obj2, obj3};
```

```objc
 	NSArray *orderArray = @[obj1, obj2, obj3];
```

## Control Structures
 * Use ternary operators to help value assignment.
 * Long form ternary operators should be wrapped in parentheses and only used for assignment and arguments.

```objc
	Blah *a = (stuff == thing ? foo : bar);
```

* Short form, `nil` coalescing ternary operators should avoid parentheses.

```objc
	Blah *b = thingThatCouldBeNil ?: defaultValue;
```
* Comparisons should be explicit for everything except BOOLs.

```objc
	if (isEdited) {
		// Bool comparison
 	}
```

```objc
 	if (count >= 3) {
 		//number comparison
 	}
```

## Categories

 * Categories should be named for the sort of functionality they provide. Don't create umbrella categories.
