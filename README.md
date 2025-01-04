# Unsafe Rust Code: Modifying Vector Through Raw Pointer

This repository demonstrates a potential bug in Rust related to unsafe code and memory management. The code modifies a vector's elements through a raw pointer.  This can lead to undefined behavior and crashes if not handled correctly.

## Bug Description
The `bug.rs` file contains code that uses `as_mut_ptr()` to obtain a raw pointer to the vector's data.  While seemingly innocuous, modifying the vector's contents using this pointer after the original vector is no longer in scope can cause data corruption or a program crash. This occurs because Rust's ownership system might reclaim the underlying memory. 

## Solution
The `bugSolution.rs` file demonstrates safer ways to manipulate vectors.  Avoid using raw pointers unless absolutely necessary, and always ensure that the memory is valid and accessible throughout the scope where the raw pointer is used.