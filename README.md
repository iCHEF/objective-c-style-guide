These guidelines build on top of [Github Objective C Code Guidelines](https://github.com/github/objective-c-style-guide), the following guidelines are all **Mandantory**, you can follow Github's guideline if it is not contray to iCHEF guidelines.
 
## Code Naming

 * All iCHEF POS class uses `iC`
 	* iCSocketContainer
 * **No Abbreviation** for noun, verb, or adjective in class or method name.

## Documentation and Organization

 * All method declarations should be documented.
 * All public method should use [VVDocumenter](https://github.com/onevcat/VVDocumenter-Xcode) to declare design intention, return type, and parameters in the header file.
 * All method declareations should have not null or nullable.
 ```objc
	- (nullable returnType *)itemWithName:(nonnull NSString *)parameter; 

 ```
 
 * Use `#pragma mark`s to categorize methods into functional groupings and protocol implementations, following this general structure:

```objc
#pragma mark Lifecycle

+ (instancetype)objectWithThing:(id)thing {}
- (instancetype)init {}
- (void)viewDidLoad {}
- (void)dealloc{}

#pragma mark Other methods

- (void)drawRect:(CGRect) {}
```

