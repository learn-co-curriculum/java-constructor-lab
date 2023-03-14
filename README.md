# Constructor Lab

## Learning Goals

- Define multiple constructors with parameters
- Use constructor chaining

## Instructions

Fork and clone the lab.

- The `RentalUnit` class represents an apartment for rent. The class defines instance variables and getter methods.
- You will add constructors to `RentalUnit`, along with Junit test methods to `RentalUnitTest`.

```java
public class RentalUnit {
    private String address;
    private int monthlyRate;
    private boolean petAllowed;
    private int minimumMonths;

    // Constructor methods here
    

    public String getAddress() {
        return address;
    }

    public int getMonthlyRate() {
        return monthlyRate;
    }

    public boolean isPetAllowed() {
        return petAllowed;
    }

    public int getMinimumMonths() {
        return minimumMonths;
    }
}
```

## Task #1

1. Edit `RentalUnit` to add a constructor that takes 4 parameters: `address`, `monthlyRate`,
   `petAllowed`, and `minimumMonths`.
   The constructor should use the parameters to initialize the corresponding instance variables.
   HINT: Have IntelliJ generate the constructor for you.

2. Edit `RentalUnitTest` to add the following test method:

```java
@Test
void test4ArgsConstructor() {
    
    //123 Main St, $1800 monthly rent, allows pets, 15 month minimum lease
        
    RentalUnit unit1 = new RentalUnit("123 Main St", 1800, true, 15);
    assertEquals("123 Main St", unit1.getAddress());
    assertEquals(1800, unit1.getMonthlyRate());
    assertTrue(unit1.isPetAllowed());
    assertEquals(15, unit1.getMinimumMonths());

    //444 Elm Dr, 3000 monthly rent, does not allow pets, 9 month minimum lease
        
    RentalUnit unit2 = new RentalUnit("444 Elm Dr", 3000, false, 9);
    assertEquals("444 Elm Dr", unit2.getAddress());
    assertEquals(3000, unit2.getMonthlyRate());
    assertFalse(unit2.isPetAllowed());
    assertEquals(9, unit2.getMinimumMonths());
    
}
```

Confirm the Junit test passes:

![rental 4 args test](https://curriculum-content.s3.amazonaws.com/6676/java-methods/rental_4args.png)



## Task #2

1. Edit `RentalUnit` to add a second constructor that takes 2 parameters: `address`, `monthlyRate`.
    - The 2-args constructor should call the 4-args constructor as the first and only line of code in the method body.
    - The constructor call should pass default values for the unspecified fields:
      Pets are not allowed and the minimum lease term is 12 months.

2. Edit `RentalUnitTest` to add the following test method:


```java
@Test
void test2ArgsConstructor() {

    //999 Willow Way, $2400 monthly rent, does not allow pets, 12 month minimum lease

    RentalUnit unit1 = new RentalUnit("999 Willow Way", 2400);
    assertEquals("999 Willow Way", unit1.getAddress());
    assertEquals(2400, unit1.getMonthlyRate());
    assertFalse(unit1.isPetAllowed());
    assertEquals(12, unit1.getMinimumMonths());
    
    //1 Birch Lane, 1000 monthly rent, does not allow pets, 12 month minimum lease

    RentalUnit unit2 = new RentalUnit("1 Birch Lane", 1000);
    assertEquals("1 Birch Lane", unit2.getAddress());
    assertEquals(1000, unit2.getMonthlyRate());
    assertFalse(unit2.isPetAllowed());
    assertEquals(12, unit2.getMinimumMonths());
    
}
```

Confirm the Junit tests both pass:

![rental 2 args test](https://curriculum-content.s3.amazonaws.com/6676/java-methods/rental_2args.png)