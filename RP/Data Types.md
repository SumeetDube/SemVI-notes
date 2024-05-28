Data types in programming define the type of data that can be stored and manipulated within a program. They specify the nature of the data (such as numbers, characters, or logical values) and the operations that can be performed on that data. In ABB's RAPID (Robot Application Programming Interface Description) language, various data types are used to handle different kinds of data efficiently. Let's explore the common data types in RAPID along with examples of programs to illustrate their usage.

### Common Data Types in RAPID:

#### 1. **Integer (INT)**:
   - Represents whole numbers (positive or negative) without decimal points.
   - Example:
     ```abb
     VAR INT num1 := 10;
     VAR INT result;

     result := num1 * 5;  ! Assigns result = 50
     ```

#### 2. **Real (REAL)**:
   - Represents floating-point numbers (numbers with decimal points).
   - Example:
     ```abb
     VAR REAL pi := 3.14159;
     VAR REAL radius := 5.0;
     VAR REAL area;

     area := pi * radius * radius;  ! Calculates area of a circle
     ```

#### 3. **Boolean (BOOL)**:
   - Represents logical values `TRUE` or `FALSE`.
   - Example:
     ```abb
     VAR BOOL isButtonPressed := TRUE;
     VAR BOOL isRunning;

     isRunning := (isButtonPressed AND NOT emergencyStop);  ! Logical expression
     ```

#### 4. **String (STRING)**:
   - Represents a sequence of characters (text).
   - Example:
     ```abb
     VAR STRING message := "Hello, World!";
     VAR STRING userInput;

     userInput := GetUserInput();  ! Function to get user input
     ```

#### 5. **Array (ARRAY)**:
   - Represents a collection of elements of the same data type.
   - Example:
     ```abb
     VAR REAL[3] coordinates := [10.0, 20.0, 30.0];
     VAR INT[5] numbers;

     numbers[0] := 1;
     numbers[1] := 2;
     numbers[2] := 3;
     ```

#### 6. **Enumeration (ENUM)**:
   - Represents a set of named constants (enumerators).
   - Example:
     ```abb
     TYPE ColorEnum:
       (
         RED,
         GREEN,
         BLUE
       );

     VAR ColorEnum selectedColor := ColorEnum.RED;
     ```

### Example Program Demonstrating Data Types in RAPID:

```abb
MODULE MainModule
  VAR INT num1 := 10;
  VAR REAL radius := 5.0;
  VAR BOOL isRunning := TRUE;
  VAR STRING message := "Hello, World!";
  VAR REAL[3] coordinates := [10.0, 20.0, 30.0];
  VAR ColorEnum selectedColor := ColorEnum.RED;

  PROC main()
    ! Calculate area of a circle
    VAR REAL area;
    area := CalcCircleArea(radius);
    OUTPUT "Area of circle with radius " + STRING(radius) + " is " + STRING(area);

    ! Display selected color
    DisplaySelectedColor(selectedColor);

    ! Check if the robot is running
    IF isRunning THEN
      OUTPUT "Robot is currently running";
    ELSE
      OUTPUT "Robot is stopped";
    ENDIF
  ENDPROC

  PROC CalcCircleArea(VAR REAL r) : REAL
    RETURN (3.14159 * r * r);
  ENDPROC

  PROC DisplaySelectedColor(VAR ColorEnum color)
    CASE color OF
      ColorEnum.RED:
        OUTPUT "Selected color is RED";
      ColorEnum.GREEN:
        OUTPUT "Selected color is GREEN";
      ColorEnum.BLUE:
        OUTPUT "Selected color is BLUE";
    ENDSELECT
  ENDPROC
ENDMODULE
```

- **Explanation**:
  - This RAPID program demonstrates the usage of various data types (`INT`, `REAL`, `BOOL`, `STRING`, `ARRAY`, `ENUM`) in defining variables (`VAR`) and performing operations.
  - The program calculates the area of a circle (`CalcCircleArea` function), displays the selected color (`DisplaySelectedColor` function), and checks if the robot is running (`IF` condition).
  - Data types are used to define variables (`VAR`) and parameters (`PROC`), perform calculations (`RETURN`), and control program flow (`IF`, `CASE`).

In summary, data types in RAPID provide a structured way to handle different types of data and enable efficient programming for controlling ABB robots. By understanding and utilizing these data types effectively, programmers can create robust and versatile robot applications in RAPID.