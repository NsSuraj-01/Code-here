# Kaprekar Number Program

## Introduction

The Kaprekar's routine is a simple iterative procedure that takes a 4-digit number as input and produces a new number by rearranging its digits. The routine is repeated until the resulting number is the Kaprekar number (6174).

## Program Description

The program consists of two main functions:

*   `diff`: calculates the difference between two numbers.
*   `kaprekar`: performs the Kaprekar's routine and returns the number of iterations required to reach the Kaprekar number.

## Code

```bash
#!/bin/bash

# Function to calculate the difference between two numbers
diff() {
  local inc=$1
  local dec=$2
  echo $((dec - inc))
}

# Function to perform Kaprekar's routine
kaprekar() {
  local num=$1
  local knum=6174
  local cnt=0

  # Check if input is a 4-digit number
  if [ ${#num} -ne 4 ] || [ ${num:0:1} -eq 0 ]; then
    echo "Invalid input"
    return
  fi

  # Check if all digits are the same
  if [ $(echo "$num" | fold -w1 | sort -u | wc -l) -eq 1 ]; then
    echo "Invalid input"
    return
  fi

  while true; do
    # Sort digits in ascending and descending order
    local inc=$(echo "$num" | fold -w1 | sort -n | tr -d '\n')
    local dec=$(echo "$num" | fold -w1 | sort -rn | tr -d '\n')

    # Calculate the difference
    local res=$(diff $inc $dec)

    # Check if the result is the Kaprekar number
    if [ $res -eq $knum ]; then
      break
    fi

    # Update the number and increment the counter
    num=$res
    cnt=$((cnt + 1))
  done

  echo "Achieved after $cnt iterations"
}

# Read input from the user
read -p "Enter a 4-digit number: " num

# Call the Kaprekar function
kaprekar $num
```

## Usage

1. **Save the code:** Save the above code in a file named `kaprekar.sh`.
2. **Make it executable:** Run the command `chmod +x kaprekar.sh` in your terminal.
3. **Run the program:** Execute the command `bash kaprekar.sh`.
4. **Enter the number:** When prompted, enter a 4-digit number. 

## Example Output

```bash
Enter a 4-digit number: 1234
Achieved after 3 iterations
```

## Java Implementation
```java
public static StringBuilder diff(List<Character> inc, List<Character> dec) {
        StringBuilder tmp = new StringBuilder();
        for(char ch : inc) tmp.append(ch);
        Integer num1 = Integer.parseInt(tmp.toString());

        tmp = new StringBuilder();
        for(char ch : dec) tmp.append(ch);
        Integer num2 = Integer.parseInt(tmp.toString());

        return new StringBuilder(num2 - num1 + "");
    }

    // Kaprekar number - 6174
    public static void kNum(String num) {
        if(num.length() != 4 || num.charAt(0) == '0') {
            System.out.println("Invalid num");
            return;
        }
 
        if (num.chars().distinct().count() == 1) {
            System.out.println("Invalid input");
            return;
        }

        List<Character> nums = new ArrayList<>();
        for(char ch : num.toCharArray()) nums.add(ch);

        String knum = "6174";
        int cnt = 0;

        while(true) {
            
            List<Character> inc = new ArrayList<>(nums);
            List<Character> dec = new ArrayList<>(nums);
            inc.sort((a,b) -> a-b);
            dec.sort((a,b) -> b-a);

            StringBuilder res = diff(inc, dec);

            if(res.toString().equals(knum)) break;
            nums = new ArrayList<>();
            for(char ch : res.toString().toCharArray()) nums.add(ch);
            cnt++;
        }

        System.out.println("achieved after " + cnt + " iterations");
    }
```
