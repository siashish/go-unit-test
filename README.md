# Unit Test in Go Language

## From your project’s root directory, run your first test:
`go test`
### output
`PASS`
`ok      github.com/unittest     0.748s`

## Our go test is probably sufficient for our little program, but there will be times when you’ll wish to see what tests are running and how long each takes. Adding the -v flag increases verbosity. Rerun your test with the new flag:
`go test -v`
### output
`=== RUN   TestAdd`
`--- PASS: TestAdd (0.00s)`
`=== RUN   ExampleAdd`
`--- PASS: ExampleAdd (0.00s)`
`PASS`
`ok      github.com/unittest     0.379s`

## Check test coverage
`go test -cover`
### output
`PASS`
`coverage: 50.0% of statements`
`ok      github.com/unittest     0.181s`

## Run the following command to calculate the coverage for your current unit test:
`go test -coverprofile=coverage.out`
### output
`PASS`
`coverage: 50.0% of statements`
`ok      github.com/unittest     0.695s`

## Go saved this coverage data in the file coverage.out. Now you can present the results in a web browser.
## Run the following command:
`go tool cover -html=coverage.out`
### output
`open html file in browser`

## Now let’s use go test again to run our benchmark:
`go test -bench=.`
## The . will match every benchmark function in a file.
### output
`goos: darwin`
`goarch: amd64`
`pkg: github.com/unittest`
`cpu: VirtualApple @ 2.50GHz`
`BenchmarkAdd-8          1000000000               0.3127 ns/op`
`PASS`
`ok      github.com/unittest     0.811s`

## You can also declare benchmark functions explicitly:
`go test -bench=Add`
### output
`goos: darwin`
`goarch: amd64`
`pkg: github.com/unittest`
`cpu: VirtualApple @ 2.50GHz`
`BenchmarkAdd-8          1000000000               0.3116 ns/op`
`PASS`
`ok      github.com/unittest     0.525s`

[Credit](https://www.digitalocean.com/community/tutorials/how-to-write-unit-tests-in-go-using-go-test-and-the-testing-package)