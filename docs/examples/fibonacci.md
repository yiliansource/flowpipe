```
def fib(n): n eq 0 ? > 0
               v
            n eq 1 ? > 1
               v
            (1, 0, 1) > (++, @2, @1 + @2) > n eq @0 ? > @2
                               ^              v
                               . <          < .

10 > fib > print