# datavalleyinternship
#stringreplace
import java.util.Scanner;

public class ReplaceCharacterAtIndex {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter a string: ");
        String originalString = scanner.nextLine();
        
        System.out.print("Enter the index where character needs to be replaced: ");
        int index = scanner.nextInt();
        
        System.out.print("Enter the replacement character: ");
        char replacementChar = scanner.next().charAt(0);
        
        String modifiedString = replaceCharacterAtIndex(originalString, index, replacementChar);
        
        System.out.println("Original String: " + originalString);
        System.out.println("Modified String: " + modifiedString);
        
        scanner.close();
    }
    
    public static String replaceCharacterAtIndex(String str, int index, char replacementChar) {
        if (index < 0 || index >= str.length()) {
            throw new IndexOutOfBoundsException("Index is out of range.");
        }
        
        char[] chars = str.toCharArray();
        chars[index] = replacementChar;
        return new String(chars);
    }
}

#exceptiondivide
public class DivisionExample {
    public static void main(String[] args) {
        int numerator = 10;
        int denominator = 0;
        
        try {
            divideNumbers(numerator, denominator);
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
    
    public static void divideNumbers(int numerator, int denominator) {
        if (denominator == 0) {
            throw new ArithmeticException("Division by zero is not allowed.");
        }
        
        int result = numerator / denominator;
        System.out.println("Result of division: " + result);
    }
}

#createexception
class CustomValidationException extends Exception {
    public CustomValidationException(String message) {
        super(message);
    }
}

public class CustomValidationDemo {
    public static void main(String[] args) {
        try {
            validateNumber(5);
            System.out.println("Number is valid.");
            
            validateNumber(-3); // This will throw CustomValidationException
        } catch (CustomValidationException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
    
    public static void validateNumber(int number) throws CustomValidationException {
        if (number < 0) {
            throw new CustomValidationException("Number cannot be negative.");
        }
    }
}

#convertingvowels
import java.util.Scanner;

public class CountVowelsConsonants {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine();
        
        int vowelCount = countVowels(inputString);
        int consonantCount = countConsonants(inputString);
        
        System.out.println("Number of vowels: " + vowelCount);
        System.out.println("Number of consonants: " + consonantCount);
        
        scanner.close();
    }
    
    public static int countVowels(String str) {
        int count = 0;
        str = str.toLowerCase();
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
                count++;
            }
        }
        return count;
    }
    
    public static int countConsonants(String str) {
        int count = 0;
        str = str.toLowerCase();
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if ((ch >= 'a' && ch <= 'z') && !(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u')) {
                count++;
            }
        }
        return count;
    }
}


