# Item 4: Make sure that objects are initialized before they’re used.

```cpp
ABEntry::ABEntry(const std::string& name, const std::string& address,
const std::list<PhoneNumber>& phones)
{
    theName = name; // these are all assignments,
    theAddress = address; // not initializations
    thePhones = phones;
    numTimesConsulted = 0;
}
```
Stop using this way and use initilaized list to have the ability to trigger constructor.
```cpp
ABEntry::ABEntry(const std::string& name, const std::string& address,
const std::list<PhoneNumber>& phones)
: theName(name),
theAddress(address), // these are now all initializations
thePhones(phones),
numTimesConsulted(0)
{

}
```
if there isn't paramter you can use default contructor
```cpp
ABEntry::ABEntry()
: theName(), // call theName’s default ctor;
theAddress(), // do the same for theAddress;
thePhones(), // and for thePhones;
numTimesConsulted(0) // but explicitly initialize numTimesConsulted to zero
{

}
```
> [!NOTE]
*Sometimes the initialization list must be used, even for built-in types.
For example, data members that are const or are references must be
initialized; they can’t be assigned.*

