# Fiber

Fibers are primitives for implementing light weight cooperative concurrency in
Ruby. Basically they are a means of creating code blocks that can be paused
and resumed, much like threads. The main difference is that they are never
preempted and that the scheduling must be done by the programmer and not the
VM.

As opposed to other stackless light weight concurrency models, each fiber
comes with a stack.  This enables the fiber to be paused from deeply nested
function calls within the fiber block.  See the ruby(1) manpage to configure
the size of the fiber stack(s).

When a fiber is created it will not run automatically. Rather it must be
explicitly asked to run using the `Fiber#resume` method. The code running inside
the fiber can give up control by calling Fiber.yield in which case it yields
control back to caller (the caller of the `Fiber#resume`).

Upon yielding or termination the Fiber returns the value of the last executed
expression

For instance:

    fiber = Fiber.new do
      Fiber.yield 1
      2
    end

    puts fiber.resume
    puts fiber.resume
    puts fiber.resume

*produces*

    1
    2
    FiberError: dead fiber called

The `Fiber#resume` method accepts an arbitrary number of parameters, if it is
the first call to `#resume` then they will be passed as block arguments.
Otherwise they will be the return value of the call to Fiber.yield

Example:

    fiber = Fiber.new do |first|
      second = Fiber.yield first + 2
    end

    puts fiber.resume 10
    puts fiber.resume 1_000_000
    puts fiber.resume "The fiber will be dead before I can cause trouble"

*produces*

    12
    1000000
    FiberError: dead fiber called

[Fiber Reference](https://ruby-doc.org/core-2.7.0/Fiber.html)