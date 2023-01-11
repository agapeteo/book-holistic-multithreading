# Purpose

Multithreading from top to bottom. From abstractions like concurrent hash maps to assembler instructions. General narrative when introducing a new concept: how and why this concept came to be. Only after that can we dive into details. We intend to provide references for people to dive deeper on particular topics.

## Audience

Who this book is for? We assume that you have a basic understanding of what an operating system is and a very basic understanding of computer hardware. We also assume that you have a basic knowledge of Java, C, C++, or Rust.

# Introduction

A simple example with one or two threads. What happens:

* On the language level;
* On the OS level;
* On the hardware level.

The rest of the books is just a deeper and broader exploration of what we have just covered.

# Theory

Theoretical basis for concurrency. Threading models, scheduling, safety and liveness properties, mutexes, deadlocks, starvation.

# Operating system

What is a Thread? Threads exists in an operating system. There's no reason to talk about threads outside of the OS. If ypu want threads on the bare metal you will end up implementing your own minimalistic OS.

# Hardware

Basics of hardware architecture. How does hardware support multithreading? How did CPU evolved alongside OS and what impact they had on each other.

# Low Level Abstractions

Thread and other concurrency primitives.

# High Level Abstractions

Concurrent Hash Map and other stuff.

# Concurrent Algorithms

# Testing concurrency

# Programming models

Shared memory, message passing...

# Cooperative scheduling

Coroutines and their cousins. Java virtual threads. How are these things implemented. What are the benefits.

# Posix Threads

# Languages

Java, C, C++, Rust, JS/Python (only to critisize their lack of comprehensive threading support).

# Test Hardware

MBP Pro, Raspberry Pi, Pine64 SBC.

