
# FAQ

Hi everyone,

Below you can find answers to questions I have received so far by email. I will update this thread with more Q/A if I receive more.

## Q1 Would you ask questions about the entire curriculum or only parts of it, such as "[[Cloud 3 Cloud Computing Services|L3 - Cloud Services]]," etc.?

(See also [[L3 Questions]]  and [[Terms_L3-Cloud_Services]] )

> [!NOTE] We will ask questions from different parts of the curriculum. **The first question will typically be a practical one where you will have to solve something on the laptop.**
> If you have done the assignments, the question will be to **modify something small on the assignment and show the changes.**

- we could ask you to kill one of the services for example so that you show what happens with the cluster.

- **On the second one** we can ask for example to increase the number of [[Threads]], or to modify the source code so that certain words to not be counted.

> [!NOTE] Then, we will typically ask two theoretical questions from the topics covered in the curriculum.
>
## Q2 know what requirements you expect us to meet — _what can one possibly expect in the exam, and what should we prepare for,  so that i can be well-prepared for the exam?_

> [!NOTE] you should be able to do something practical. Then, you should be able to discuss the theoretical concepts listed on the file with typical questions.
>
## Q3 if the slideshow on module 3 is the updated one?

> [!NOTE] These slides are prepared by the students for the presentation in the classroom. They have all the relevant structure to guide you to the right material you need to read online.

## Q4 Feedback on assign

## Q5 The online module in module 4, how much of it do we need to go through?

> [!NOTE] You should study the first three (out of four) sections:
>
> 1) Introduction  to [[Serverless Computing]]
> 2) Introduction to [[AWS Lambda]]
> 3) Using [[AWS Lambda]] ( [[Getting Started with  AWS Lambda]] )
>
> **You can skip the last one (AWS Serverless Services)**
>
## Q6 if i can choose which assignment i want to present and talk about?

Yes, if you have done both assignments we will allow you to pick the one you prefer. But we can also decide to discuss both of them.

## Q7 we have to do live coding, and if you have submitted the assignments, what type of live coding questions can we expect to solve?
>
> [!NOTE] Please, check answer to Q1.

## Q8 emphasis do you place on the practical versus the theoretical aspects. how much time do you allocate to each? **does one take up more time and weight in the evaluation than the other?**

> [!NOTE] In terms of time, we will try to allocate equal time to the (typically) three questions, where the first will typically be the practical one.
> we estimate around 5-7 minutes per question. In terms of how they are weighted, there is no exact formula.
>
## Q9 you focus on the following

> [!NOTE] _"A small program with multiple [[Threads]] to show race conditioning and how it can be fixed. Another one could be to show that you can start a VM, a container, or a [[Kubernetes]] cluster."_
> **Is this all you need to know to be well-prepared for the live coding part, or are there other topics/more things that one might encounter?**

the file with questions and the examples mentioned are just reference type of questions that we can ask. You should check the topics of the lectures to get the full picture of topics that you need to study. Other examples could be a [[client-server]] application, a simple application that performs heartbeat signaling, etc.

## Q10 Could the following code be a good example of the question  

" an example of this question can be to write a small program with multiple [[Threads]] to show race conditioning and how it can be fixed,"

```Python
import threading

# Shared resource
counter = 0
lock = threading.Lock()

# Function to increment the counter safely
def increment_counter_safe():
global counter
for _ in range(100000):
 with lock:
  counter += 1

# Create threads
thread1 = threading.Thread(target=increment_counter_safe)
thread2 = threading.Thread(target=increment_counter_safe)

# Start threads
thread1.start()
thread2.start()

# Wait for both threads to finish
thread1.join()
thread2.join()

# Print final value of the counter
print (f"Final counter value (with lock): {counter}")
```

> [!NOTE] Yes, this could be what we would look for as an answer for this. Of course, assuming that you will also explain how race conditioning is caused and how it is solved.

## Q11 How much time do we have to present the miniproject in the exam?

### also if it is allowed to use the README made for the project during the exam? _This is because some commands are very long._

> [!NOTE] 5-7 minutes. And yes, you can use the README, thats fine.
> **Suggestion:** do not spend time explaining/presenting what the project does, I know that. Focus on showing that it works and then we will ask our question(s).

## Q12 It seems that I need to know how to: setup a [[Virtual Machines|VM]] , [[Containers]], [[Kubernetes|Kubernetes Cluster]], [[client-server]], and [[Threads|multithreading/processes]]. Are there any more that are important to know?

### I am also asking this because I see code for [[Protocol Buffers|protobuffs]], usage of [[ZeroMQ]] and [[AMQP]]. And I haven't seen any code for **locks** yet, which I remember deals with the shared memory problem for [[Threads]]

> [!NOTE] Check the exercises that I have allocated after each lecture and take them as a reference.
> Of course, we will not ask you to implement a full [[Leader Election]] algorithm (e.g., the [[Bully Algorithm]]), but we can ask you to show how you would start and how you would then continue.
>
> **The locks are needed for problems like race conditioning, which I have mentioned as an example of question we can ask (check Q10).**
>
## Q13 A question about the [[Flood-based consensus algorithm]] ([[Consensus]]) example

### **[[Flood-based consensus algorithm|flood-based consensus]] example:** Everyone floods their command list to each other and P3 simply votes differently (he votes R), is command A invoked because it's the majority or does nothing happen because there is no full [[Consensus]]?
>
> [!NOTE] What you are describing is an [[arbitrary failure]]. For the [[Flood-based consensus algorithm]], we have not considered arbitrary failures but only fail-stop ones.
> **Anyway, the solutions you propose could both be valid, depending on the system and on the implementation design.**

> [!NOTE] **Followup:** Actually, I stand corrected, that we have seen the flooding [[Consensus]] with arbitrary failures in the last lecture. And the algorithm indeed states that if we have one arbitrary failed node and two correct ones, then the majority wins so A will be executed
> _(slides 22 and 23, [[Cloud 10 Fault Tolerance|lecture 10]])_
>

## Q14 the 3k + 1 nodes idea. It said earlier that 2k + 1 nodes is needed for tolerating k faulty nodes in case of arbitrary failures

### Now 3k + 1 on the slide "System model". Is it because we are using a primary in the case requiring 3k + 1, and not one in 2k + 1?

> [!NOTE] The difference between the 2k+1 and the 3k+1 cases is that in the first, the k arbitrary nodes behave in the same way towards all the other nodes (i.e., they send the wrong message to all the nodes)
> **In the second,** they might send different messages to different nodes.
>
> Detecting the first case is easier, as the k+1 correct nodes make the majority.
>
> The second case is more complicated, for which we need 2k+1 correct nodes.

## Q15 If only one assignment has been submitted, is it fine to just talk about that one at the exam? **YES, it's fine**

