## How to use the materials

*NOTE: This README is a collection of the notes of the course. It is NOT a written version of the course, and as such it might not always make sense to you. If anyone wants to submit PRs to help turn this into a written version of the course I'm willing to work with you to do that, but for now it is just my notes.*

Github repo: https://github.com/joncalhoun/algorithmswithgo.com

I have tried to provide tests that make it easy for you to verify your code as you write it.

To test, navigate to the code and run `go test`

```bash
go test
```

*Sidenote: Wnat color? Try something like this: <https://github.com/rakyll/gotest>. I use a bash function that does something similar. It is provided below.

```bash
go_test() {
    go test $* | sed ''/PASS/s//$(printf "\033[32mPASS\033[0m")/'' | sed ''/SKIP/s//$(printf "\033[34mSKIP\033[0m")/'' | sed ''/FAIL/s//$(printf "\033[31mFAIL\033[0m")/'' | sed ''/FAIL/s//$(printf "\033[31mFAIL\033[0m")/'' | GREP_COLOR="01;33" egrep --color=always '\s*[a-zA-Z0-9\-_.]+[:][0-9]+[:]|^'
}
```
*Bash script stems from something shared by Dave Cheney on Twitter iirc*

Generally you don't want to run ALL of the tests. We can use the `-run` flag to run a tests for a specific function.

```bash
go test -run=NumInList
```

It is also worth noting that these tests aren't a great example of how you should necessarily write tests. Many of them are written specifically to make it easier for beginners. Eg rather than passing an `io.Writer` into the `FizzBuzz` function, I instead opt to change what `os.Stdout` is in the test. I generally wouldn't recommend this.

If that is all confusing to you, don't worry about it. It is a technical detail that doesn't matter right now. I'm just saying don't use the algorithm tests as a way to learn to testing in Go. Instead, start here: <https://www.calhoun.io/how-to-test-with-go/>

I also have a paid course on testing here: <https://testwithgo.com> If you like this course, you may enjoy that one too.

And one final warning - these tests are NOT exhaustive. They may miss corner cases. The idea is to give you a decent starting point to verify your code but that's it. They will probably suffice for the first few modules, but in later, more complex algorithms, they probably won't. See the last few sections of this module for some suggestions on other ways to practice and test your code using sites like Code Jam, HackerRank, etc.

As the course progresses we will probably start to use benchmarks too. I'm not going to teach those, but there are tons of great resources including the std lib docs, Dave Cheney's blog post (<https://dave.cheney.net/2013/06/30/how-to-write-benchmarks-in-go>), and I even touch on them briefly in my testing course.

Lastly, the `solutions` directory will have code solutions (along with a copy of the tests) in case you need them. I'll never check solutions into the base directory so you have a good starting point with tests.


Source : https://github.com/joncalhoun/algorithmswithgo.com/tree/master/module01