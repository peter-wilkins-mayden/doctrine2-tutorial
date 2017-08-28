* Defensive programming
Code is not reusable - code for the use case
Solid + object callesthenics
- One level of indentation per method.
- Don't use the ELSE keyword.
- Wrap all primitives and Strings in classes.
- First class collections.
- One dot per line.
- Don't abbreviate.
- Keep all classes less than 50 lines.
- No classes with more than two instance variables.
- No getters or setters.


Immuntable state - no stteres - deep clone - eg PSR7
Constuctor is only injection point
No uninitialized properties
no optional dependencies - use null object pattern
avoid all unneccessary public methods - considered harmful
avoid flags / ifs / conditionals
all state is private
enforce strict invarients - type checking  https://github.com/beberlei/assert
No mixed parameter or return types
Value objects FTW
classes final by default (no extends) where possible
Unit tests - CRAP index <= 2
Law of demeter - only talk to neighbours

* Doctrine Best Practises
Domain first - code entities without ORM first - define db after modelling Domain
Entities have behavior - they are not typed arrays (records) - no  setters - domain specific api
Design internal state last.
Entities always in valid state - validate form data before creation - use data transfer object.\
No Auto increment index - use UUID. Constraints over composite keys - Don't over normalise
Named constructors for different sources of data - disable constructors
No setters - they lack meaning. harm code clarity
No framework in the buisness logic
Avoid lifecycle callbacks - no unexpected side-effects
Immutable entities
```
@Entity(readOnly=true)
```
Enable second level cache
Append only data structures
Event sourcing
Use custom repositories / Query functions (class with one invode method)
Don't use getRepository - Inject repos intoo constructors
get() function - throws exception if entity not found - reduces null checking
find() - can return null
Pass id's rrather than entities between services
Json bucket
many databases - eg reporting database - secondary to main data source.
Perf - UnitOfWork, DQL (don't use paginator - use custom repos), Snd Level cacheProfile hotspots
