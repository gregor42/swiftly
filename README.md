swiftly
=======

Native libraries rewritten in pure Swift with an open license

The purpose of this project is two-fold:

1. To Swift-ify the Objective-C-Based frameworks.  i.e. write wrapper code that allows for more idiomatic Swift than is currently possible when using Coccoa, Foundation, etc..
2. To promote the adoption of Free Software in the Swift Community

For example, in **Using Swift with Coccoa and Objective-C** in the section on *Working with ni*l it points out that ObjC works with raw pointers that could be NULL.  

Swift however guarantees all values are non-nil.  

Thus Swift wraps the class-types in imported ObjC API's in an implicitly unwrapped optional type.  

So before you use an ObjC type you need to check that it is not missing. *::drumroll::*

 In their example when importing this ObjectiveC method:

<pre>- (NSDate *)dueDateForProject:(Project *)project;</pre>

You have to do this in Swift:

<pre>func dueDateForProject(project: Project!) -> NSDate! </pre>

The ! at the end is bypassing the safety built into the language.  This is a broken idiom - an *antipattern* and at the moment at least, it is all over the place.

Thus the need in this case for a native Swift Date class/protocol/etc...
