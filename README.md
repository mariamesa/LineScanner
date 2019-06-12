# LineScanner
Opens a file and determines how many numbers are on each line.

import java.util.Scanner;
import java.io.*;

public class LineScanner {
    public static void main (String [] arg) throws IOException {
        Scanner inFile = new Scanner(new File("numbers.text"));
        int count = 0,lineNumber = 0;
        while(inFile.hasNextLine())  {
            String line = inFile.nextLine();
            Scanner sc = new Scanner(line);
            while(sc.hasNextInt()) {
                sc.nextInt();
                count++;
            }
            lineNumber++;
            System.out.println("There are " + count + " numbers on line " + lineNumber);
            count = 0;
        }
    }
}
