Version 1.3

- AutoCoding no longer attempts to encode virtual properties. Only ivar-backed properties will be encoded
- Added dictionaryRepresentation method for quickly accessing all properties of a class
- The codableKeys and uncodableKeys methods are now class methods, allowing them to be used more easily in factory methods 
- The class-level codable/uncodableKeys methods now only return the properties for the class on which they are called, not all of its superclasses as well
- It is no longer necessary to call [super codableKeys] or [super uncodableKeys] and merge arrays when overriding the codableKeys or uncodableKeys class methods on a subclass (overriding the codableKeys instance method is not recommended)

Version 1.2.1

- writeToFile:atomically: method now returns a BOOL to indicate success
- Changed category file names

Version 1.2

- Read-only properties can now be copied and coded as long as they have a KVC compliant ivar (i.e. one whose name matches the property or the property with the _ prefix)
- initWithCoder: no longer calls [self init], in compliance with Apple docs
- codableKeys method now uses caching for better performance
- Exposed previously private setWithCoder: method used by BaseModel library

Version 1.1.2

- Switched constructor to return new type-safe `instancetype` instead of id, making it easier to use dot-syntax property accessors on loaded instances.

Version 1.1.1

- Read-only properties are now excluded from codableKeys
- Added unit tests

Version 1.1

- Added automatic NSCopying implementation
- writeToFile now obeys the useAuxiliaryFile parameter

Version 1.0

- Initial release