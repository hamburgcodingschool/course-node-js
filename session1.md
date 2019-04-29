# Session 1

## Introduction

What is Node.js?
- Engine / Runtime
- server-side
- in a single thread
- explain: what is a Thread
- implemented asynchronically
- runtime / framework
- based on V8 engine

## Event loop

How does it work?
- there is an infinite loop running: the event loop
- is running on that single thread and processes everything that is happening in there
- you remember setTimeout()?
- the whole phases (timers, callbacks, idle/prepare, poll, check, close) are repeated over and over

