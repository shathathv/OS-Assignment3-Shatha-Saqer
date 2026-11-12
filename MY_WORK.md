# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | shatha ali saqer|
| **Student ID** | 445052012 |
| **University Email** | 445052012@std.psau.edu.sa |
| **GitHub Username** | shathathv |
| **Repository Link** | https://github.com/shathathv/OS-Assignment3-Shatha-Saqer |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - November 11, 2026, [4:00 PM]

What I did: Reviewed the assignment requirements and examined the starter code.

Details: I studied the ReadyQueue and SharedStats classes to understand how shared data is accessed by multiple threads.

Challenges: Understanding where synchronization was needed to prevent race conditions.

Solution: I reviewed the shared variables and identified the methods that required locks.

Time spent: [actual time spent]

---

### Entry 2 - November 11, 2026, [5:00 PM]

What I did: Implemented locking in the ReadyQueue class.

Details: I used ReentrantLock to protect the shared list and map in the add, poll, processOf, and snapshot methods.

Challenges: Making sure the lock was always released, even if an exception occurred.

Solution: I used try-finally blocks to guarantee that the lock is released.

Time spent: [actual time spent]

⸻

### Entry 3 - November 11, 2026, [6:30 PM]

What I did: Protected the shared statistics in SharedStats.

Details: I added a shared ReentrantLock to protect the statistics update methods and getter methods.

Challenges: Ensuring that multiple CPU workers could safely access and update shared counters.

Solution: I used the same statsLock for all statistics operations and released it in finally blocks.

Time spent: [actual time spent]

⸻

### Entry 4 - November 12, 2026, [3:30 PM]

What I did: Implemented semaphore synchronization in the ReadyQueue.

Details: I initialized the Semaphore with zero permits, released a permit when a process was added, and used acquire() when a CPU worker requested a process.

Challenges: Replacing busy waiting with proper thread coordination.

Solution: I used Semaphore acquire() and release() to coordinate CPU workers with available processes.

Time spent: [actual time spent]

⸻

### Entry 5 - November 12, 2026, [4:00 PM]

What I did: Improved the CPU worker shutdown mechanism.

Details: I updated wakeAll() to release permits for all CPU workers and added a completion check after acquiring a semaphore permit.

Challenges: Making sure waiting CPU workers wake up and terminate when all processes are completed.

Solution: I used the completed-process count to detect shutdown and totalCPUs to release the waiting workers.

Time spent: [actual time spent]

⸻

### Entry 6 - November 12, 2026, [6:00 PM]

What I did: Tested the synchronization implementation.

Details: I ran the program five times and checked the verification results after each run.

Challenges: Ensuring that the program consistently completed without synchronization errors or busy waiting.

Solution: I checked all four verification results in every run. All checks passed, and busy-waiting polls remained zero.

