# Go-Conference-2024-Tokyo
This Repository Contains the Information regarding the the talk for "Data Race Detection In go From Beginners Eye" 
Session Details : https://gocon.jp/2024/sessions/5/

# Data Race Detection in Go

## Description**

Do you know what is Data Race in concurrent programming and what is inside it's hood ?

The topic addresses the challenge of protecting systems or programs from the unforeseen consequences of elusive data race bugs in concurrent programs. It emphasizes the need for reliable and scalable solutions and delves into the Happens Before Race Detection approach using Vector Clocks.

## Background

Recently, I faced a problem in my code a data race issue that caused My service to crash after I mistakenly deployed it without checking for race conditions . I didn't know how to fix and prevent the data race issue at first , so I searched online to learn more about data races and the Go Race Detector. Curiosity led me to explore how to prevent Data Races, and I'm excited to share my story of understanding the inner workings of the Go Data Race Detector.

In the realm of concurrent programming, the occurrence of Data Race conditions can be frequent and challenging to manage. If I put it in simple words , when two or more goroutines access shared memory data concurrently and one goroutine is a write , Data Race conditions may arise, leading to unpredictable failures which we can not detect long after the code has been deployed to production. This session focuses on exploring the Go Race Detector, which is built upon the C/C++ ThreadSanitizer runtime library. Originally designed to identify errors in Google's internal codebase and Chromium, The Race Detector is a powerful and proven tool for detecting data race bugs.

Given that we wanted to write multithreaded programs, how can we protect our systems from the unknown consequences of difficult to track down data race bugs in a manner that is reliable and scalable .

Go Race Detector follows " Pure Happens Before Race Detection" using Vector Clocks so let's understand the concepts.
