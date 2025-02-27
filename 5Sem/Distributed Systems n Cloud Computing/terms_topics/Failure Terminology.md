> [!failure] **[[arbitrary failure]]:** May produce arbitrary responses at arbitrary times

> [!NOTE] Terms
> - **Failure:** A component is not living up to its specifications (ex: crashed program)
> - **Error:** Part of component that can lead to a failure (programming bug)
> - **Fault:** Cause of an error. (sloppy programming)

> [!NOTE] Basic Concepts
> - **Fault prevention:** prevent the occurrence of a **fault** (dont hire sloppy programmers)
> - **Fault tolerance:** Build a component such that it can mask the occurrence of a fault. (Build each component by two independent programmers)
> - **Fault removal:** Reduce the presence, future incidence, and consequences of **faults** (estimate how a recruiter is doing when it comes to hiring sloppy programmers)
# [[Dependability]]
# Failure Models (types of failures)
## Crash failure
Server halts, but is working correctly until it halts
## Omission failure
Fails to respond to incoming requests
### Receive omission
Fails to receive incoming messages
### Send omission
Fails to send messages
## Timing failure
Response lies outside a specified time interval
## Response failure
Response is incorrect
### Value failure
the value of the response is wrong
### State-transition failure
Deviates from the correct flow of control
## **[[arbitrary failure]]**
May produce arbitrary responses at arbitrary times

## [[Halting Failures]]
> [!NOTE] **Scenario:** [[Halting Failures]]
> $C$ no longer perceives any activity from $C*$ -- a [[Halting Failures|Halting Failure]]?
> (Distinguishing between a **crash** or **omission/timing failure** may be impossible)
### Halting failure types
- **Fail-stop:** Crash failures, but reliably detectable.
- **Fail-noisy:** Crash failures, eventually reliably detectable.
- **Fail-silent:** omission or Crash failures: clients cannot tell what went wrong
- **Fail-safe:** [[arbitrary failure|arbitrary]], yet benign failures (i.e., they can't do any harm)
- **fail-arbitrary:** [[arbitrary failure|arbitrary]], with malicious failures.
### Asynchronous vs Synchronous systems
- **Asynchronous system:** No assumptions about process execution speeds or message delivery times $\to$ **Cannot reliably detect crash failures**
- **Synchronous system:** Process execution speeds and message delivery times are bounded $\to$ **we can reliably detect omission and timing failures.**
In practice we have **partially synchronous systems:** most of the time, we can assume the system is asynchronous, yet there is no bound on the time that a system is asynchronous $\to$ **Can normally reliably detect crash failures.**


# [[Process-resilience]]