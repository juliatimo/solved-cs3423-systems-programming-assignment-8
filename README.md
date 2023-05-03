Download Link: https://assignmentchef.com/product/solved-cs3423-systems-programming-assignment-8
<br>
Process Control




<h1>Warning</h1>

<strong>Warning: </strong>do <strong><u>NOT </u></strong>utilize the <sub>fox </sub>machines for performing or testing this assignment! You can and <strong>WILL </strong>cause a <sub>fork()</sub>-bomb, causing the system(s) to become unstable and unusable.

Instead, you MUST utilize servers hen04.cs.utsarr.net or hen03.cs.utsarr.net. Note that these servers are accessible only in the following ways:

<ul>

 <li>Within the UTSA network (i.e., using the on-campus network);</li>

 <li>via VDI from home; or,</li>

 <li>via connecting to a <sub>fox </sub>machine <em>first</em>, <em>then </em>proceeding to SSH into one of these two <sub>hen </sub></li>

</ul>

If either server becomes unstable or unusable due to a student’s out-of-control project, email me to alert me to the situation and I will have the system(s) reset.

For this assignment, you will use <strong>C</strong>’s process control functions to exercise basic process creation. Your program should have the following functionality:

<h1>Concurrency</h1>

Given <strong>up to six </strong>commands separated by commas (a comma will be its own token, with whitespace around it) and <strong>any number of </strong>arguments each, execute all commands <em>concurrently </em>(i.e., in parallel and not one after the other).

Each process (excluding the parent) should print their PID followed by their PPID followed by their command without arguments <strong>to stderr</strong>. Any normal behavior by the command issued should remain the same. You do not need to account for redirection or pipelining.

Your program <strong>should not produce orphans</strong>. Toward verification of this, if a process’s PPID is 1, it is an orphan that has been adopted by the <sub>init </sub>process. In solving this problem, be sure that your child processes still run concurrently. Do not wait for one process to complete before starting a new one.

<h2>Example</h2>

<strong>$ assign8 ls -a , pwd , cat hello.txt</strong>

<strong>PID: 35003, PPID: 35002, CMD: ls PID: 35004, PPID: 35002, CMD: pwd</strong>

<h3>PID: 35005, PPID: 35002, CMD: cat</h3>

<strong>/home/ssilvestro</strong>

<strong>. .. courses Desktop Downloads this is the contents of hello.txt</strong>

Note that since the processes are happening in parallel, the order of the output is not guaranteed.

<h1>Compiling Your Program</h1>

Your submission will include a makefile so the following command can be used to compile your code.

<strong>$ make assign8</strong>

This should produce an executable file named <strong>assign8</strong>. For more information about the make utility, check the related document on Blackboard.

If you attempt the extra credit, <strong><sub>$ make assign8-2 </sub></strong>should compile the extra credit portion to <strong>assign8-2</strong>.

<h1>Extra Credit (10 points)</h1>

Create a second program, <strong><sub>assign8-2 </sub></strong>which takes <strong>exactly two </strong>commands, with <strong>any number of </strong>arguments each, and separated by a comma. The program should pipe the output of the first command to the second using <strong><sub>dup2()</sub></strong>.

<h2>Example</h2>

<strong>$ assign8-2 ls -l , sort -k5 -n </strong>should behave as

<strong>$ ls -l | sort -k5 -n</strong>

Extra credit is not given to late assignments. All requirements must be met for both parts of the assignment to qualify for extra credit.

<strong>Assignment Data</strong>

This assignment does not include sample input files since it will only take arguments.

<h1>Program Files</h1>

Your submission should consist of up to five files:

<ul>

 <li><strong><sub>c </sub></strong>– the main file which is compiled <strong>(required)</strong></li>

 <li><strong><sub>h </sub></strong>– an optional header file if necessary</li>

 <li><strong><sub>assign8-2.c </sub></strong>– the main file which is compiled for extra credit <strong>(required for extra credit)</strong></li>

 <li><strong><sub>assign8-2.h </sub></strong>– an optional header file if necessary</li>

 <li><strong><sub>Makefile </sub></strong>– the makefile to make the <strong><sub>assign8 </sub></strong>executable <strong>(required)</strong>.</li>

</ul>


