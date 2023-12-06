# slogctx

Context aware slog

## Usage

```go
func init() {
	slog.SetDefault(slog.New(slogctx.NewHandler(slog.NewTextHandler(os.Stdout, nil))))
}

func main() {
	ctx := context.Background()
	ctx = slogctx.With(ctx, "foo", "bar")
	slog.InfoContext(ctx, "hello world")
}
```

```sh
$ go run .
time=2023-12-06T16:29:33.440-07:00 level=INFO msg="hello world" foo=bar
```