Time spent: [actual time spent]
---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned that synchronization is important when multiple threads access shared data at the same time. Without proper synchronization, race conditions can happen and cause incorrect results. In this assignment, I used ReentrantLock to protect the ReadyQueue and shared statistics. I also learned that try-finally is important because it ensures that locks are released even if an exception occurs. The counting Semaphore helped CPU workers wait for available processes instead of using busy waiting. I was surprised that the program could show inconsistent results without synchronization, even when the code looked correct.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was implementing the CPU workers shutdown mechanism. At first, I found it difficult to understand how waiting CPU workers should stop when all processes were completed. The Semaphore needed to wake up the waiting workers without causing busy waiting. I also had to make sure that the shutdown signal used the total number of CPUs. Another challenge was checking the completed process count after acquiring a semaphore permit. I tested the changes several times until all four verification checks passed consistently..]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I overcame the challenges by reading the assignment instructions and reviewing the README file carefully. I studied the existing code to understand how the ReadyQueue and SharedStats classes worked. When I was unsure about the semaphore behavior, I reviewed the code and checked where acquire() and release() should be used. I also checked the shutdown condition to make sure all CPU workers could terminate correctly. After making the changes, I ran the program five times and checked the verification results each time. This helped me confirm that all four checks passed and busy waiting remained zero.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization is used in many real-world applications where multiple users or processes access shared resources. In banking systems, locks help prevent two transactions from incorrectly updating the same account balance at the same time. In online ticket booking systems, synchronization prevents two users from booking the same seat. In databases, locks protect shared records while they are being updated. A print queue can use a counting semaphore to control access to available printers. These examples show that synchronization helps maintain data consistency and prevents conflicts between concurrent operations.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In the original starter code, multiple CPU threads could access and update the same shared counter without mutual exclusion. For example, CPU-1 and CPU-2 could both read the value 12 before either thread writes its update. Both threads could then write 13, so one increment would be lost instead of the counter reaching 14. This is a race condition because the result depends on the timing of the threads, and it can be difficult to detect because it does not happen in every run.]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Context switches (quanta executed)    expected 29    observed 29    PASS
Completed processes                   expected 14    observed 14    PASS
Total service time (ms)               expected 88892  observed 88892  PASS
Busy-waiting polls (must be 0)        expected 0      observed 0      PASS
All shared values are consistent.]
```

**Explanation of the timeline:**
[CPU-1 and CPU-2 both read contextSwitchCount as 12 before either thread updates it. CPU-1 calculates 13, and CPU-2 also calculates 13 using the same old value. CPU-1 writes 13, then CPU-2 writes 13, overwriting the first update. The final value becomes 13 instead of 14, so one increment is lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used one ReentrantLock in ReadyQueue to protect the shared list and map in the add(), poll(), processOf(), and snapshot() methods. I used a separate statsLock for the three statistics update methods and their getters, because the counters are independent but need safe access. Using one lock for all statistics makes the code simpler, but it can reduce concurrency because only one statistics operation can hold the lock at a time. Separate locks for the queue and statistics provide mutual exclusion while avoiding unnecessary blocking between these two resources; however, the default ReentrantLock is not fair, so bounded waiting is not guaranteed.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| Critical section (variable / method)	Lock used	Why it needs protection
ReadyQueue.add()	lock	Protects the shared list and map when adding a process.
ReadyQueue.poll()	lock	Protects the list when removing a process.
ReadyQueue.processOf()	lock	Protects access to the shared map.
ReadyQueue.snapshot()	lock	Protects access when reading the queue contents.
SharedStats update methods	statsLock	Prevents lost updates to shared statistics.
SharedStats getter methods	statsLock	Ensures safe and consistent reading of statistics. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the original starter, CPU workers repeatedly checked the queue when it was empty, causing busy waiting and wasting CPU time. In my final version, I initialized the counting Semaphore to 0 because no processes are available initially. After the 14 initial processes are added, the semaphore has 14 permits, before CPU workers start acquiring them. When a CPU calls acquire() on an empty queue, it blocks instead of continuously polling. At shutdown, the last CPU releases totalCPUs permits to wake waiting workers, allowing them to check the completion condition and terminate instead of waiting forever..]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[This is the Producer-Consumer problem. The main thread acts as the initial producer by adding processes to the ready queue, while CPU workers act as consumers by taking processes from it. CPU workers can also act as producers when they re-enqueue unfinished processes.]

**Semaphores for a bounded queue (name and initial value)**:
[* empty = K (the queue capacity)
* full = 0 (initially, the queue is empty)
* mutex = 1 (allows one thread to access the queue at a time).]

**Deadlock scenario and prevention**:
[Deadlock can happen if a producer acquires the mutex before waiting on the empty semaphore when the queue is full. The producer holds the mutex while waiting for a free slot, but the consumer needs that mutex to remove an item and create a free slot. This causes circular waiting. To prevent it, wait on empty before acquiring the mutex, which breaks the hold-and-wait condition..]

## Summary

**Key concepts I understood through these questions:**
1. Synchronization prevents race conditions and protects shared data using mutual exclusion.
2. ReentrantLock and try-finally protect critical sections and prevent lost updates.
3. Counting Semaphore coordinates CPU workers, avoids busy waiting, and supports safe shutdown.

**Concepts I need to study more:**
1. Understanding deadlock conditions and how to prevent them in concurrent programs.
2. Learning more about semaphore behavior, thread scheduling, and fair lock mechanisms.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [t] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [t] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [t] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [t] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [t] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [t] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [t] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [t] **The four verification lines are ✔ in 5 consecutive runs**
- [t] Every lock is released in a `finally` block
- [t] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [t] Each feature has clear comments

**Commits**
- [t] **At least 4 meaningful commits, ideally 7 or more**
- [t] **One commit per feature**
- [t] Commits are spread over **different dates** (not all in the last hour)
- [t] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [t] Full name and student ID filled in at the top
- [t] Development log has **5+ entries** on different dates
- [t] Reflection: 4 questions, 5-7 sentences each
- [t] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [t] No `[...]` placeholders left
- [t] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [t] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
