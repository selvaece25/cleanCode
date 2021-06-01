Code is clean if it can be understood easily – by everyone on the team. Clean code can be read and enhanced by a developer other than its original author. With understandability comes readability, changeability, extensibility and maintainability.
_____________________________________

## General rules
1. Follow standard conventions.
2. Keep it simple stupid. Simpler is always better. Reduce complexity as much as possible.
3. Boy scout rule. Leave the campground cleaner than you found it.
4. Always find root cause. Always look for the root cause of a problem.

## Design rules
1. Keep configurable data at high levels.
2. Prefer polymorphism to if/else or switch/case.
3. Separate multi-threading code.
4. Prevent over-configurability.
5. Use dependency injection.
6. Follow Law of Demeter. A class should know only its direct dependencies.

## Understandability tips
1. Be consistent. If you do something a certain way, do all similar things in the same way.
2. Use explanatory variables.
3. Encapsulate boundary conditions. Boundary conditions are hard to keep track of. Put the processing for them in one place.
4. Prefer dedicated value objects to primitive type.
5. Avoid logical dependency. Don't write methods which works correctly depending on something else in the same class.
6. Avoid negative conditionals.

## Names rules
1. Choose descriptive and unambiguous names.
2. Make meaningful distinction.
3. Use pronounceable names.
4. Use searchable names.
5. Replace magic numbers with named constants.
6. Avoid encodings. Don't append prefixes or type information.

#### Naming Integers : One of the most used categories of integer variables is a count or number of something
For example: numberOfFailures or failureCount

 I always add a unit description at the end of the variable name. For example, instead of tooltipShowDelay, I use tooltipShowDelayInMillis or even better **tooltipShowDelayInMillisecs**
 
#### Naming Floating-Point Numbers
If the unit of a variable is not clear, I add a unit description at the end of the variable name, like widthInCentimeters, rainFallAmountInInchesPerHour, angleInDegrees, failurePercent, or failureRatio.

#### Naming Booleans: Boolean variables can have only one of two values: true or false
I name boolean variables using patterns: isSomething, hasSomething, doesSomething, didSomething, shouldDoSomething or willDoSomething.
For example: isDisabled, hasErrors, allowsWhitespace, didUpdate, shouldUpdate, willUpdate

#### Naming Arrays, Lists, and Sets: When naming arrays, lists, or sets, I always use a plural form of a noun, like customers, errors, or tasks.

#### Naming Strings: 
Strings are very common and many entities are intrinsically strings, like name, title, city, or country. Sometimes when I need to store numerical data in strings, I want to tell the code reader clearly that it is a question about a number in string format and I use a variable name like <someValue>String or <someValue>AsString.

For example: **yearAsString**

#### Naming Pairs and Tuples
I name a pair using the pattern variable1AndVariable2

For example: 
const heightAndWidthInCentimeters: [number, number] = [100, 200]
const heightWidthAndDepthInCentimeters: [number, number, number] = [100, 200, 40]
const [heightInCentimeters,,depthInCentimeters] = heightWidthAndDepthInCentimeters

#### Naming Objects :
You can also freely decorate the object’s name with an adjective. For example: completedTask  
If possible, I try to avoid using object variable names that can be confused with a variable name for a string or a number. For example, instead of naming objects value or name, I use valueObject or nameObject.

For example: const { nameObject } = getPersonById(1234);
  
#### Naming Index on Loop:   
I don’t use loop iterator variable names like i or k. Rather I use the variable name index or <something>Index. 
For example: userIndex  
  
#### File Name:
The file name must be all lower case. It may include dashes(-) or underscores(_) but no other punctuation allowed.
File encoding type must be UTF-8.

#### Package Name:
Package names are all lowerCamelCase.
example: com.nodeSimplified.exampleCode.

#### Class Name:
Class names, interface names, typedef, and record names are all UpperCamelCase.
These names are always nouns or noun phrases.
example: ImmutableList.
 
### Frontend Naming your functions: 

##### FOR PROPS
When defining the prop names, I usually prefix with on*, as in onClick. This matches the built-in event handler convention. And by matching it, we declare that these props will house similarly-used event handler functions.

##### FOR FUNCTION NAMES
For the function names, I follow the exact same pattern, but I replace on with handle*, as in handleClick. Together, it’d look like: 
 
For example: <MyComponent onClick={handleClick} />

So on is describing what actual event this will be tied to. handle is describing what will be called when that event fires. 

#### Extract the unique values for the given key of each item in the array
 The map() method creates a new array with the results of calling a provided function on every element in the calling array.
 For example: 
 
 const listOfUserGroups = [...new Set(users.map(it => it.group))];
// listOfUserGroups is ['editor', 'admin'];
 
#### Create an object that contains the frequency of the specified key 
 const groupByAge = users.reduce((acc, it) => {
  acc[it.age] = acc[it.age] + 1 || 1;
  return acc;
}, {});
// groupByAge is {23: 1, 28: 2, 34: 1}
 
 
#### React | Vue naming convention:
1. Component’s names should be PascalCase ( Example: LoginScreen.js )
2. All other helper files should be camelCase. ( Example: commonUtils.js )
3. All the folder names should be camelCase. ( Example: components )
4. CSS files should be named the same as the component PascalCase. Global CSS which applies to all components should be placed in global.css and should be named in camelCase Example: LoginScreen.css(for components), global.css(for global styles)
 
## Functions rules
1. Small.
2. Do one thing.
3. Use descriptive names.
4. Prefer fewer arguments.
5. Have no side effects.
6. Don't use flag arguments. Split method into several independent methods that can be called from the client without the flag.

##### Methods naming: verb + noun pair works just fine for most of the cases: calculateTotal, getAverage, setColor, saveContent
  
##### Event handler: on + event name  (optionally with event target object) 

For example: onButtonClick, onClose, onAfterRender
  
Another common naming pattern I like is when iterating over items. When receiving the argument inside the function, use the singular version of the array name.
  
const **newFruits** = fruits.map(fruit => {
    return doSomething(fruit);
});
  
#### Transforming values
Prefixing function names with **to**
For example: 
toDollars('euros', 20);
toUppercase('a string');  
  
  
## Comments rules
1. Always try to explain yourself in code.
2. Don't be redundant.
3. Don't add obvious noise.
4. Don't use closing brace comments.
5. Don't comment out code. Just remove.
6. Use as explanation of intent.
7. Use as clarification of code.
8. Use as warning of consequences.

## Source code structure
1. Separate concepts vertically.
2. Related code should appear vertically dense.
3. Declare variables close to their usage.
4. Dependent functions should be close.
5. Similar functions should be close.
6. Place functions in the downward direction.
7. Keep lines short.
8. Don't use horizontal alignment.
9. Use white space to associate related things and disassociate weakly related.
10. Don't break indentation.

## Objects and data structures
1. Hide internal structure.
2. Prefer data structures.
3. Avoid hybrids structures (half object and half data).
4. Should be small.
5. Do one thing.
6. Small number of instance variables.
7. Base class should know nothing about their derivatives.
8. Better to have many functions than to pass some code into a function to select a behavior.
9. Prefer non-static methods to static methods.

## Tests
1. One assert per test.
2. Readable.
3. Fast.
4. Independent.
5. Repeatable.

## Code smells
1. Rigidity. The software is difficult to change. A small change causes a cascade of subsequent changes.
2. Fragility. The software breaks in many places due to a single change.
3. Immobility. You cannot reuse parts of the code in other projects because of involved risks and high effort.
4. Needless Complexity.
5. Needless Repetition.
6. Opacity. The code is hard to understand.
