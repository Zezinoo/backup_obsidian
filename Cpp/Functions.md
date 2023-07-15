The way functions are executed can be summarized in:
- Create [[stackframe]] for each function
- Push parameters and return adress to stack
- Jump to other part of the binary to execute the function
- In the end of the stack (FIFO), go back to the return adress
That's why creating a lot of functions can generate a lot of [[overhead]] in your program at [[runtime]].