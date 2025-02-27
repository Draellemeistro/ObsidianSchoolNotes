
> [!NOTE] **Scenario**
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