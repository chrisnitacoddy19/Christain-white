 Overview
This repository contains the source code for a simple calculator application built using Java Swing. The application allows users to perform basic arithmetic operations such as addition, subtraction, multiplication, division, and modulus, with an easy-to-use graphical user interface (GUI).
Features
Basic arithmetic operations:
Addition (+)
Subtraction (-)
Multiplication (*)
Division (/)
Modulus (%)
Clear (C) button to reset the input.
Delete (DEL) button to remove the last digit entered.
Error handling for division by zero and modulus by zero.
Simple and intuitive GUI layout.
Contributions
This project was developed and contributed to by a group of 10 individuals, each bringing their expertise to different areas of the development process. The contributions were distributed across various aspects of the application, including the user interface, event handling, testing, and documentation. The team worked collaboratively to design, implement, and test the calculator to ensure its functionality and usability.
Group Members and Their Contributions:
>>Christain (Project Manager)
Managed the overall project, coordinated tasks, and ensured timely delivery.
Set up the project structure and organized team meetings.
>>Charles (UI/UX Designer)
Designed the graphical user interface (GUI), ensuring a simple and user-friendly layout.
Focused on button positioning, color schemes, and text field design to enhance the user experience.
 SHALOM ASUELIMEN Electrical(Lead Developer)
Led the development of the main logic behind the calculator's functionality.
Implemented the core arithmetic operations, handling the event-driven architecture using ActionListener.
Integrated error handling for division by zero and modulus by zero.
AMOS BENJAMIN Electrical(Java Swing Specialist)
Focused on using Java Swing components like JFrame, JButton, and JTextField to construct the application.
Ensured that the application maintained cross-platform compatibility and provided a smooth experience on all supported operating systems.
 Alhassan Godwin Ojochegbe from 
Electrical and Electronics Engineering (Backend Developer)
Contributed to the backend logic, ensuring accurate calculation of arithmetic operations.
Worked on implementing the mathematical functions and optimizing the calculation flow.
 Muhammad Muazu from
Mechatronics (Testing Lead)
Developed and executed test cases to ensure that all arithmetic operations worked as expected.
Conducted unit tests and integration tests, focusing on edge cases like division by zero and clearing input.
 Oyeniyi Hussainah Kehinde from 
Mechatronics Engineering (Documentation Specialist)
Created the project documentation, including the README file and user manual.
Ensured that the documentation was clear and easy to follow for future developers and users.
 Sashe Gorman Mechatronics (Quality Assurance)
Assisted in identifying and fixing bugs during the testing phase.
Verified the correctness of results and ensured that no unexpected behavior occurred in the application.
....... (Security & Performance Analyst)
Focused on improving the performance of the calculator application.
Ensured the application ran efficiently and handled potential issues like excessive memory usage or slowdowns.
..... (Deployment & Release Manager)
Handled the deployment and release process for the application.
Prepared the project for submission, packaged the files, and made sure that the application could be easily run by users.
Technologies Used
Java 8: Programming language used to develop the application.
Swing API: Used for building the graphical user interface (GUI).
AWT (Abstract Window Toolkit): Used for handling events and layout management.
Prerequisites
To run this application, ensure the following:
Java Development Kit (JDK) version 8 or higher is installed.
A Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans for compiling and running the code.
Installation and Setup
Clone the Repository: To get started, clone this repository to your local machine using the following command:
bash
Copy
git clone https://github.com/yourusername/calculator-java-swing.git

Navigate to the project directory:
bash
Copy
cd calculator-java-swing

Compile and Run: If you are using a terminal/command prompt:
Compile the Calculator.java file:
bash
Copy
javac Calculator.java

Run the compiled Calculator class:
bash
Copy
java Calculator

Alternatively, if you're using an IDE (e.g., IntelliJ IDEA or Eclipse), simply import the project and run the Calculator class.
Code Walkthrough
1. Frame Setup:
The JFrame class is used to create the main window of the application. The frame properties such as title, size, layout, and background color are set here.
java
Copy
setTitle("Calculator");
setSize(1000, 1000);
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
setLayout(null);
getContentPane().setBackground(Color.BLUE);

2. Text Field:
A JTextField is used to display the current input or result. It is set as non-editable, so the user can only interact with it through the buttons.
java
Copy
textField = new JTextField();
textField.setBounds(30, 25, 320, 50);
textField.setEditable(false);
textField.setFont(new Font("Arial", Font.BOLD, 22));
add(textField);

3. Buttons for Numbers and Operations:
Number buttons (0-9) and operator buttons (+, -, *, /, %, =) are created using the JButton class.
Action listeners are added to these buttons to handle user input.
java
Copy
for (int i = 0; i < 10; i++) {
    numberButtons[i] = new JButton(String.valueOf(i));
    numberButtons[i].addActionListener(this);
    numberButtons[i].setFont(new Font("Arial", Font.BOLD, 20));
    numberButtons[i].setBackground(Color.GRAY);
    numberButtons[i].setForeground(Color.WHITE);
}

4. Action Listener:
The actionPerformed method is implemented to handle the button clicks. It checks which button was pressed and performs the corresponding operation.
Numbers are added to the text field.
Operators are stored and used to perform the respective calculation when the "=" button is pressed.
java
Copy
@Override
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == addButton) {
        num1 = Double.parseDouble(textField.getText());
        operator = '+';
        textField.setText("");
    }
    // Similar checks for other operators
}

5. Error Handling:
The application handles division by zero and modulus by zero errors by displaying an error message in the text field.
java
Copy
if (num2 == 0) {
    textField.setText("Error: Div by 0");
    return;
}

6. Clear and Delete Buttons:
Clear (C) resets the text field.
Delete (DEL) removes the last character entered.
java
Copy
clrButton.addActionListener(this);
delButton.addActionListener(this);

7. Main Method:
The main method creates an instance of the Calculator class to launch the application.
java
Copy
public static void main(String[] args) {
    new Calculator();
}

Testing
Ensure that all basic functionality is working as expected:
Perform simple calculations (+, -, *, /, %).
Test edge cases like dividing by zero and modulus by zero.
Verify that the "Clear" and "Delete" buttons function correctly.
Error Handling
Division by zero and modulus by zero will display appropriate error messages.
Any invalid input or operation will result in an error message being displayed in the text field.
Future Improvements
Add more advanced operations such as square root, exponentiation, etc.
Improve the user interface (UI) with a more modern look and feel.
Add keyboard support for better user experience.
Acknowledgments
Swing API documentation for providing the necessary components for creating a graphical user interface in Java.
Online tutorials and community resources for helping with Java Swing development.
