# PHPUnit

- [Documentation](https://phpunit.readthedocs.io/en/8.5/configuration.html)

## XML Configuration File

- phpunit.xml -> nicht in git; persönliche Variablen speichern
- phpunit.xml.dist -> in git

```
<php>
    <env name="foo" value="bar" force="true"/>
</php>
```

## Packages

- [Snapshot testing with PHPUnit](https://github.com/spatie/phpunit-snapshot-assertions) - für API tests

## Skipping, Incomplete

```
$this->markTestSkipped('reason');
$this->markTestIncomplete('reason');
```

## Mocking

- [Test Doubles](https://phpunit.readthedocs.io/en/9.0/test-doubles.html)
- [Laracasts: Fake it Till You Make it](https://laracasts.com/series/build-a-stock-tracker-app/episodes/6)

### Stubs

> The practice of replacing an object with a test double that (optionally) returns configured return values is referred to as stubbing. - [PHPUnit](https://phpunit.readthedocs.io/en/9.0/test-doubles.html#stubs)

```
<?php
class SomeClass
{
    public function doSomething()
    {
        // Do something.
    }
}
```

```
<?php
use PHPUnit\Framework\TestCase;

class StubTest extends TestCase
{
    public function testStub()
    {
        // Create a stub for the SomeClass class.
        $stub = $this->createStub(SomeClass::class);

        // Configure the stub.
        $stub->method('doSomething')
             ->willReturn('foo');

        // Calling $stub->doSomething() will now return
        // 'foo'.
        $this->assertSame('foo', $stub->doSomething());
    }
}
```

### Mocking

> The practice of replacing an object with a test double that verifies expectations, for instance asserting that a method has been called, is referred to as mocking. - [Mock Pbjects](https://phpunit.readthedocs.io/en/9.0/test-doubles.html#mock-objects)

```
<?php
use PHPUnit\Framework\TestCase;

class SubjectTest extends TestCase
{
    public function testObserversAreUpdated()
    {
        // Create a mock for the Observer class,
        // only mock the update() method.
        $observer = $this->createMock(Observer::class);

        // Set up the expectation for the update() method
        // to be called only once and with the string 'something'
        // as its parameter.
        $observer->expects($this->once())
                 ->method('update')
                 ->with($this->equalTo('something'));

        // Create a Subject object and attach the mocked
        // Observer object to it.
        $subject = new Subject('My subject');
        $subject->attach($observer);

        // Call the doSomething() method on the $subject object
        // which we expect to call the mocked Observer object's
        // update() method with the string 'something'.
        $subject->doSomething();
    }
}
```

### Hard Dependencys

Wenn Klasse in einer anderen Funktion erstellt wird ([Mockery](http://docs.mockery.io/en/latest/cookbook/mocking_hard_dependencies.html) erforderlich)
```
<?php
namespace AppTest;
use Mockery as m;
class ServiceTest extends \PHPUnit_Framework_TestCase
{
    public function testCallingExternalService()
    {
        $param = 'Testing';

        $externalMock = m::mock('overload:App\Service\External');
        $externalMock->shouldReceive('sendSomething')
            ->once()
            ->with($param);
        $externalMock->shouldReceive('getSomething')
            ->once()
            ->andReturn('Tested!');

        $service = new \App\Service();

        $result = $service->callExternalService($param);

        $this->assertSame('Tested!', $result);
    }
}
```
Wie mache ich das mit PHPUnit?