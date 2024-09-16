# LLM-literature-review

Name: Maxwell Rovenger -- 2398501
Email: mrovenger@chapman.edu
Date: 9/15/2024
LLM Used: ChatGPT

Recursion In Computer Systems

# Question: 
How does reucrsion affect memory usage in a program?

# Conversation with ChatGPT:

Question:
    Can you answer this question?: How does recursion affect memory usage in a program?

ChatGPT Reponse:
    Recursion affects memory usage by adding a new stack frame for each recursive call. Each stack frame stores information such as the function’s parameters, local variables, and the return address. As the recursion depth increases, more stack framgites are created, which can lead to high memory consumption. If the recursion depth is too deep, it may cause a stack overflow, exhausting the available stack memory.

Question:
    Does recursion create a more efficient environment regarding memory usage or does it provide no benefit other than improved readability and functionality?

ChatGPT Reponse:
    Recursion does not generally create a more efficient environment regarding memory usage compared to iterative solutions. In fact, it often leads to higher memory usage due to the extra stack frames for each recursive call.
    However, recursion can improve readability and functionality in some cases, making the code easier to understand, especially for problems that naturally fit recursive patterns (e.g., tree traversal, factorial, Fibonacci sequence). 
    In terms of memory efficiency, recursion typically doesn’t offer benefits over iteration unless a technique like tail recursion optimization is applied. Tail recursion allows some languages or compilers to optimize and reuse stack frames, effectively reducing the memory overhead. However, this optimization isn’t universally available in all languages.
    So, while recursion enhances readability and can be useful for solving specific types of problems, it usually leads to higher memory consumption compared to iterative approaches

Question:
    To continue our recursive conversation, is tail recursion optimization commonplace for popular programming languages like python, javascript, and c++? 

ChatGPT Reponse:
    Python:
        Python does not support tail recursion optimization. Due to Python’s interpreter design, even tail-recursive functions will still create new stack frames for each recursive call. Python’s recursion limit (usually around 1,000 calls) can be quickly hit, leading to RecursionError. Python emphasizes readability and simplicity over low-level optimization like TCO.
    JavaScript:
        JavaScript has limited support for tail recursion optimization, depending on the engine and version. ECMAScript 2015 (ES6) introduced tail call optimization as part of the standard, but not all JavaScript engines have fully implemented this feature. For example, V8 (used in Chrome and Node.js) does not currently implement tail call optimization, so its practical use is still limited.
    C++:
        C++ can optimize tail recursion in some cases, but it’s not guaranteed by the language standard. C++ compilers like GCC and Clang can apply TCO as part of general optimizations if they detect a tail-recursive function. However, this behavior is compiler-specific and dependent on optimization settings (-O flags), so it’s not guaranteed in every scenario.

Question:
Within the programming languages field, what were the historical developments to find out that recursive functions increased memory usage?

ChatGPT Reponse:
    Early Days of Recursion:
        In the 1960s, recursion became more prominent with the advent of ALGOL (short for Algorithmic Language), one of the first languages to formally support recursion. ALGOL’s support for recursion introduced developers to the idea of functions calling themselves, but it quickly became clear that recursion required the creation of new stack frames for each function call, leading to memory growth proportional to the recursion depth.
        Researchers like John McCarthy, who developed LISP (1958), a language known for supporting recursion, further explored recursive structures in computation. LISP introduced concepts like functional programming, where recursion is a natural fit, but the computational cost of each function call was recognized as a challenge.
    Stack and Memory Models:
        By the 1970s, with the advent of structured programming (in languages like Pascal), programmers became more aware of the memory trade-offs involved in recursion versus iteration. Structured programming encouraged clearer, modular code, which led to more use of recursion for certain problems like sorting (e.g., quicksort), but also made evident the cost of creating deep recursion stacks.
        The invention of the call stack—a fundamental data structure used by programming languages to manage function calls—brought more understanding of how recursion consumes memory. Each time a recursive function is called, a new stack frame is created to store information like the function’s arguments, return address, and local variables. This process led to memory inefficiencies for deep recursion.
    Stack Overflow and Practical Limitations:
        As recursive algorithms (e.g., Fibonacci sequence, factorial calculation) gained popularity, developers noticed that recursion depth could lead to stack overflow errors—when the stack exceeded its memory allocation due to deep recursive calls. This practical limitation became evident in languages like C and Pascal, where recursive calls for large inputs caused crashes.
    Development of Tail Recursion Optimization:
        To address the memory inefficiencies, the concept of tail recursion optimization (TCO) was developed in the 1970s and 1980s, particularly in functional languages like Scheme and ML. TCO allows recursive calls that occur in the “tail position” (the last action in a function) to be optimized so that they reuse the current function’s stack frame, preventing memory buildup.
        Guy L. Steele and other researchers in the 1970s contributed significantly to the development of TCO through work on Scheme and the Lambda Calculus. Scheme, a dialect of LISP, was designed to support efficient tail-call optimization, allowing for deep recursion without excessive memory usage.
    Modern Understanding and Compilers:
        As memory became less constrained and compilers grew more sophisticated, languages like C++, Java, and Python incorporated recursive functions into their standard libraries, but without guaranteed TCO. Functional programming languages like Haskell continued to push for recursion-friendly features, while imperative languages favored iteration to avoid memory overhead from recursion.
        By the late 20th century, studies into algorithmic complexity helped solidify the understanding that recursion, while elegant for certain problem domains, can be memory-inefficient without optimizations like TCO. Researchers and developers sought ways to balance the readability of recursion with practical memory limitations, often opting for iterative approaches in high-performance environments.

# References:
Tail Call Optimization. (n.d.). Retrieved September 15, 2024, from Tufts University website: https://www.cs.tufts.edu/cs/21/notes/tail_calls/index.html

Balaam, M. (2009). A brief history of tail recursion. Overload, 20(109). Retrieved September 15, 2024, from https://accu.org/journals/overload/20/109/balaam_1914/

Paul Graham, The Roots of Lisp (exploring recursion in LISP).

Guy L. Steele, RABBIT: A Compiler for SCHEME (on tail call optimization in functional languages).