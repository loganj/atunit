AtUnit
======

AtUnit **minimizes boilerplate code** in unit tests and *guides test development* by enforcing good practices.  

  * mark exactly one field with `@Unit` to indicate the object under test.
  * mark fields with `@Mock` or `@Stub` to obtain mock objects
  * inject your tests, and your test subjects, using your favorite IoC container


Mock Objects Integration
-------------------------
AtUnit **integrates with JMock or EasyMock** to provide mock objects:

  * obtain a JMock context simply by declaring a field
  * annotate fields with `@Mock` to obtain JMock or !EasyMock mock objects
  * annotate fields with `@Stub` to obtain a JMock or !EasyMock stub object


... or you can use your own **mock objects plug-in** with two easy steps:

  * implement the `MockFramework` interface
  * annotate your tests with `@MockFrameworkClass(MyMockFramework.class)`


Dependency Injection
-----------------------
AtUnit integrates with **Guice** or **Spring** to take all of the work out of dependency-injected tests.

With Guice:

  * never see the `Injector`, never write bootstrapping boilerplate!
  * `@Inject` test class fields without even defining a `Module`
  * declaratively obtain mock objects with `@Inject @Mock`
  * if you need more binding flexibility, simply have your test class implement `Module`

With Spring:

  * annotate fields with `@Bean` to get them from the Spring context
  * fields annotated with `@Bean` which do not appear in your Spring context are added to it automatically!  (This includes `@Mock` and `@Stub` fields.)
  * !AtUnit looks for a Spring XML file with the same name as your test, or you can specify the location yourself with `@Context("filename")`
  * Most of the time, you don't even need a Spring XML file!


You can easily **plug in other containers** in two steps:
    * implement the `Container` interface
    * annotate your tests with `@ContainerClass(MyContainer.class)`

Get Started
-----------
These [Example AtUnit Tests][examples] are the quickest way to get started with AtUnit.  They demonstrate most permutations of supported containers and mock frameworks, and illustrate the various ways AtUnit makes writing tests easier.

[examples]: http://atunit.googlecode.com/svn/trunk/doc/api/atunit/example/