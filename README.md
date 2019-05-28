# how to run

```bash
bundle install
bundle exec start_server
```

# how to make requests

using ghz to perform load test

```bash
ghz -proto ./hello.proto  -call helloworld.Greeter/SayHello -d '{"name": "World"}' -n=10000 -c=1000 -insecure localhost:9000
```

# benchmark results
```
Summary:
  Count:        10000
  Total:        3.53 s
  Slowest:      432.26 ms
  Fastest:      8.60 ms
  Average:      334.39 ms
  Requests/sec: 2831.55

Response time histogram:
  8.600 [1]     |
  50.966 [74]   |
  93.333 [74]   |
  135.699 [106] |∎
  178.065 [113] |∎
  220.431 [107] |∎
  262.797 [100] |∎
  305.163 [119] |∎
  347.529 [6211]        |∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎
  389.896 [2891]        |∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎∎
  432.262 [204] |∎

Latency distribution:
  10% in 333.69 ms 
  25% in 336.55 ms 
  50% in 340.87 ms 
  75% in 352.35 ms 
  90% in 365.79 ms 
  95% in 371.19 ms 
  99% in 403.96 ms 
Status code distribution:
  [OK]   10000 responses
```