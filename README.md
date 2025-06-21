# LRU Cache in golang

```bash
go get https://github.com/dhyanio/go-lru
```

```golang
const (
  cacheCapabity  = 10
  cacheTTL       = 5 * time.Second
)

var evictFunc = func(key string, value []byte) {
  fmt.Printf("Evicted: %s -> %s\n", key, value)
}

cacheOpts := cache.CacheOpts{
  Capacity: cacheCapabity,
  TTL:      cacheTTL,
  OnEvict:  evictFunc,
}
cc := cache.NewCache(cacheOpts)
```
