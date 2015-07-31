
Spozin' you have a scenario that has a step like the following:
```
And the foo is barred:
  | foo | bar | baz |
  | 1   | 2   | 100 |
```

If you have a Pojo who's properties match the table like this:

```java

public static class FooBar {
        public int foo;
        public int bar;
        public int baz;

        public int getBaz() {
            return baz;
        }

        public void setBaz(int baz) {
            this.baz = baz;
        }

        public int getBar() {
            return bar;
        }

        public void setBar(int bar) {
            this.bar = bar;
        }


        public int getFoo() {
            return foo;
        }

        public void setFoo(int foo) {
            this.foo = foo;
        }
```

Then your step definition auto-magically serializes your datatable to your pojo like this:
```java
   @And("^the foo is barred:$")
    public void the_foo_is_barred(List<FooBar> fooBars) throws Throwable {
        FooBar firstFooBar = fooBars.get(0);
        //... do something interesting!
    }

```

Also, not all properties are required in the table so
```
And the foo is barred:
  | foo |
  | 1   | 
```

is totally acceptable as well ;)
