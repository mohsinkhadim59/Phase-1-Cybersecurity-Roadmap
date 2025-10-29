# 📓 Day 20

**Focus:** TASK NAME

## Tasks
- [ ] Task 1
- [ ] Task 2

## Findings
- Command(s): 
- Notes: 

## Reflections
- What I learned today:
- What needs review:

>[!Warning] This Example is a must to understand various functionalities
>```bash
>#!/bin/zsh 
># Interactive calculator script using bc 
># Function to calculate area of a circle 
>calculate_circle_area() { 
>echo -n "Enter the radius of the circle: " 
>read radius 
>area=$(echo "scale=2; 3.14159 * $radius * $radius" | bc)
> echo "The area of the circle with radius $radius is: $area square units" } 
> # Function to calculate area of a rectangle 
> calculate_rectangle_area() { 
> echo -n "Enter the length of the rectangle: " 
> read length
>  echo -n "Enter the width of the rectangle: " 
>  read width 
>  area=$(echo "scale=2; $length * $width" | bc) 
>  echo "The area of the rectangle with length $length and width $width is: $area square units" } 
>  
>  # Function to solve quadratic equation ax² + bx + c = 0 solve_quadratic() { 
>  echo -n "Enter coefficient a: " 
>  read a 
>  echo -n "Enter coefficient b: " 
>  read b echo -n "Enter coefficient c: " 
>  read c 
>  # Calculate discriminant 
>  discriminant=$(echo "scale=4; ($b * $b) - (4 * $a * $c)" | bc) 
>  
>  # Check the discriminant 
>  if (($(echo "$discriminant < 0" | bc -l))); 
>  then 
>  echo "The equation has no real solutions (discriminant < 0)" 
>  elif (($(echo "$discriminant == 0" | bc -l))); then
>   # One solution x=$(echo "scale=4; -$b / (2 * $a)" | bc)
>    echo "The equation has one solution: x = $x" 
>    else 
>    # Two solutions 
>    x1=$(echo "scale=4; (-$b + sqrt($discriminant)) / (2 * $a)" | bc -l) 
>    x2=$(echo "scale=4; (-$b - sqrt($discriminant)) / (2 * $a)" | bc -l) 
>    echo "The equation has two solutions:" 
>    echo "x1 = $x1" 
>    echo "x2 = $x2" 
>    fi 
>    } 
>    # Main program loop 
>    while true; do echo "" echo "===== BC Calculator Menu =====" 
>    echo "1. Calculate area of a circle" 
>    echo "2. Calculate area of a rectangle" 
>    echo "3. Solve quadratic equation (ax² + bx + c = 0)" 
>    echo "4. Exit" 
>    echo "" 
>    
>    echo -n "Enter your choice (1-4): " 
>    read choice 
>    case $choice in 
>    1) calculate_circle_area ;; 
>    2) calculate_rectangle_area ;; 
>    3) solve_quadratic ;; 
>    4) 
>   echo "Exiting calculator. Goodbye!" 
>   exit 0 
>   ;; 
>   *) 
>   echo "Invalid option. Please try again." ;; 
>   esac 
>   done
>```

[Cheatsheet-Tree](Cheatsheet-Tree.md) 🔗
