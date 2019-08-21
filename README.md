
# Go pointer vs copy
Go sample project to understand difference between pointer and copy

## Instructions

### Normal

```
# by copy
go test ./... -bench=BenchmarkMemoryStackSingle -benchmem -run='^$' -count=10 > stack.txt && benchstat stack.txt
# by pointer
go test ./... -bench=BenchmarkMemoryHeapSingle -benchmem -run='^$' -count=10 > head.txt && benchstat head.txt
```

### Normal - Limiting the processor

```
# by copy
GOMAXPROCS=1 go test ./... -bench=BenchmarkMemoryStackSingle -benchmem -run='^$' -count=10 > stack.txt && benchstat stack.txt
# by pointer
GOMAXPROCS=1 go test ./... -bench=BenchmarkMemoryHeapSingle -benchmem -run='^$' -count=10 > head.txt && benchstat head.txt
```

### Mutiple

```
# by copy
go test ./... -bench=BenchmarkMemoryStackMultiple -benchmem -run='^$' -count=10 > stack.txt && benchstat stack.txt
# by pointer
go test ./... -bench=BenchmarkMemoryHeapMultiple -benchmem -run='^$' -count=10 > head.txt && benchstat head.txt
```

### Mutiple - Limiting the processor

```
# by copy
GOMAXPROCS=1 go test ./... -bench=BenchmarkMemoryStackMultiple -benchmem -run='^$' -count=10 > stack.txt && benchstat stack.txt
# by pointer
GOMAXPROCS=1 go test ./... -bench=BenchmarkMemoryHeapMultiple -benchmem -run='^$' -count=10 > head.txt && benchstat head.txt
```

---

## Links

* https://medium.com/@blanchon.vincent/go-should-i-use-a-pointer-instead-of-a-copy-of-my-struct-44b43b104963
