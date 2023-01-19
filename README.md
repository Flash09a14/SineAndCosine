# SineAndCosine
## Python Sine and Cosine Wave simulation
### How to run:
###### Only need to do once:
1) Open your terminal
2) type: pip3 install -r requirements.txt
3) If it returns an error, make sure your terminal path is on the folder of your project (type: cd (project folder path))
4) Close the terminal once all requirements are installed
###### After installments:
5) Run the python file (either using the terminal or directly)

## Code:
```py
import matplotlib.pyplot as plt
import numpy as np
from os import system, name

def main():
    if name == "nt":
        _ = system("cls")
    else:
        _ = system("clear")
    try:
        print("NOTE: This is a very close approximate result of the waves. Accuracy may vary.\n")
        print("Sine and cosine are periodic functions that are used in trigonometry to represent the shape of a wave.\nThey are defined by mathematical equations and have a smooth, repetitive shape that oscillates between a minimum and maximum value.\nThe sine wave is defined by the function y = sin(x), where x is the angle in radians, and y is the amplitude (or height) of the wave at that angle.\nThe sine wave oscillates around the x-axis, and the amplitude of a sine wave is the maximum height of the wave.\nThe cosine wave is defined by the function y = cos(x), where x is the angle in radians, and y is the amplitude (or height) of the wave at that angle\nThe cosine wave oscillates around the y-axis.\nSine and cosine waves are related to each other.\nA sine wave can be obtained from a cosine wave by a phase shift of 90 degrees and vice versa.\nFor a visual representation, visit: https://setosa.io/ev/sine-and-cosine/#:~:text=Sine%20and%20cosine%20—%20a.k.a.%2C%20sin,adjacent%20side%20to%20the%20hypotenuse%20. \n")
        print("The 'frequency' of the wave changes the amount of waves we have in a specific area.\nThe 'initial radian' changes the starting radian of the wave, rather than it always starting at 0.\nThe 'radius' changes the circle radius therefore increasing the height of the wave.\n'Operation' asks you what waves do you want to show in the simulation.\n")
        while True:
            frequency = float(input("Frequency: "))
            start_radian = float(input("Initial Radian: "))
            wave_height = float(input("Radius: "))
            operation = input("Operation (Sin, Cos, Both): ")
            
            x = np.linspace(0, 2 * np.pi, 100)

            if operation == "Both":
                y_sine = wave_height * np.sin(frequency * (x + start_radian))
                y_cosine = wave_height * np.cos(frequency * (x + start_radian))
                plt.plot(x, y_sine, 'r', x, y_cosine, 'b')

            elif operation == "Sin":
                y_sine = wave_height * np.sin(frequency * (x + start_radian))
                plt.plot(x, y_sine, 'r')

            elif operation == "Cos":
                y_cosine = wave_height * np.cos(frequency * (x + start_radian))
                plt.plot(x, y_cosine, 'b')

            else:
                print("Invalid operation")
            
            plt.show()
            
    except ValueError as e:
        print(e)
        return main()

if __name__ == "__main__":
    main()
```

### Sine/Cosine waves explanation:

###### Sine and cosine are periodic functions that are used in trigonometry to represent the shape of a wave.They are defined by mathematical equations and have a smooth, repetitive shape that oscillates between a minimum and maximum value.The sine wave is defined by the function y = sin(x), where x is the angle in radians, and y is the amplitude (or height) of the wave at that angle.The sine wave oscillates around the x-axis, and the amplitude of a sine wave is the maximum height of the wave.The cosine wave is defined by the function y = cos(x), where x is the angle in radians, and y is the amplitude (or height) of the wave at that angle\nThe cosine wave oscillates around the y-axis.Sine and cosine waves are related to each other.A sine wave can be obtained from a cosine wave by a phase shift of 90 degrees and vice versa.For a visual representation, visit: https://setosa.io/ev/sine-and-cosine/#:~:text=Sine%20and%20cosine%20—%20a.k.a.%2C%20sin,adjacent%20side%20to%20the%20hypotenuse%20.

### Toolkit:
###### The 'frequency' of the wave changes the amount of waves we have in a specific area.The 'initial radian' changes the starting radian of the wave, rather than it always starting at 0.The 'radius' changes the circle radius therefore increasing the height of the wave.'Operation' asks you what waves do you want to show in the simulation.
